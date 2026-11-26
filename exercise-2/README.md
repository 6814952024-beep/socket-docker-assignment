# Socket API & Docker Assignment (Exercise 1 & 2)

- ชื่อ-นามสกุล: [ใส่ชื่อของคุณ]
- รหัสนักศึกษา: [ใส่รหัสนักศึกษา]

---

## Exercise 1: Chat (1 Server + 2 Clients)

ระบบแชตด้วย TCP Socket และ threading โดย Server รับการเชื่อมต่อจาก Client 2 ตัว
และส่งต่อ (broadcast) ข้อความที่ได้รับให้ Client อื่น รันบน Docker Compose

### วิธีรัน
```bash
cd exercise-1
docker compose up --build
docker exec -it chat_client1 bash    # แล้วรัน python client.py
docker exec -it chat_client2 bash    # แล้วรัน python client.py
docker compose down
```

### ผลลัพธ์
รัน container ทั้งหมด
![up](screenshots/ex1-01-up.png)

รายการ container
![ps](screenshots/ex1-02-ps.png)

แชตระหว่าง Client 1 และ Client 2
![chat](screenshots/ex1-03-chat.png)

Log ของ Server
![server log](screenshots/ex1-04-server-log.png)

ปิด container
![down](screenshots/ex1-05-down.png)

---

## Exercise 2: Flask Web App + Socket Server

หน้าเว็บ Flask รับข้อความผ่านฟอร์ม (POST) แล้วทำหน้าที่เป็น socket client
ส่งไปยัง socket server ซึ่งตอบกลับแบบ Echo และแสดงผลบนหน้าเว็บ

### วิธีรัน
```bash
cd exercise-2
docker compose up --build
# เปิดเบราว์เซอร์ที่ http://localhost:5000
docker compose down
```

### ผลลัพธ์
รัน container ทั้งหมด
![up](screenshots/ex2-01-up.png)

หน้าฟอร์ม
![form](screenshots/ex2-02-form.png)

ผลลัพธ์หลังกด Send
![result](screenshots/ex2-03-result.png)

Log ของ Socket Server
![server log](screenshots/ex2-04-server-log.png)

---

## วิธีหยุดการทำงาน
รัน `docker compose down` ในโฟลเดอร์ที่มีไฟล์ docker-compose.yml