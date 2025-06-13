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
![image](https://github.com/user-attachments/assets/0505358a-3986-4340-b85f-372c46116135)

Result:
![image](https://github.com/user-attachments/assets/b72ed892-6122-4618-87d0-4e6a5c23c4ae)

#### Attach the JWT Bearer Token for each API request
![image](https://github.com/user-attachments/assets/45aafc9d-3ac1-4a63-a299-89753bbce691)


### Customer
#### Get All Customers
- Get All Customers from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Customers/GetAllCustomers
  ![image](https://github.com/user-attachments/assets/98bee8b5-917a-4d31-8ea0-8bea60fcb83e)

- Result:
  ![image](https://github.com/user-attachments/assets/43ce899e-8d59-42fa-b50d-5257697d45af)

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
  ![image](https://github.com/user-attachments/assets/e0e3013f-47b5-4027-af46-a566099ada04)

- Result:
  ![image](https://github.com/user-attachments/assets/095bbe4b-3401-4ed3-9199-f1c514af4494)

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
  ![image](https://github.com/user-attachments/assets/f712e221-47cb-4048-bd24-3ceea674921c)

- Result
  ![image](https://github.com/user-attachments/assets/baeb010f-f9ef-4e55-8401-4638aa2d3a1a)

#### Get Customer By Code
- Get Customer from SQL Accounting Database by Code
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Customers/GetCustomerByCode/{customerCode}
  ![image](https://github.com/user-attachments/assets/a834146f-748b-4912-8911-a924a9782877)

- Result:
  ![image](https://github.com/user-attachments/assets/864cff83-42e2-4c39-97c5-972afcced747)

#### Delete Customer
- Delete Customer from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Customers/DeleteCustomer/{customerCode}
  ![image](https://github.com/user-attachments/assets/6681e770-7a53-426c-a00f-b605c538a8d7)

- Result:
  ![image](https://github.com/user-attachments/assets/e91f81f8-09b1-45ad-94d8-147d23bf5c92)


### Item
#### Get All Items
- Get All Items from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/GetAllItems
  ![image](https://github.com/user-attachments/assets/54dbcb12-3336-486e-b3f5-bbc03899cd91)

- Result:
  ![image](https://github.com/user-attachments/assets/73369e0e-f519-4713-8db7-a912e71d661e)

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
  ![image](https://github.com/user-attachments/assets/9c06ca9b-7763-4039-9106-485768bfea9f)

- Result:
  ![image](https://github.com/user-attachments/assets/8b43a1a0-5dcb-4f90-801d-4367d87c8948)

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
  ![image](https://github.com/user-attachments/assets/c78a118c-02c8-4e8e-bbe0-c0e75ba73478)

- Result:
  ![image](https://github.com/user-attachments/assets/24c55f85-6a26-4a0c-846d-04b82186d444)

#### Get Item by ItemCode
- Get Item by ItemCode from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/GetItemByItemCode/{itemCode}
  ![image](https://github.com/user-attachments/assets/c9b6f7a1-978b-493f-8dfe-3420221c5f3b)

- Result:
  ![image](https://github.com/user-attachments/assets/83c2a248-50a2-42a0-961d-34c6822bee2c)

#### Delete Item
- Delete Item from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/DeleteItem/{itemCode}
  ![image](https://github.com/user-attachments/assets/63527e8b-b720-44ea-83c8-f34fe2c7cc32)

- Result:
  ![image](https://github.com/user-attachments/assets/5754277d-52d3-4212-8893-c6206ca0b268)

### SalesInvoice
#### Get All SalesInvoices
- Get all SalesInvoices from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/GetAllSalesInvoices
  ![image](https://github.com/user-attachments/assets/ed0375eb-fd0f-4417-87b8-1091c18347b4)

- Result:
  ![image](https://github.com/user-attachments/assets/ce64d7b3-3659-426c-b0df-2067c04a866a)
  ![image](https://github.com/user-attachments/assets/b0ed6e7b-9278-4706-b8ad-439e8d38a878)

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
  ![image](https://github.com/user-attachments/assets/c9a3047c-db4a-4590-a57c-947f29e24417)

- Result:
  ![image](https://github.com/user-attachments/assets/d6aa2701-6d78-467b-9eff-d93e32575ef0)
  ![image](https://github.com/user-attachments/assets/b629d1f5-3bb0-421f-b398-6a06b542016d)

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
  ![image](https://github.com/user-attachments/assets/818adb71-954f-4b81-9ca1-b624c8fda122)

- Result
  ![image](https://github.com/user-attachments/assets/634e2b4d-f04c-499e-bc2e-9bbaf48836fc)
  ![image](https://github.com/user-attachments/assets/d2a187b8-f481-4fb3-9d64-e47d0035387b)

#### Get SalesInvoice by InvoiceNo
- Get SalesInvoice by InvoiceNo from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/GetSalesInvoiceByDocNo/INV-20250613-001
  ![image](https://github.com/user-attachments/assets/9e6c6bf6-68ff-4143-a3bb-0ec596678bb6)

- Result:
  ![image](https://github.com/user-attachments/assets/9f804737-defc-42f6-9401-7b35a8aadbdc)
  ![image](https://github.com/user-attachments/assets/39d17f3f-b559-4a97-8758-8d656db4a608)

#### Delete SalesInvoice
- Delete SalesInvoice in SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/DeleteSalesInvoice/{invoiceNo}
  ![image](https://github.com/user-attachments/assets/9dee9966-6897-444a-9ded-c2e2b2ddfaea)

- Result:
  ![image](https://github.com/user-attachments/assets/fa3ad7c6-e096-4682-a7c1-aea7013a31ff)
