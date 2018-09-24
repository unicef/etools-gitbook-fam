# Interaction with VISION

One of the important aspects is the proper application data synchronization with the external services.

For this purposes in case of Financial Assurance module were added fetching Purchase Orders from VISION. 

VISION is external database maintained by UNICEF and used by different services. When Purchase Order Number is prompted, while creating new Engagement, backend is trying to find it inside the database. If no such record exists, the VISION will be used additionally and in case of success entity will be synchronized into the database. 

![](../.gitbook/assets/image%20%283%29.png)

VISION url to perform the purchase orders synchronization  
`https://devapis.unicef.org/BIService/BIWebService.svc/GetPurchaseOrderInfo_JSON/<vendor_number>`

Example response:

```javascript
[
  {
    'PURCHASING_ORG_CODE': '1234',
    'PURCHASING_GROUP_CODE': '123',
    'PURCHASING_GROUP_NAME': 'Belem, Brazil',
    'PLANT_CODE': '12345',
    'VENDOR_CODE': '123456789',
    'VENDOR_NAME': 'SAMPLE VENDOR EXAMPLE, LLC',
    'VENDOR_CTRY_NAME': 'Brazil',
    'GRANT_REF': 'AA000000000',
    'EXPIRY_DATE': '\\/Date(7654321000000)\\/',
    'DONOR_NAME': 'Example-Brazil',
    'PREQ_NO': '000000000',
    'PREQ_ITEM': 30,
    'PREQ_QTY': 1,
    'SO_NUMBER': '000',
    'PO_NUMBER': '1234567890',
    'PO_ITEM': 30,
    'PO_TYPE': 'ZLCO',
    'PO_DATE': '\\/Date(0123456700000)\\/',
    'PO_ITEM_QTY': 1,
    'CURRENCY_CODE': 'BRL',
    'AMOUNT_CURR': 21,
    'AMOUNT_USD': 42,
    'MATERIAL_CODE': 'Unknown',
    'MATERIAL_DESC': 'Unknown',
    'CREATE_DATE': '\\/Date(1351742400000)\\/',
    'UPDATE_DATE': '\\/Date(1404964800000)\\/'
  }
]
```

Fields mapping:

```text
'purchase_order': {
    "order_number": "PO_NUMBER",
    "contract_start_date": "PO_DATE",
    "auditor_firm": "VENDOR_CODE",
},
'order_item': {
    "number": "PO_ITEM",
    "purchase_order": "PO_NUMBER",
},
'auditor_firm': {
    "vendor_number": "VENDOR_CODE",
    "name": "VENDOR_NAME",
    "country": "VENDOR_CTRY_NAME",
},
'grant': {
    "name": "GRANT_REF",
    "expiry": "EXPIRY_DATE",
    "donor": "DONOR_NAME"
},
'donor': {
    "name": "DONOR_NAME",
}
```

