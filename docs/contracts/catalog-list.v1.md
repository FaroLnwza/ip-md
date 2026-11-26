# API รายการสินค้า
สถานะ: PROPOSED
รุ่น: v1
เจ้าของข้อเสนอ: Microservice

คำขอ: GET /api/v1/catalog/products
Request body: ไม่ส่ง
Query: available เลือกใส่ได้ รับ true หรือ false

## โครงสร้างข้อมูล (Fields)
- `id` : `string` (รหัสสินค้า เช่น "pen", "notebook", "eraser")
- `name` : `string` (ชื่อสินค้า)
- `priceSatang` : `number` (ราคาสินค้า หน่วยเป็นสตางค์)
- `available` : `boolean` (สถานะความพร้อมขาย true / false)

## ชุดข้อมูลตัวอย่าง (3 รายการ)
1. id: "pen", name: "ปากกาสีน้ำเงิน", priceSatang: 2500, available: false
2. id: "notebook", name: "สมุดบันทึก", priceSatang: 12900, available: true
3. id: "eraser", name: "ยางลบ", priceSatang: 800, available: true

## Query และผลลัพธ์ที่คาด (Status & Response)
- **(ไม่ระบุ Query)** -> Status `200` : แสดงสินค้าทั้งหมด 3 รายการ (pen, notebook, eraser)
- **`?available=true`** -> Status `200` : ได้เฉพาะสินค้าที่พร้อมขาย 2 รายการ (notebook, eraser)
- **`?available=true`** -> Status `200` : ได้เฉพาะสินค้าที่พร้อมขาย 1 รายการ (eraser)
- **`?available=false`** -> Status `200` : ได้เฉพาะสินค้าที่ไม่พร้อมขาย 1 รายการ (pen)


