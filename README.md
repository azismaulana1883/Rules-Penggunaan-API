**API Data Submission and Retrieval Guide**

This guide provides instructions for submitting and retrieving data using the JSON format for a specific service.

__Data Submission (POST Request)__
1. **Authorization**
- Use the Bearer Token authentication method.
- Authorization Header: __Bearer <token>__
2. **Data Submission Endpoint**
- Use the HTTP __POST__ method.
- Endpoint: __http://your-api.com/api/purchase-order__ (replace with the appropriate endpoint)
3. **Request Header**
- Set the __Content-Type__ header to __application/json__.
- Set the __Authorization__ header according to the authentication method described.
4. **JSON Data Format**
Below is an example of JSON data, and ensure that the JSON data aligns with the requirements of the intended service.
```
{
  "PurchaseOrder": {
    "POPurpose": "PO Creation",
    "PONumber": "123456",
    "POVersionNumber": "1",
    "POResponseVersionNumber": "0",
    "messageGenerationDateTime": "2024-01-08T12:00:00",
    "latestUpdateDateTime": "2024-01-08T12:00:00",
    "originalPOIssueDate": "2024-01-01",
    "currency": "USD",
    "paymentTerms": "TT60",
    "headerRemarks": "This is a sample remark",
    "sender": {
      "senderName": "PT. PRIMA SEJATI SEJAHTERA",
      "senderPerson": "John Doe"
    },
    "recipient": "Vendor XYZ",
    "buyer": {
      "buyerName": "Company ABC",
      "buyerAddressLine1": "123 Main Street",
      "buyerCountryCode": "ID",
      "buyerContactEmail": "buyer@example.com"
    },
    "sellerName": "Vendor XYZ",
    "actualManufacturer": {
      "actualManufacturerCode": "123",
      "actualManufacturerName": "Vendor XYZ",
      "actualManufacturerAddressLine1": "456 Manufacturer Street",
      "actualManufacturerCountryCode": "US"
    },
    "shipTo": {
      "shipToCode": "789",
      "shipToName": "Ship To XYZ",
      "shipToAddressLine1": "789 Shipping Street"
    },
    "T1Customer": "GroupMkt123",
    "headerExtension": null,
    "lineItems": [
      {
        "lineItemNumber": 1,
        "adidasOrderNumber": "A123",
        "adidasArticleNumber": "ART-456",
        "adidasWorkingNumber": "WORK-789",
        "requestDate": "2024-01-15",
        "adidasRequestDate": "2024-01-10",
        "adidasPlanDate": "2024-01-20",
        "priorityAndOrderType": "High - Retail",
        "orderQty": 100,
        "orderUOM": "PCS",
        "season": "Spring",
        "materialReferenceNumber": "MAT-123",
        "materialDescriptor": {
          "materialDescription": "Sample Material",
          "materialColor": "Blue"
        },
        "unitPrice": 10.50,
        "lineExtension1": null,
        "lineExtension2": "Additional Info",
        "lineExtension3": null,
        "lineExtension4": null,
        "lineExtension5": null
      }
    ]
  }
}
```
5. **Example Request using cURL**
```
curl -X POST -H "Content-Type: application/json" -H "Authorization: Bearer <token>" -d '{"PurchaseOrder": {...}}' http://example.com/api/purchase-order
```

**Data Retrieval (GET Request)**
1. **Authorization**
- Use Bearer Token authentication method.
- Authorization Header: __Bearer <token>__
2. **Data Retrieval Endpoint**
- Utilize HTTP __GET__ method.
- Endpoint: __http://api.panbrothers.co.id/PO__
3. **Request Header**
Set the __Content-Type__ header to __application/json__.
Set the Authorization header according to the authentication method described earlier.

4. **Example Request using cURL**
```
curl -X GET -H "Content-Type: application/json" -H "Authorization: Bearer <token>" http://example.com/api/purchase-order/123456
```
5. **JSON Data Format Received**
```
{
  "PurchaseOrder": {
    "POPurpose": "PO Creation",
    "PONumber": "123456",
    "POVersionNumber": "1",
    "POResponseVersionNumber": "0",
    "messageGenerationDateTime": "2024-01-08T12:00:00",
    "latestUpdateDateTime": "2024-01-08T12:00:00",
    "originalPOIssueDate": "2024-01-01",
    "currency": "USD",
    "paymentTerms": "TT60",
    "headerRemarks": "This is a sample remark",
    "sender": {
      "senderName": "PT. PRIMA SEJATI SEJAHTERA",
      "senderPerson": "John Doe"
    },
    "recipient": "Vendor XYZ",
    "buyer": {
      "buyerName": "Company ABC",
      "buyerAddressLine1": "123 Main Street",
      "buyerCountryCode": "ID",
      "buyerContactEmail": "buyer@example.com"
    },
    "sellerName": "Vendor XYZ",
    "actualManufacturer": {
      "actualManufacturerCode": "123",
      "actualManufacturerName": "Vendor XYZ",
      "actualManufacturerAddressLine1": "456 Manufacturer Street",
      "actualManufacturerCountryCode": "US"
    },
    "shipTo": {
      "shipToCode": "789",
      "shipToName": "Ship To XYZ",
      "shipToAddressLine1": "789 Shipping Street"
    },
    "T1Customer": "GroupMkt123",
    "headerExtension": null,
    "lineItems": [
      {
        "lineItemNumber": 1,
        "adidasOrderNumber": "A123",
        "adidasArticleNumber": "ART-456",
        "adidasWorkingNumber": "WORK-789",
        "requestDate": "2024-01-15",
        "adidasRequestDate": "2024-01-10",
        "adidasPlanDate": "2024-01-20",
        "priorityAndOrderType": "High - Retail",
        "orderQty": 100,
        "orderUOM": "PCS",
        "season": "Spring",
        "materialReferenceNumber": "MAT-123",
        "materialDescriptor": {
          "materialDescription": "Sample Material",
          "materialColor": "Blue"
        },
        "unitPrice": 10.50,
        "lineExtension1": null,
        "lineExtension2": "Additional Info",
        "lineExtension3": null,
        "lineExtension4": null,
        "lineExtension5": null
      }
    ]
  }
}
```

Note:
- Replace __<token>__ with the appropriate token and adjust the endpoint and JSON data structure according to the specifications of the target service.
- If there are parameters like {PONumber}, make sure to replace them with the correct values.
- Ensure that the endpoint and credentials are in line with the ones provided by the API service.
- Monitor the API documentation to ensure that you adhere to the applicable rules and limitations.u.