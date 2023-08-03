# LAMA API DOCUMENTATION

## Navigate
# [Xero APIs](xero.md)
# [Clients APIs](client.md)

---

## Xero Sync
*POST **/v2/xero/sync***

#### Parameters
* **model** - required string
    * Valid values are:
        * employee
        * timesheet
        * client - Ongoing development
        * invoice - Ongoing development

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