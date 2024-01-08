Panduan Pengiriman dan Penarikan Data Menggunakan JSON
Berikut adalah panduan untuk pengiriman dan penarikan data menggunakan format JSON pada layanan tertentu.

Pengiriman Data (POST Request)
1. Authorization
Gunakan metode otentikasi Basic Authentication.
Header Authorization: Basic <base64-encoded-credentials>
2. Endpoint Pengiriman Data
Gunakan metode HTTP POST.
Endpoint: http://example.com/api/purchase-order
3. Header Request
Atur header Content-Type sebagai application/json.
Atur header Authorization sesuai dengan metode otentikasi yang telah dijelaskan.
4. Format Data JSON
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
5. Contoh Request dengan cURL
```
curl -X GET -H "Content-Type: application/json" -H "Authorization: Basic <base64-encoded-credentials>" http://example.com/api/purchase-order/123456
```

Catatan:
Pastikan untuk mengganti <base64-encoded-credentials> dengan kredensial yang sesuai.
Sesuaikan endpoint dan struktur data JSON dengan spesifikasi layanan yang diintegrasikan.
Jika terdapat parameter seperti {PONumber}, pastikan untuk menggantinya dengan nilai yang benar.
Pastikan endpoint dan kredensial sesuai dengan yang diberikan oleh penyedia layanan API.
Pantau dokumentasi API untuk memastikan bahwa Anda mengikuti aturan dan batasan yang berlaku.