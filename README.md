# KPS App Portal — GitHub Pages

หน้า GitHub Pages สำหรับใช้เป็นลิงก์สั้น/ลิงก์กลางเข้าสู่  
**KPS App Portal — โรงพยาบาลกำแพงแสน**

ปลายทาง Google Apps Script Web App:



## วิธีติดตั้ง

1. เข้า GitHub แล้วสร้าง Repository ใหม่ เช่น `kps-app-portal`
2. เลือก Public (GitHub Pages สำหรับ Free account ใช้ง่ายที่สุด)
3. Upload ไฟล์ `index.html` นี้ไปไว้ที่ root ของ Repository
4. ไปที่ **Settings → Pages**
5. ที่ **Build and deployment**
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/ (root)`
6. กด Save
7. รอประมาณ 1–3 นาที

GitHub จะให้ URL ประมาณ:

`https://USERNAME.github.io/kps-app-portal/`

เมื่อเปิด URL นี้ ระบบจะ Redirect ไปยัง Google Apps Script Web App โดยอัตโนมัติ

## การเปลี่ยน URL ปลายทาง

หากมีการ Deploy Google Apps Script ใหม่แล้ว URL `/exec` เปลี่ยน  
ให้แก้ URL ใน `index.html` ทั้ง 3 จุด:

- `meta http-equiv="refresh"`
- `link rel="canonical"`
- `window.location.replace(...)`

## ความปลอดภัย

ไฟล์ GitHub Pages นี้ **ไม่มี**
- SUPABASE_KEY
- ADMIN_PASS
- PASSWORD_SECRET

Secret ทั้งหมดควรเก็บไว้ใน Google Apps Script → Project Settings → Script Properties เท่านั้น

## หมายเหตุ

GitHub Pages ทำหน้าที่เป็นหน้าเข้า/Redirect เท่านั้น  
ตัวระบบจริงยังทำงานบน Google Apps Script + Supabase
