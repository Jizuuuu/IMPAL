# TUBES-IMPAL

**Eling – Smart Daily Reminder App**

## Daftar Isi

- [Deskripsi Aplikasi](#deskripsi-aplikasi)
- [Fitur Utama Sistem](#fitur-utama-sistem)
- [Pemilihan Teknologi](#pemilihan-teknologi)
- [Controlling Works](#controlling-works)

---

## Deskripsi Aplikasi

Eling adalah aplikasi mobile yang digunakan untuk membantu pengguna mengelola dan mengingat berbagai aktivitas sehari-hari. Aplikasi ini dirancang sebagai pengingat digital yang memungkinkan pengguna membuat, mengatur, dan menerima notifikasi untuk aktivitas yang perlu dilakukan pada waktu tertentu, seperti jadwal kuliah, mengerjakan tugas, minum obat, rapat, berolahraga, maupun aktivitas pribadi lainnya.

Melalui aplikasi ini, pengguna dapat membuat reminder secara manual dengan menentukan aktivitas, tanggal, waktu, kategori, serta pengulangan reminder. Sistem kemudian akan menyimpan reminder dan menjadwalkan alarm atau notifikasi sesuai dengan waktu yang telah ditentukan. Pengguna juga dapat mengubah, menghapus, menunda (snooze), maupun menandai reminder sebagai selesai.

Sebagai fitur tambahan, Eling memanfaatkan teknologi **Speech-to-Text** untuk memungkinkan pengguna membuat reminder menggunakan suara. Suara pengguna akan dikonversi menjadi teks yang kemudian dapat diproses oleh sistem. Pengguna dapat memeriksa dan mengubah hasil transkripsi sebelum digunakan untuk membuat reminder.

Eling juga menyediakan fitur **AI Reminder Assistant** yang menggunakan Google Gemini API untuk membantu memahami input pengguna dalam bahasa natural. Pengguna dapat memberikan perintah seperti *"Besok jam 7 pagi ingatkan saya untuk mengerjakan tugas pemrograman"*, kemudian AI membantu mengidentifikasi informasi seperti aktivitas, tanggal, waktu, dan pengulangan. 

Hasil pemrosesan AI akan ditampilkan terlebih dahulu kepada pengguna dalam bentuk preview sebelum reminder disimpan.

AI pada Eling berfungsi sebagai fitur pendukung dalam proses pembuatan reminder. Data reminder yang telah dikonfirmasi pengguna tetap dikelola oleh sistem, sedangkan alarm, notifikasi, penyimpanan data, pengaturan reminder, serta proses perubahan dan penghapusan reminder dikendalikan oleh aplikasi.

---

## Fitur Utama Sistem

1. **Manajemen Reminder**  
   Sistem pengelolaan reminder yang memungkinkan pengguna membuat, melihat, mengubah, dan menghapus pengingat. Pengguna dapat menentukan aktivitas, tanggal, waktu, kategori, serta pengulangan reminder sesuai kebutuhan.

2. **Alarm & Notifikasi**  
   Sistem memberikan alarm atau notifikasi kepada pengguna ketika waktu reminder telah tiba. Pengguna dapat melihat aktivitas yang harus dilakukan melalui notifikasi, melakukan snooze, maupun menandai reminder sebagai selesai.

3. **Reminder Berulang**  
   Sistem menyediakan pengaturan reminder berulang untuk aktivitas yang dilakukan secara rutin. Pengguna dapat menentukan pengulangan seperti setiap hari, hari tertentu, mingguan, maupun pengaturan pengulangan lainnya.

4. **Speech-to-Text**  
   Fitur yang memungkinkan pengguna membuat reminder menggunakan suara. Sistem mengubah suara pengguna menjadi teks menggunakan layanan Speech-to-Text. Hasil transkripsi ditampilkan kepada pengguna sehingga dapat diperiksa atau diperbaiki sebelum diproses lebih lanjut.

5. **AI Reminder Assistant**  
   Fitur kecerdasan buatan yang membantu pengguna membuat reminder menggunakan bahasa natural. Pengguna dapat menuliskan atau memberikan perintah seperti *"Besok jam 8 pagi ingatkan saya untuk kuliah"*. AI kemudian membantu mengenali aktivitas, tanggal, waktu, dan pengulangan dari input tersebut.

6. **AI Reminder Preview**  
   Sistem menampilkan hasil pemrosesan AI sebelum reminder disimpan. Pengguna dapat memeriksa informasi yang telah dikenali, melakukan perubahan apabila diperlukan, kemudian memberikan konfirmasi untuk menyimpan reminder.

7. **Kategori Reminder**  
   Sistem menyediakan kategori untuk membantu pengguna mengelompokkan reminder berdasarkan jenis aktivitas, seperti Kuliah, Tugas, Pribadi, Kesehatan, Pekerjaan, dan Lainnya.

8. **Riwayat Reminder**  
   Sistem menyimpan riwayat aktivitas reminder sehingga pengguna dapat melihat reminder yang telah selesai maupun reminder yang terlewat.

9. **Pencarian Reminder**  
   Pengguna dapat mencari reminder berdasarkan kata kunci dan melihat reminder berdasarkan kategori tertentu.

10. **Pengaturan Reminder & Notifikasi**  
    Pengguna dapat mengatur preferensi notifikasi, suara alarm, getaran, serta durasi snooze sesuai kebutuhan.

---

## Pemilihan Teknologi

Tim pengembang aplikasi ini terdiri dari mahasiswa, sehingga faktor kepraktisan menjadi pertimbangan utama dalam menentukan teknologi yang digunakan. Setiap teknologi dipilih dengan mempertimbangkan kemudahan dalam proses pengembangan, integrasi antar komponen sistem, serta kemudahan pemeliharaan aplikasi di kemudian hari.

### A. UI/UX & Prototyping

- **Tools:** Figma
- **Justifikasi:** Figma digunakan untuk merancang tampilan dan pengalaman pengguna aplikasi Eling, mulai dari wireframe, prototype, style guide, hingga komponen antarmuka. Perancangan dilakukan terlebih dahulu agar struktur navigasi dan tampilan setiap halaman dapat ditentukan sebelum masuk ke tahap implementasi aplikasi.

### B. Mobile Application

- **Framework:** Flutter
- **Bahasa Pemrograman:** Dart
- **Justifikasi:** Flutter digunakan sebagai framework utama untuk membangun aplikasi mobile Eling. Flutter memungkinkan tim mengembangkan antarmuka aplikasi secara terstruktur menggunakan satu basis kode. Dart digunakan sebagai bahasa pemrograman utama karena merupakan bahasa yang digunakan oleh Flutter dan mendukung pengembangan aplikasi mobile dengan baik.

Flutter juga memudahkan pembuatan komponen antarmuka yang konsisten serta mendukung integrasi dengan berbagai layanan seperti API, notifikasi lokal, mikrofon, dan layanan Speech-to-Text.

### C. Backend & REST API

- **Backend:** Supabase
- **API:** REST API
- **Justifikasi:** Supabase digunakan sebagai backend untuk menyediakan layanan basis data, autentikasi, serta akses data melalui API. Penggunaan Supabase membantu mengurangi kompleksitas pembangunan backend sehingga tim dapat lebih fokus pada pengembangan fitur utama aplikasi.

Komunikasi antara aplikasi Flutter dengan layanan backend dilakukan melalui API sehingga proses pengelolaan data pengguna dan reminder dapat dilakukan secara terstruktur.

### D. Basis Data

- **Database:** PostgreSQL
- **Platform:** Supabase
- **Justifikasi:** PostgreSQL digunakan sebagai basis data utama untuk menyimpan data pengguna, reminder, kategori, riwayat reminder, serta pengaturan pengguna. PostgreSQL dipilih karena memiliki struktur basis data relasional yang sesuai untuk mengelola hubungan antara pengguna dengan reminder dan data pendukung lainnya. Supabase menyediakan PostgreSQL sebagai layanan basis data sehingga pengelolaan database dapat dilakukan secara terintegrasi dengan backend aplikasi.

### E. Autentikasi

- **Authentication:** Supabase Auth
- **Justifikasi:** Supabase Auth digunakan untuk menangani proses registrasi, login, logout, serta autentikasi pengguna. Penggunaan layanan autentikasi ini membantu memastikan bahwa data reminder hanya dapat diakses oleh pengguna yang memiliki hak akses terhadap data tersebut.

### F. Kecerdasan Buatan (AI Engine)

- **LLM API:** Google Gemini API
- **Integrasi:** Aplikasi Eling melalui backend/API
- **Justifikasi:** Google Gemini API digunakan pada fitur **AI Reminder Assistant** sebagai fitur pendukung dalam proses pembuatan reminder.

Pengguna dapat memberikan input dalam bentuk bahasa natural, misalnya:

> "Besok jam 7 pagi ingatkan saya untuk mengerjakan tugas pemrograman."

AI kemudian membantu mengidentifikasi informasi yang terdapat dalam kalimat tersebut, seperti:

- aktivitas: mengerjakan tugas pemrograman;
- tanggal: 18-01-2027;
- waktu: 07.00;
- pengulangan: tidak ada.

Hasil pemrosesan AI tidak langsung menjadi reminder aktif. Sistem terlebih dahulu menampilkan hasil tersebut kepada pengguna dalam bentuk preview. Pengguna dapat melakukan perubahan apabila terdapat informasi yang kurang tepat dan kemudian melakukan konfirmasi sebelum reminder disimpan.

AI hanya berperan dalam memahami input pengguna. Informasi reminder yang telah dikonfirmasi, penyimpanan data, pengaturan alarm, notifikasi, serta pengelolaan reminder tetap dikendalikan oleh sistem.

### G. Speech-to-Text

- **Teknologi:** Speech-to-Text API/Service
- **Integrasi:** Flutter
- **Justifikasi:** Speech-to-Text digunakan untuk mengubah suara pengguna menjadi teks. Fitur ini memungkinkan pengguna membuat reminder tanpa harus mengetik secara manual.

Contoh penggunaan:

> Pengguna mengatakan: "Jam 8 malam ingatkan saya untuk mengerjakan laporan."

Sistem akan mengubah suara tersebut menjadi teks, kemudian teks dapat diteruskan ke AI Reminder Assistant untuk membantu mengenali informasi reminder.

### H. Local Notification & Alarm

- **Teknologi:** Local Notification
- **Integrasi:** Flutter
- **Justifikasi:** Sistem notifikasi lokal digunakan untuk memberikan pengingat kepada pengguna berdasarkan tanggal dan waktu reminder yang telah disimpan. Fitur ini memungkinkan reminder tetap memberikan notifikasi meskipun aplikasi tidak sedang dibuka.

---

## Alur Utama Sistem

```text
Input Manual / Input Suara
            ↓
      Speech-to-Text
            ↓
        Teks Input
            ↓
   AI Reminder Assistant
            ↓
Identifikasi Aktivitas,
Tanggal, Waktu, Pengulangan
            ↓
     Preview Reminder
            ↓
    Konfirmasi Pengguna
            ↓
     Reminder Disimpan
            ↓
 Alarm / Notifikasi Dijadwalkan
            ↓
     Reminder Ditampilkan
            ↓
Selesai / Snooze / Terlewat

## CONTROLING WORK
[Buka Spreadsheet Controling Work](https://docs.google.com/spreadsheets/d/1WhWnzT9Gy6BpvVMmNNfOIT7bykbvL7h-UR7XL2mpLXs/edit?usp=sharing)  
