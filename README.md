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
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454645671-0505358a-3986-4340-b85f-372c46116135.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T135911Z&X-Amz-Expires=300&X-Amz-Signature=41e615f61fdf9264c2faa6cbcb326c078cc350cacf1dcfe7fd3999ff1f325e55&X-Amz-SignedHeaders=host" >

Result:
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454645750-b72ed892-6122-4618-87d0-4e6a5c23c4ae.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T140156Z&X-Amz-Expires=300&X-Amz-Signature=33c1563e7a48b8eaa8514d22dffefcd235f709670bd57322e057f62c10c3d472&X-Amz-SignedHeaders=host">

#### Attach the JWT Bearer Token for each API request
<img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454646060-45aafc9d-3ac1-4a63-a299-89753bbce691.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T140234Z&X-Amz-Expires=300&X-Amz-Signature=2f3c3a45abde8bf17f128d19e272e74a91d627779b766dceb7ddcbbb739b0794&X-Amz-SignedHeaders=host">


### Customer
#### Get All Customers
- Get All Customers from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Customers/GetAllCustomers
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454648046-98bee8b5-917a-4d31-8ea0-8bea60fcb83e.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T140331Z&X-Amz-Expires=300&X-Amz-Signature=3a57db8bd33ecaaa8beacbd4abc12f81179ec5eddddd040e7402489d3c649042&X-Amz-SignedHeaders=host">

- Result:
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454648152-43ce899e-8d59-42fa-b50d-5257697d45af.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T140554Z&X-Amz-Expires=300&X-Amz-Signature=ba91c1dc760d252e918ed5c1d2eaab4d1d6f9778bf8d34eef087c8741c996a18&X-Amz-SignedHeaders=host">

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
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454655688-e0e3013f-47b5-4027-af46-a566099ada04.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T140706Z&X-Amz-Expires=300&X-Amz-Signature=a46c27a591b5c682a3b210360a57caeba93f617b54004a4bc2858f8001436acc&X-Amz-SignedHeaders=host">

