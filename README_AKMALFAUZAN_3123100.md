
# 🔔 Backend Alarm Sederhana

## 📖 Deskripsi
Backend ini bertanggung jawab atas logika alarm, termasuk penjadwalan, pengelolaan data alarm, dan notifikasi pengguna.

---

## 🎯 Fitur Utama
✅ **Penjadwalan Alarm** – Menggunakan `AlarmManager` atau `WorkManager` untuk memastikan alarm berbunyi tepat waktu.  
✅ **Penyimpanan Data** – Menyimpan konfigurasi alarm menggunakan `SharedPreferences` atau database `Room`.  
✅ **Notifikasi** – Mengirimkan notifikasi saat alarm aktif, dengan dukungan suara dan getaran.  
✅ **Optimasi Performa** – Memastikan alarm berjalan efisien tanpa menguras baterai perangkat.  

---

## ⚙️ Struktur Proyek

---

## 🛠 Implementasi Backend
### **📌 1. Penjadwalan Alarm**
Gunakan `AlarmManager` untuk mengatur alarm berdasarkan waktu yang dipilih:
```java
AlarmManager alarmManager = (AlarmManager) getSystemService(Context.ALARM_SERVICE);
PendingIntent pendingIntent = PendingIntent.getBroadcast(this, 0, new Intent(this, AlarmReceiver.class), PendingIntent.FLAG_UPDATE_CURRENT);

Calendar calendar = Calendar.getInstance();
calendar.set(Calendar.HOUR_OF_DAY, selectedHour);
calendar.set(Calendar.MINUTE, selectedMinute);
calendar.set(Calendar.SECOND, 0);

alarmManager.setExact(AlarmManager.RTC_WAKEUP, calendar.getTimeInMillis(), pendingIntent);

Tentu, berikut adalah storyboard dan README untuk bagian backend dengan tema alarm sederhana:

---

## **Storyboard Backend Alarm Sederhana**

### **1. Pendahuluan**
Sistem alarm ini akan berjalan di backend, memungkinkan pengguna untuk mengatur dan mengelola alarm sederhana melalui API.

### **2. Fitur Utama**
- **Menambahkan alarm**: Pengguna dapat mengatur alarm dengan waktu tertentu.
- **Menghapus alarm**: Alarm dapat dihapus sebelum waktunya berbunyi.
- **Menampilkan daftar alarm**: API menyediakan daftar alarm yang telah diatur.
- **Notifikasi**: Alarm akan berbunyi atau memberikan notifikasi pada waktu yang telah ditentukan.

### **3. Alur Kerja**
1. **Pengguna mengirim permintaan** untuk menambahkan alarm dengan waktu yang diinginkan.
2. **Backend menyimpan data alarm** dalam database.
3. **Sistem pengecekan berkala** akan menjalankan tugas untuk memeriksa apakah ada alarm yang waktunya telah tiba.
4. **Jika waktu alarm tiba**, backend akan mengaktifkan notifikasi atau menjalankan aksi yang telah ditentukan.

---

## **README.md Backend Alarm Sederhana**

```md
# Backend Alarm Sederhana

Backend sederhana untuk mengelola alarm berdasarkan waktu yang telah diatur oleh pengguna.

## Fitur
- Menambahkan alarm
- Menghapus alarm
- Menampilkan daftar alarm
- Memberikan notifikasi ketika alarm berbunyi

## Instalasi
1. Clone repositori:
   ```
   git clone https://github.com/your-repo/backend-alarm.git
   cd backend-alarm
   ```
2. Install dependencies:
   ```
   npm install
   ```
3. Jalankan server:
   ```
   npm start
   ```

## API Endpoint
### **Menambahkan Alarm**
- **Endpoint**: `POST /alarm`
- **Body Request**:
  ```json
  {
    "time": "2025-05-21T08:00:00",
    "message": "Bangun pagi!"
  }
  ```

### **Menghapus Alarm**
- **Endpoint**: `DELETE /alarm/{id}`

### **Mendapatkan Daftar Alarm**
- **Endpoint**: `GET /alarm`
- **Response**:
  ```json
  [
    {
      "id": 1,
      "time": "2025-05-21T08:00:00",
      "message": "Bangun pagi!"
    }
  ]
  ```

## Teknologi
- Node.js
- Express.js
- Database (contoh: SQLite atau MongoDB)
- Cron Job untuk eksekusi alarm otomatis

Dengan semua fitur tambahan yang bisa diimplementasikan, sistem alarm ini bisa menjadi lebih dari sekadar pengingat waktu—ia bisa menjadi asisten pribadi yang membantu pengguna dalam aktivitas sehari-hari. Jika kamu ingin mengembangkan proyek ini lebih lanjut, aku siap membantu dalam menyusun arsitektur, kode, atau dokumentasi tambahan! 


