# LAMA API DOCUMENTATION

## Navigate
# [Xero APIs] (xero.md)

## Get all clients
*GET **/client?page=client-list

#### Parameters
* **assigned_employee** - required employee_id
* **page** - required string
    * Valid value: client-list

#### Sample Request
```bash
curl --location --request POST 'https://<site>/client?page=client-list&assigned_employee=219' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <token>' \
```