- Result:
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454656559-095bbe4b-3401-4ed3-9199-f1c514af4494.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T140801Z&X-Amz-Expires=300&X-Amz-Signature=03ada1086b6a07abc78370847b3e8e5a782ddacf64517c20973d8959fed8a60b&X-Amz-SignedHeaders=host">

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
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454658039-864cff83-42e2-4c39-97c5-972afcced747.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141052Z&X-Amz-Expires=300&X-Amz-Signature=09866116df3de7d73d70e5ebe99ea88eceab16b8cf99e0ee324f2fd902491c52&X-Amz-SignedHeaders=host">
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
  ![image](https://github.com/user-attachments/assets/f0cb057b-f971-4d06-a38d-51c519905af5)

- Result:
  ![image](https://github.com/user-attachments/assets/4aa8ba7b-f026-4469-980e-52d6dfff811c)

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
  ![image](https://github.com/user-attachments/assets/d8b6a3cd-e593-4b65-b488-9c988ef08e7c)

- Result:
  ![image](https://github.com/user-attachments/assets/89de4fcb-7069-41d1-9ac3-2733b9aca289)

#### Get Item by ItemCode
- Get Item by ItemCode from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/GetItemByItemCode/{itemCode}
  ![image](https://github.com/user-attachments/assets/f96b4871-13b9-4e8e-bff8-03ebf33d1c2f)

- Result:
  ![image](https://github.com/user-attachments/assets/a88de8bc-8999-4a8f-a352-b12da4e196a7)

#### Delete Item
- Delete Item from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/Items/DeleteItem/{itemCode}
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454671817-63527e8b-b720-44ea-83c8-f34fe2c7cc32.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141518Z&X-Amz-Expires=300&X-Amz-Signature=4d04394e484248ece2999f6f08e5b3b73f52e04da728e67b3f456054d2db621f&X-Amz-SignedHeaders=host">

- Result:
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454671855-5754277d-52d3-4212-8893-c6206ca0b268.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141536Z&X-Amz-Expires=300&X-Amz-Signature=247ae211459eecf9db1890716e24ecfd85ba39b29d5ecf722eb57862d6bdc9c1&X-Amz-SignedHeaders=host">

### SalesInvoice
#### Get All SalesInvoices
- Get all SalesInvoices from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/GetAllSalesInvoices
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454673264-ed0375eb-fd0f-4417-87b8-1091c18347b4.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141554Z&X-Amz-Expires=300&X-Amz-Signature=d66409c61254a09d623211788692a137df63fb0373b349e7ad692235a935d9b5&X-Amz-SignedHeaders=host">

- Result:
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454673718-ce64d7b3-3659-426c-b0df-2067c04a866a.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141612Z&X-Amz-Expires=300&X-Amz-Signature=d88dedb5858f56282b53611762590544043138280ebdb7aa9b19f1bb3fca339f&X-Amz-SignedHeaders=host">
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454673775-b0ed6e7b-9278-4706-b8ad-439e8d38a878.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141630Z&X-Amz-Expires=300&X-Amz-Signature=bec4fd3caf05be6add4801b6ad46b2360a848675122d76b05dc174d0d920656d&X-Amz-SignedHeaders=host">

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
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454687550-c9a3047c-db4a-4590-a57c-947f29e24417.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141659Z&X-Amz-Expires=300&X-Amz-Signature=d0bad271d7e1b1f1f3d49648e9a0525ba232b0cb27505640f40e1ea91dd36566&X-Amz-SignedHeaders=host">

- Result:
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454687663-d6aa2701-6d78-467b-9eff-d93e32575ef0.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141719Z&X-Amz-Expires=300&X-Amz-Signature=cc422df30cb8a75e493bce6c886719870fdb0d8898e3539b75bac745855adda9&X-Amz-SignedHeaders=host">
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454687777-b629d1f5-3bb0-421f-b398-6a06b542016d.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141737Z&X-Amz-Expires=300&X-Amz-Signature=7f7beca2d3e2892d4baa1324ad774c87b842ac322e7c52067a59c3690a4df437&X-Amz-SignedHeaders=host">

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
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454689172-818adb71-954f-4b81-9ca1-b624c8fda122.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141810Z&X-Amz-Expires=300&X-Amz-Signature=72cd5139aca3d12c3d40b6bce25e30937049e7507a94e44416a6c8bc62a875a3&X-Amz-SignedHeaders=host">

- Result
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454688354-634e2b4d-f04c-499e-bc2e-9bbaf48836fc.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141830Z&X-Amz-Expires=300&X-Amz-Signature=8e5aa83546767a9d51d2d64d874c750a5dc8e9f826643b5f47c2cc23f5199f59&X-Amz-SignedHeaders=host">
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454688476-d2a187b8-f481-4fb3-9d64-e47d0035387b.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141845Z&X-Amz-Expires=300&X-Amz-Signature=8ec8cb8c4eb808a021c225cdd4baba17c74250557baa02a371fb47eb09648763&X-Amz-SignedHeaders=host">

#### Get SalesInvoice by InvoiceNo
- Get SalesInvoice by InvoiceNo from SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/GetSalesInvoiceByDocNo/INV-20250613-001
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454689471-9e6c6bf6-68ff-4143-a3bb-0ec596678bb6.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141904Z&X-Amz-Expires=300&X-Amz-Signature=07c48abab87dc22684aa5095de8c1ef4cf6c1325c00ad4d298a72cc3df943411&X-Amz-SignedHeaders=host">

- Result:
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454689561-9f804737-defc-42f6-9401-7b35a8aadbdc.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141923Z&X-Amz-Expires=300&X-Amz-Signature=7172b8b2a1f9ce9e58558751eefae0699e812120dfb37a79a24c560c2df5c7f0&X-Amz-SignedHeaders=host">
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454689679-39d17f3f-b559-4a97-8758-8d656db4a608.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141938Z&X-Amz-Expires=300&X-Amz-Signature=09e3ddd69acfcdff564c6fbd5d1baeb6e098e98dbb20aed35f0695c8519902c2&X-Amz-SignedHeaders=host">

#### Delete SalesInvoice
- Delete SalesInvoice in SQL Accounting Database
- Call API endpoint => https://dingdon-sql.ddns.net:2211/api/SalesInvoices/DeleteSalesInvoice/{invoiceNo}
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454685698-9dee9966-6897-444a-9ded-c2e2b2ddfaea.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T141958Z&X-Amz-Expires=300&X-Amz-Signature=854452053a78801dfa04d7c6f2799db9cedbe6ac79559abe8c64f87ab16c3b51&X-Amz-SignedHeaders=host">

- Result:
  <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/183855054/454685761-fa3ad7c6-e096-4682-a7c1-aea7013a31ff.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250613%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250613T142014Z&X-Amz-Expires=300&X-Amz-Signature=ffe71a6e7a4b4d4b0e7877e5b716e69e790bde54f887f9374ab0747abc0a2f21&X-Amz-SignedHeaders=host">
