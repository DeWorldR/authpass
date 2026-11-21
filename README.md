# AuthPass

ระบบยืนยันตัวตนด้วย JWT สร้างด้วย NestJS ไว้เป็นพื้นฐานของระบบ login ในโปรเจกต์อื่น

**Tech:** NestJS · TypeScript · MongoDB (Mongoose) · Passport-JWT · Argon2 · class-validator

## ฟีเจอร์
- สมัครสมาชิก รหัสผ่านถูก hash ด้วย Argon2 ก่อนบันทึก
- เข้าสู่ระบบแล้วได้ JWT กลับไป ตั้งอายุ token ได้จาก `.env`
- route ที่ต้อง login ป้องกันด้วย JWT Strategy ของ Passport

## API
| Method | Path | ใช้ทำอะไร |
|---|---|---|
| POST | `/auth/signup` | สมัครสมาชิก |
| POST | `/auth/signin` | เข้าสู่ระบบ รับ JWT |
| GET | `/auth/profile` | ข้อมูลผู้ใช้ (ต้องแนบ Bearer token) |

## รันในเครื่อง
```bash
npm install
# .env
# MONGO_URI=mongodb://localhost:27017/authpass
# JWT_SECRET=<secret>
# JWT_EXPIRATION=1d
npm run start:dev
```
