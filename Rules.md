**Panduan Pengiriman dan Penarikan Data Menggunakan JSON**

Berikut adalah panduan untuk pengiriman dan penarikan data menggunakan format JSON pada layanan tertentu.

__Pengiriman Data (POST Request)__
1. **Authorization**
- Gunakan metode otentikasi Bearer Token.
- Header Authorization: __Bearer <token>__
2. **Endpoint Pengiriman Data**
- Gunakan metode HTTP __POST__.
- Endpoint: __http://example.com/api/purchase-order__ gunakan endpoint yang sesuai!
3. **Header Request**
- Atur header __Content-Type__ sebagai __application/json__.
- Atur header __Authorization__ sesuai dengan metode otentikasi yang telah dijelaskan.
4. **Format Data JSON**
Berikut ini adalah contoh data JSON dan Pastikan data JSON sesuai dengan kebutuhan layanan yang dituju.
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
5. **Contoh Request dengan cURL**
```
curl -X POST -H "Content-Type: application/json" -H "Authorization: Bearer <token>" -d '{"PurchaseOrder": {...}}' http://example.com/api/purchase-order
```

**Penarikan Data (GET Request)**
1. **Authorization**
- Gunakan metode otentikasi __Bearer Token__.
- Header Authorization: __Bearer <token>__
2. **Endpoint Penarikan Data**
- Gunakan metode HTTP __GET__.
- Endpoint: __http://api.panbrothers.co.id/PO__
3. **Header Request**
Atur header __Content-Type__ sebagai __application/json__.
Atur header Authorization sesuai dengan metode otentikasi yang telah dijelaskan.

4. **Contoh Request dengan cURL**
```
curl -X GET -H "Content-Type: application/json" -H "Authorization: Bearer <token>" http://example.com/api/purchase-order/123456
```
5. **Data JSON yang akan kamu terima**
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

Catatan:
- Pastikan untuk mengganti __<token>__ dengan token yang sesuai dan sesuaikan endpoint dan struktur data JSON dengan spesifikasi layanan yang diintegrasikan. Jika metode otentikasi atau endpoint berbeda, sesuaikan petunjuk tersebut dengan aturan API yang digunakan.
- Sesuaikan endpoint dan struktur data JSON dengan spesifikasi layanan yang diintegrasikan.
- Jika terdapat parameter seperti {PONumber}, pastikan untuk menggantinya dengan nilai yang benar.
- Pastikan endpoint dan kredensial sesuai dengan yang diberikan oleh penyedia layanan API.
- Pantau dokumentasi API untuk memastikan bahwa Anda mengikuti aturan dan batasan yang berlaku.