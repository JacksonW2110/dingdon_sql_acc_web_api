## API Documentation
### DingDon
#### BaseUrl = https://dingdon-sql.ddns.net:2211
#### API Testing with Postman

#### Get JWT Token
- JWT Token expires every 30 minutes
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Auth/login with the login object attach to request body
```
  "email": "EMAIL",
  "password": "PASSWORD"
```
![image](https://github.com/user-attachments/assets/1dfa9ab9-64c2-47b1-a9f7-58c859eb56b4)

Result:
![image](https://github.com/user-attachments/assets/614c57c8-904c-4e23-84fa-561239f47eb8)

#### Attach the JWT Bearer Token for each API request
![image](https://github.com/user-attachments/assets/9cd4541a-73cb-46cc-ba98-c53a57975d44)

### Customer
#### Get All Customers
- Get All Customers from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Customers/GetAllCustomers
  ![image](https://github.com/user-attachments/assets/c4e2fa2a-377e-41c6-9d59-5627627bc4eb)

- Result:
  ![image](https://github.com/user-attachments/assets/a2060094-92e0-4491-a077-033ebe6f0edb)

#### Add Customer
- Add Customer to SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Customers/AddCustomer with the object attach to request body
  ```
  {
    "code": "string",
    "controlaccount": "string",
    "companyname": "string",
    "area": "string",
    "agent": "string",
    "creditterm": "string",
    "creditlimit": 0,
    "overduelimit": 0,
    "currencycode": "string",
    "outstanding": 0,
    "addCustomerBranchRequestDtos": [
      {
        "code": "string",
        "branchname": "string",
        "addresS1": "string",
        "addresS2": "string",
        "attention": "string",
        "phonE1": "string",
        "email": "string"
      }
    ]
  }
  ```
  ![image](https://github.com/user-attachments/assets/5f45d042-bf4f-46f6-92e9-73102deae457)

- Result:
  ![image](https://github.com/user-attachments/assets/685b3ce3-8efe-418e-993c-ae4edf947ed0)

### Update Customer 
- Update Customer to SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Customers/UpdateCustomer/{customerCode} with the object attach to request body
```
{
  "code": "string",
  "controlaccount": "string",
  "companyname": "string",
  "area": "string",
  "agent": "string",
  "creditterm": "string",
  "creditlimit": 0,
  "overduelimit": 0,
  "currencycode": "string",
  "outstanding": 0,
  "updateCustomerBranchRequestDtos": [
    {
      "code": "string",
      "branchname": "string",
      "addresS1": "string",
      "addresS2": "string",
      "attention": "string",
      "phonE1": "string",
      "email": "string"
    }
  ]
}
```
  ![image](https://github.com/user-attachments/assets/249847b5-6848-4bf7-b76c-328d9728741f)

- Result
  ![image](https://github.com/user-attachments/assets/8b737a60-5c5e-4815-a658-907f89458342)

#### Get Customer By Code
- Get Customer from SQL Accounting Database by Code
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Customers/GetCustomerByCode/{customerCode}
  ![image](https://github.com/user-attachments/assets/4a991d4d-7d84-4671-b3e3-fdab8f1057ed)

- Result:
  ![image](https://github.com/user-attachments/assets/91d722d7-f742-4722-a4f7-973976fd19d4)

#### Delete Customer
- Delete Customer from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Customers/DeleteCustomer/{customerCode}
  ![image](https://github.com/user-attachments/assets/dd60d8ab-29ac-4682-bac5-5ec5318f713b)

- Result:
  ![image](https://github.com/user-attachments/assets/0e5d055b-eec7-4e9c-a906-c1b0e50e5430)

### Item
#### Get All Items
- Get All Items from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/GetAllItems
  ![image](https://github.com/user-attachments/assets/cef4cb41-8b10-48c3-b67a-96b70e2c9617)

- Result:
  ![image](https://github.com/user-attachments/assets/d023fc98-cd34-4711-b6eb-1228c5508431)

#### Add Item
- Add Item to SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/CreateItem with the object attach to request body
- Make sure the StockGroup already existed in SQL Accounting
```
{
  "code": "string",
  "description": "string",
  "stockgroup": "string",
  "stockcontrol": true,
  "costingmethod": 0,
  "balsqty": 0,
  "addItemUomRequestDtos": [
    {
      "uom": "string",
      "rate": 0,
      "refcost": 0,
      "refprice": 0,
      "isbase": true
    }
  ]
}
```
  <img width="1272" height="718" alt="image" src="https://github.com/user-attachments/assets/0efe284b-6662-4d4f-8767-dbb969cbadeb" />
  <img width="1279" height="302" alt="image" src="https://github.com/user-attachments/assets/281b663d-09bb-4777-a62d-9c4af370cd4e" />

- Result:
  <img width="1271" height="840" alt="image" src="https://github.com/user-attachments/assets/0062a606-adc1-44bb-9766-aaf806dc93bc" />
  <img width="1270" height="143" alt="image" src="https://github.com/user-attachments/assets/c2f5d569-8291-41fb-9e9a-4578f090457d" />



#### Update Item
- Update Item to SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/UpdateItem/{itemCode} with object attach to request body
- Make sure the StockGroup already existed in SQL Accounting
  ```
  {
    "code": "string",
    "description": "string",
    "stockgroup": "string",
    "stockcontrol": true,
    "costingmethod": 0,
    "balsqty": 0;
    "updateItemUomRequestDtos": [
      {
        "uom": "string",
        "rate": 0,
        "refcost": 0,
        "refprice": 0,
        "isbase": true
      }
    ]
  }
  ```
  <img width="1290" height="776" alt="image" src="https://github.com/user-attachments/assets/bbbd7c6f-d01e-4b7d-af55-7a19257dd53f" />
  <img width="1286" height="199" alt="image" src="https://github.com/user-attachments/assets/f81ed432-8de7-4d09-a71f-cb987c42359e" />


- Result:
  <img width="1268" height="862" alt="image" src="https://github.com/user-attachments/assets/b42768e0-065e-4c9a-a8b3-0006c16a9398" />
  <img width="1280" height="233" alt="image" src="https://github.com/user-attachments/assets/d2eeba49-0172-4713-95f2-aab85ebaeeb0" />


#### Get Item by ItemCode
- Get Item by ItemCode from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/GetItemByItemCode/{itemCode}
  ![image](https://github.com/user-attachments/assets/f96b4871-13b9-4e8e-bff8-03ebf33d1c2f)

- Result:
  ![image](https://github.com/user-attachments/assets/a88de8bc-8999-4a8f-a352-b12da4e196a7)

#### Delete Item
- Delete Item from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/DeleteItem/{itemCode}
  <![image](https://github.com/user-attachments/assets/6abe0f53-fb21-4a6c-833e-12463a75b671)

- Result:
  ![image](https://github.com/user-attachments/assets/63f488dd-e81c-49c0-9be5-467454e753bb)

### SalesInvoice
#### Get All SalesInvoices
- Get all SalesInvoices from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/GetAllSalesInvoices
  ![image](https://github.com/user-attachments/assets/ee203691-9d02-4dd4-a0a5-dfd2b3bc061c)

- Result:
  ![image](https://github.com/user-attachments/assets/4d9f7e49-7852-43cb-9a7f-f59c91e14391)
  ![image](https://github.com/user-attachments/assets/4a68f759-090b-4a30-b93f-502559a96837)

#### Create SalesInvoice
- Create SalesInvoice in SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/CreateSalesInvoice with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docno": "string",
    "docdate": "2025-06-13",
    "code": "string",
    "project": "string",
    "docamt": 0,
    "addSalesInvoiceDetailRequestDtos": [
      {
        "itemcode": "string",
        "description": "string",
        "qty": 0,
        "uom": "string",
        "unitprice": 0,
        "disc": "string",
        "tax": "string",
        "taxrate": "string",
        "taxinclusive": true
      }
    ]
  }
  ```
  ![image](https://github.com/user-attachments/assets/780a49d4-5187-49b5-b9b4-b482723873c3)

- Result:
  ![image](https://github.com/user-attachments/assets/84a1fd6c-6cb2-40d7-ae70-c7c2c6a8c386)
  ![image](https://github.com/user-attachments/assets/dd845e5d-a5a2-4ebd-9ff6-9e329eaa00a4)

#### Update SalesInvoice
- Update SalesInvoice in SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/UpdateSalesInvoice/{invoiceNo} with object attach to request body
- Make sure the customer existed in SQL Accounting Database
  ```
  {
    "docdate": "2025-06-13",
    "code": "string",
    "project": "string",
    "docamt": 0,
    "updateSalesInvoiceDetailRequestDtos": [
      {
        "itemcode": "string",
        "description": "string",
        "qty": 0,
        "uom": "string",
        "unitprice": 0,
        "disc": "string",
        "tax": "string",
        "taxrate": "string",
        "taxinclusive": true
      }
    ]
  }
  ```
  ![image](https://github.com/user-attachments/assets/1d5bf782-5fa3-4758-a8b4-9fab62968f8b)

- Result
  ![image](https://github.com/user-attachments/assets/1aaa6cfc-da41-409c-8543-82842bef1a24)
  ![image](https://github.com/user-attachments/assets/4044d120-7543-4719-8829-ac2ffd5342fa)

#### Get SalesInvoice by InvoiceNo
- Get SalesInvoice by InvoiceNo from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/GetSalesInvoiceByDocNo/{invoiceNo}
  ![image](https://github.com/user-attachments/assets/3a4432f5-b04c-4cb9-befd-1d173c85b7e6)

- Result:
  ![image](https://github.com/user-attachments/assets/5060c8c1-7f8e-4864-a79b-2e84bdc68107)
  ![image](https://github.com/user-attachments/assets/0317ba03-651f-4968-a7bc-51d35120dff1)

#### Delete SalesInvoice
- Delete SalesInvoice in SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/DeleteSalesInvoice/{invoiceNo}
  ![image](https://github.com/user-attachments/assets/e01da130-45ad-455e-b5d5-302797984507)

- Result:
  ![image](https://github.com/user-attachments/assets/c187a913-24dc-4275-82d8-f8cd82d8590e)

