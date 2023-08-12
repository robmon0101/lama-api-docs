# LAMA API DOCUMENTATION

## Navigate
# [Xero](xero.md)
# [Clients](client.md)

---
## Xero Sync
*POST **/v2/xero/sync***

#### Parameters
* **model** - required string
    * Valid values are:
        * employee
        * timesheet
        * client
        * invoice

#### Sample Request
```bash
curl --location --request POST 'https://<site>/v2/xero/sync' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <token>' \
--data-raw '{
   "model": "employee
'
```

#### Response - Success
```json
{
    'sync': 'completed',
    'data': {
        'success': [], # IDs of successful documents
        'error': [] # IDs of failed documents
    },
    'status': 'success',
    'message': '<success message>'
}
```

#### Response - Error
```json
{
    'sync': 'failed',
    'data': null,
    'status': 'error',
    'message': '<error message>'
}
```

---
## Payroll Calendars
*GET **/v2/xero/payroll-calendars***

#### Sample Request
```bash
curl --location --request GET 'https://<site>/v2/xero/payroll-calendars' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <token>'
```

#### Response - Success
```json
{
    'data': <list of payroll calendar object>,
    'errors': null,
    'status_code': 200
}
```

---
## Payroll Calendar Object
* **id** - int
    * Unique ID
* **name** - string
    * Name
