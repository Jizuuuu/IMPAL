# Spesifikasi Kebutuhan Perangkat Lunak (SKPL)

**Eling – Aplikasi Mobile Pengingat Harian Berbasis AI**

## Daftar Isi

1. [Pendahuluan](#1-pendahuluan)
   - [1.1 Tujuan Penulisan Dokumen](#11-tujuan-penulisan-dokumen)
   - [1.2 Lingkup Masalah](#12-lingkup-masalah)
2. [Deskripsi Umum](#2-deskripsi-umum)
   - [2.1 Perspektif Produk](#21-perspektif-produk)
   - [2.2 Fungsi Produk](#22-fungsi-produk)
   - [2.3 Karakteristik Pengguna](#23-karakteristik-pengguna)
   - [2.4 Lingkungan Operasi](#24-lingkungan-operasi)
   - [2.5 Batasan Perancangan dan Implementasi](#25-batasan-perancangan-dan-implementasi)
   - [2.6 Asumsi dan Ketergantungan](#26-asumsi-dan-ketergantungan)
3. [Kebutuhan Spesifik](#3-kebutuhan-spesifik)
   - [3.1 Kebutuhan Antarmuka Eksternal](#31-kebutuhan-antarmuka-eksternal)
   - [3.2 Kebutuhan Fungsional](#32-kebutuhan-fungsional)
     - [3.2.1 Autentikasi dan Manajemen Pengguna](#321-autentikasi-dan-manajemen-pengguna)
     - [3.2.2 Manajemen Reminder](#322-manajemen-reminder)
     - [3.2.3 Alarm dan Notifikasi](#323-alarm-dan-notifikasi)
     - [3.2.4 Speech-to-Text](#324-speech-to-text)
     - [3.2.5 AI Reminder Assistant](#325-ai-reminder-assistant)
     - [3.2.6 Kategori dan Riwayat Reminder](#326-kategori-dan-riwayat-reminder)
     - [3.2.7 Pengaturan dan Profil](#327-pengaturan-dan-profil)
   - [3.3 Daftar Use Case](#33-daftar-use-case)
   - [3.4 Kebutuhan Nonfungsional](#34-kebutuhan-nonfungsional)
   - [3.5 Kebutuhan Data](#35-kebutuhan-data)
4. [Matriks Keterlacakan](#4-matriks-keterlacakan)

---

## 1. Pendahuluan

### 1.1 Tujuan Penulisan Dokumen

Dokumen Spesifikasi Kebutuhan Perangkat Lunak (SKPL) ini mendefinisikan kebutuhan fungsional dan nonfungsional dari **Eling**, yaitu aplikasi mobile pengingat aktivitas harian berbasis AI.

Dokumen ini digunakan sebagai acuan bagi tim pengembang dalam menentukan kebutuhan sistem yang harus direalisasikan. SKPL menjadi dasar dalam proses perancangan, implementasi, pengujian, dan validasi sistem serta menjadi dasar penyusunan Deskripsi Perancangan Perangkat Lunak (DPPL).

Eling dirancang sebagai aplikasi pengingat harian yang memungkinkan pengguna membuat reminder secara manual maupun menggunakan input suara yang kemudian diproses oleh AI untuk mengenali informasi reminder seperti aktivitas, tanggal, waktu, dan pengulangan.

### 1.2 Lingkup Masalah

Pengguna sering memiliki berbagai aktivitas yang harus dilakukan pada waktu tertentu, seperti kuliah, mengumpulkan tugas, rapat, olahraga, atau aktivitas pribadi lainnya. Pencatatan aktivitas secara manual terkadang kurang praktis karena pengguna harus mengisi beberapa informasi reminder satu per satu.

Eling menyediakan fitur pengingat harian yang memungkinkan pengguna membuat dan mengelola reminder melalui perangkat mobile.

Fitur utama yang disediakan Eling meliputi:

- pembuatan reminder secara manual;
- pengaturan aktivitas, tanggal, dan waktu reminder;
- pengaturan reminder berulang;
- alarm dan notifikasi pengingat;
- fitur snooze pada reminder;
- input reminder menggunakan suara;
- konversi suara menjadi teks menggunakan Speech-to-Text;
- pemrosesan teks menggunakan AI untuk mengenali informasi reminder;
- menampilkan hasil pemrosesan AI sebelum reminder disimpan;
- konfirmasi pengguna sebelum hasil AI disimpan sebagai reminder;
- pengelompokan reminder berdasarkan kategori;
- riwayat reminder;
- pencarian reminder;
- pengaturan suara, getaran, dan durasi snooze;
- pengelolaan profil pengguna.

AI pada Eling digunakan sebagai **asisten untuk membantu membuat reminder**, bukan sebagai sistem yang melakukan analisis produktivitas pengguna.

**Di luar lingkup sistem:**

- analisis produktivitas pengguna;
- analisis pola kebiasaan pengguna;
- pemberian insight produktivitas;
- prediksi aktivitas pengguna;
- rekomendasi aktivitas secara otomatis;
- sistem manajemen tugas yang kompleks;
- penyimpanan reminder secara otomatis tanpa konfirmasi pengguna.

---

## 2. Deskripsi Umum

### 2.1 Perspektif Produk

Eling merupakan aplikasi mobile yang berfungsi sebagai pengingat aktivitas harian pengguna. Sistem menyediakan dua cara utama untuk membuat reminder, yaitu melalui input manual dan melalui input suara yang diproses menggunakan Speech-to-Text dan AI.

Pada pembuatan reminder menggunakan suara, pengguna menyampaikan aktivitas dalam bahasa natural. Sistem kemudian mengubah suara menjadi teks menggunakan Speech-to-Text. Teks tersebut dikirim ke layanan AI untuk mengenali informasi reminder seperti aktivitas, tanggal, waktu, dan pengulangan.

Hasil pemrosesan AI tidak langsung disimpan. Sistem menampilkan hasil tersebut kepada pengguna dalam bentuk preview sehingga pengguna dapat memeriksa dan mengubah informasi sebelum melakukan konfirmasi.

Secara umum, alur pembuatan reminder menggunakan AI adalah:

```text
Input Suara Pengguna
        ↓
Speech-to-Text
        ↓
Teks Input
        ↓
AI Reminder Assistant
        ↓
Identifikasi Aktivitas,
Tanggal, Waktu, dan Pengulangan
        ↓
Preview Reminder
        ↓
Konfirmasi Pengguna
        ↓
Reminder Disimpan
        ↓
Alarm / Notifikasi Dijadwalkan
```
### 2.2 Fungsi Produk

Fungsi utama yang disediakan oleh Eling meliputi:

- **Autentikasi dan manajemen pengguna**
  - registrasi akun;
  - login dan logout;
  - pengelolaan profil pengguna.

- **Manajemen reminder**
  - membuat reminder secara manual;
  - menentukan aktivitas atau judul reminder;
  - menentukan tanggal dan waktu;
  - mengatur reminder berulang;
  - mengubah reminder;
  - menghapus reminder;
  - melihat daftar reminder;
  - melihat detail reminder.

- **Alarm dan notifikasi**
  - memberikan notifikasi pada waktu yang ditentukan;
  - menampilkan informasi aktivitas pada notifikasi;
  - melakukan snooze;
  - mengatur durasi snooze;
  - menandai reminder sebagai selesai.

- **Speech-to-Text**
  - menerima input suara;
  - mengubah suara menjadi teks;
  - menampilkan hasil transkripsi;
  - memungkinkan pengguna mengubah hasil transkripsi.

- **AI Reminder Assistant**
  - memproses teks input pengguna;
  - mengenali aktivitas atau judul reminder;
  - mengenali tanggal;
  - mengenali waktu;
  - mengenali pengulangan;
  - menampilkan hasil dalam bentuk preview;
  - memungkinkan pengguna mengubah hasil AI;
  - meminta konfirmasi sebelum menyimpan reminder.

- **Kategori dan riwayat**
  - memberikan kategori pada reminder;
  - melihat reminder berdasarkan kategori;
  - melihat riwayat reminder;
  - mencatat reminder yang selesai atau terlewat;
  - mencari reminder berdasarkan kata kunci.

- **Pengaturan**
  - mengatur status notifikasi;
  - mengatur suara;
  - mengatur getaran;
  - mengatur durasi snooze;
  - mengelola profil pengguna.

### 2.3 Karakteristik Pengguna

| Pengguna | Deskripsi | Hak Akses Utama |
| --- | --- | --- |
| Pengguna | Pengguna umum yang menggunakan aplikasi untuk membuat dan mengelola pengingat aktivitas harian | Membuat, melihat, mengubah, menghapus, menyelesaikan, dan mencari reminder; menggunakan Speech-to-Text dan AI; mengatur profil dan notifikasi |

Pengguna tidak memerlukan kemampuan teknis khusus untuk menggunakan Eling. Pengguna cukup memahami penggunaan dasar perangkat mobile seperti menyentuh tombol, mengisi formulir, memberikan izin mikrofon, dan menerima notifikasi.

### 2.4 Lingkungan Operasi

Eling dirancang untuk berjalan pada perangkat mobile dengan lingkungan operasi sebagai berikut:

- **Platform:** Android
- **Framework:** Flutter
- **Bahasa pemrograman:** Dart
- **Basis data:** PostgreSQL
- **Backend/layanan data:** Supabase atau backend yang menyediakan REST API
- **Layanan AI:** Google Gemini API
- **Speech-to-Text:** layanan Speech-to-Text yang kompatibel dengan perangkat mobile
- **Koneksi:** Internet diperlukan untuk fitur Speech-to-Text dan pemrosesan AI
- **Notifikasi:** mekanisme notifikasi lokal pada perangkat
- **Perangkat keras:** layar sentuh, speaker, dan mikrofon

### 2.5 Batasan Perancangan dan Implementasi

Batasan perancangan dan implementasi Eling adalah:

- aplikasi dikembangkan sebagai aplikasi mobile;
- framework yang digunakan adalah Flutter;
- bahasa pemrograman yang digunakan adalah Dart;
- basis data menggunakan PostgreSQL;
- layanan backend menggunakan Supabase atau layanan backend yang menyediakan API;
- pemrosesan AI menggunakan Google Gemini API;
- Speech-to-Text menggunakan layanan yang sesuai dengan platform mobile;
- API key layanan AI tidak disimpan secara langsung pada aplikasi mobile;
- komunikasi dengan layanan backend dilakukan melalui API;
- AI hanya digunakan untuk membantu mengubah input bahasa natural menjadi informasi reminder;
- hasil AI harus ditampilkan kepada pengguna sebelum disimpan;
- pengguna tetap dapat membuat reminder secara manual;
- sistem tidak melakukan analisis produktivitas atau pola kebiasaan pengguna;
- sistem tidak membuat reminder secara otomatis tanpa persetujuan pengguna;
- fitur AI bergantung pada ketersediaan koneksi internet dan layanan eksternal.

### 2.6 Asumsi dan Ketergantungan

Eling memiliki beberapa asumsi dan ketergantungan sebagai berikut:

- pengguna memiliki perangkat mobile yang kompatibel dengan aplikasi;
- pengguna memberikan izin notifikasi kepada aplikasi;
- pengguna memberikan izin mikrofon apabila menggunakan fitur Speech-to-Text;
- tanggal dan waktu pada perangkat pengguna diatur dengan benar;
- layanan Speech-to-Text tersedia ketika fitur tersebut digunakan;
- Google Gemini API tersedia ketika pengguna menggunakan fitur AI;
- koneksi internet tersedia untuk fitur yang membutuhkan layanan eksternal;
- apabila layanan AI gagal, pengguna tetap dapat menggunakan fitur reminder manual;
- notifikasi lokal dapat berjalan pada perangkat sesuai dengan izin dan konfigurasi sistem operasi;
- pengguna bertanggung jawab untuk memastikan informasi reminder yang dibuat sudah benar sebelum disimpan.

---

## 3. Kebutuhan Spesifik

### 3.1 Kebutuhan Antarmuka Eksternal

#### 3.1.1 Antarmuka Pengguna

Eling menggunakan antarmuka mobile yang dirancang untuk memudahkan pengguna membuat dan mengelola reminder.

Halaman utama sistem meliputi:

- halaman login;
- halaman registrasi;
- halaman utama;
- halaman daftar reminder;
- halaman tambah reminder;
- halaman edit reminder;
- halaman detail reminder;
- halaman input suara;
- halaman preview hasil AI;
- halaman kategori;
- halaman riwayat reminder;
- halaman pencarian;
- halaman profil;
- halaman pengaturan notifikasi.

Antarmuka menyediakan navigasi yang sederhana dan konsisten agar pengguna dapat membuat reminder dengan jumlah langkah yang seminimal mungkin.

#### 3.1.2 Antarmuka Perangkat Keras

Eling menggunakan perangkat keras yang tersedia pada smartphone, yaitu:

- layar sentuh untuk interaksi pengguna;
- mikrofon untuk input suara;
- speaker untuk suara alarm;
- perangkat mobile untuk menampilkan notifikasi.

Tidak diperlukan perangkat keras tambahan.

#### 3.1.3 Antarmuka Perangkat Lunak

Eling berkomunikasi dengan beberapa layanan perangkat lunak, yaitu:

- backend/API untuk pengelolaan data;
- PostgreSQL untuk penyimpanan data;
- Google Gemini API untuk pemrosesan bahasa natural;
- layanan Speech-to-Text untuk mengubah suara menjadi teks;
- sistem notifikasi lokal pada perangkat.

#### 3.1.4 Antarmuka Komunikasi

Komunikasi antara aplikasi dengan backend dan layanan eksternal dilakukan melalui jaringan internet menggunakan protokol HTTP/HTTPS.

Data yang dikirimkan ke layanan eksternal harus dibatasi sesuai kebutuhan fitur dan tidak boleh menyertakan informasi yang tidak diperlukan untuk pemrosesan reminder.

---

## 3.2 Kebutuhan Fungsional

### 3.2.1 Autentikasi dan Manajemen Pengguna

| ID | Kebutuhan | Prioritas |
| --- | --- | --- |
| SKPL-F-001 | Sistem harus menyediakan registrasi akun menggunakan data nama, email, dan kata sandi. | Tinggi |
| SKPL-F-002 | Sistem harus menyediakan fitur login dan logout bagi pengguna. | Tinggi |
| SKPL-F-003 | Sistem harus membatasi akses data reminder berdasarkan akun pengguna yang sedang login. | Tinggi |
| SKPL-F-004 | Pengguna dapat melihat profil miliknya sendiri. | Sedang |
| SKPL-F-005 | Pengguna dapat mengubah data profil miliknya sendiri. | Sedang |

### 3.2.2 Manajemen Reminder

| ID | Kebutuhan | Prioritas |
| --- | --- | --- |
| SKPL-F-006 | Pengguna dapat membuat reminder secara manual. | Tinggi |
| SKPL-F-007 | Pengguna dapat menentukan judul atau aktivitas reminder. | Tinggi |
| SKPL-F-008 | Pengguna dapat menentukan tanggal reminder. | Tinggi |
| SKPL-F-009 | Pengguna dapat menentukan waktu reminder. | Tinggi |
| SKPL-F-010 | Pengguna dapat mengubah data reminder yang telah dibuat. | Tinggi |
| SKPL-F-011 | Pengguna dapat menghapus reminder. | Tinggi |
| SKPL-F-012 | Sistem menampilkan daftar reminder milik pengguna. | Tinggi |
| SKPL-F-013 | Pengguna dapat mengatur reminder agar berulang. | Tinggi |
| SKPL-F-014 | Sistem menyediakan pilihan pengulangan seperti sekali, setiap hari, hari kerja, mingguan, atau pengulangan tertentu. | Sedang |
| SKPL-F-015 | Pengguna dapat melihat detail reminder yang telah dibuat. | Sedang |

### 3.2.3 Alarm dan Notifikasi

| ID | Kebutuhan | Prioritas |
| --- | --- | --- |
| SKPL-F-016 | Sistem harus memberikan alarm atau notifikasi pada waktu reminder yang telah ditentukan. | Tinggi |
| SKPL-F-017 | Notifikasi harus menampilkan informasi aktivitas reminder yang harus dilakukan. | Tinggi |
| SKPL-F-018 | Pengguna dapat melakukan snooze ketika reminder muncul. | Tinggi |
| SKPL-F-019 | Sistem menyediakan pilihan durasi snooze. | Sedang |
| SKPL-F-020 | Pengguna dapat menandai reminder sebagai selesai. | Tinggi |
| SKPL-F-021 | Sistem menyimpan status reminder setelah reminder selesai atau terlewat. | Sedang |
| SKPL-F-022 | Sistem harus tetap dapat memberikan notifikasi reminder yang telah dijadwalkan tanpa pengguna harus membuka aplikasi secara terus-menerus. | Tinggi |

### 3.2.4 Speech-to-Text

| ID | Kebutuhan | Prioritas |
| --- | --- | --- |
| SKPL-F-023 | Sistem menyediakan fitur input reminder menggunakan suara. | Tinggi |
| SKPL-F-024 | Sistem harus mengubah suara pengguna menjadi teks menggunakan Speech-to-Text. | Tinggi |
| SKPL-F-025 | Sistem menampilkan hasil transkripsi suara kepada pengguna. | Tinggi |
| SKPL-F-026 | Pengguna dapat mengubah hasil transkripsi sebelum dikirim ke AI. | Sedang |
| SKPL-F-027 | Sistem menampilkan pesan kesalahan apabila proses Speech-to-Text gagal. | Sedang |

### 3.2.5 AI Reminder Assistant

| ID | Kebutuhan | Prioritas |
| --- | --- | --- |
| SKPL-F-028 | Sistem dapat mengirimkan teks reminder dari pengguna ke layanan AI. | Tinggi |
| SKPL-F-029 | Sistem harus dapat mengenali aktivitas atau judul reminder dari teks pengguna. | Tinggi |
| SKPL-F-030 | Sistem harus dapat mengenali tanggal reminder dari teks pengguna apabila informasi tanggal tersedia. | Tinggi |
| SKPL-F-031 | Sistem harus dapat mengenali waktu reminder dari teks pengguna apabila informasi waktu tersedia. | Tinggi |
| SKPL-F-032 | Sistem harus dapat mengenali informasi pengulangan reminder apabila tersedia. | Sedang |
| SKPL-F-033 | Sistem menampilkan hasil pemrosesan AI dalam bentuk preview reminder. | Tinggi |
| SKPL-F-034 | Pengguna dapat mengubah informasi reminder hasil pemrosesan AI sebelum menyimpannya. | Tinggi |
| SKPL-F-035 | Sistem tidak boleh menyimpan hasil pemrosesan AI sebagai reminder aktif sebelum pengguna memberikan konfirmasi. | Tinggi |
| SKPL-F-036 | Sistem menampilkan pesan kesalahan apabila layanan AI tidak tersedia atau gagal memproses input. | Sedang |
| SKPL-F-037 | Pengguna tetap dapat membuat reminder secara manual apabila layanan AI gagal. | Tinggi |

### 3.2.6 Kategori dan Riwayat Reminder

| ID | Kebutuhan | Prioritas |
| --- | --- | --- |
| SKPL-F-038 | Pengguna dapat memberikan kategori pada reminder. | Sedang |
| SKPL-F-039 | Sistem menyediakan kategori reminder seperti Kuliah, Tugas, Pribadi, Kesehatan, Pekerjaan, dan Lainnya. | Sedang |
| SKPL-F-040 | Pengguna dapat melihat riwayat reminder yang telah selesai atau terlewat. | Sedang |
| SKPL-F-041 | Sistem mencatat status reminder pada riwayat. | Sedang |
| SKPL-F-042 | Pengguna dapat mencari reminder berdasarkan kata kunci. | Sedang |
| SKPL-F-043 | Pengguna dapat melihat reminder berdasarkan kategori. | Rendah |

### 3.2.7 Pengaturan dan Profil

| ID | Kebutuhan | Prioritas |
| --- | --- | --- |
| SKPL-F-044 | Pengguna dapat mengatur status notifikasi aplikasi. | Tinggi |
| SKPL-F-045 | Pengguna dapat mengatur suara notifikasi atau alarm. | Sedang |
| SKPL-F-046 | Pengguna dapat mengatur penggunaan getaran pada notifikasi. | Sedang |
| SKPL-F-047 | Pengguna dapat menentukan durasi snooze default. | Sedang |
| SKPL-F-048 | Pengguna dapat melihat dan mengubah informasi profil. | Sedang |

---

## 3.3 Daftar Use Case

| ID | Use Case | Aktor |
| --- | --- | --- |
| UC-01 | Registrasi dan Login | Pengguna |
| UC-02 | Mengelola Profil | Pengguna |
| UC-03 | Membuat Reminder Manual | Pengguna |
| UC-04 | Melihat Reminder | Pengguna |
| UC-05 | Mengubah Reminder | Pengguna |
| UC-06 | Menghapus Reminder | Pengguna |
| UC-07 | Mengatur Reminder Berulang | Pengguna |
| UC-08 | Menerima Alarm atau Notifikasi | Pengguna |
| UC-09 | Melakukan Snooze Reminder | Pengguna |
| UC-10 | Menyelesaikan Reminder | Pengguna |
| UC-11 | Input Reminder dengan Suara | Pengguna |
| UC-12 | Memproses Reminder dengan AI | Pengguna |
| UC-13 | Mengonfirmasi Hasil AI | Pengguna |
| UC-14 | Mengelola Kategori Reminder | Pengguna |
| UC-15 | Melihat Riwayat Reminder | Pengguna |
| UC-16 | Mencari Reminder | Pengguna |
| UC-17 | Mengatur Notifikasi | Pengguna |

---

## 3.4 Kebutuhan Nonfungsional

| ID | Kategori | Kebutuhan |
| --- | --- | --- |
| SKPL-NF-001 | Kegunaan | Sistem harus memiliki antarmuka yang sederhana dan mudah digunakan oleh pengguna tanpa kemampuan teknis khusus. |
| SKPL-NF-002 | Kegunaan | Proses pembuatan reminder manual harus dapat dilakukan dengan langkah yang sederhana dan jelas. |
| SKPL-NF-003 | Kegunaan | Sistem harus menggunakan istilah dan navigasi yang konsisten pada seluruh halaman aplikasi. |
| SKPL-NF-004 | Kinerja | Sistem harus memberikan respons yang wajar ketika pengguna melakukan operasi seperti membuat, mengubah, menghapus, atau melihat reminder. |
| SKPL-NF-005 | Kinerja | Sistem harus menampilkan indikator proses ketika sedang melakukan proses Speech-to-Text atau pemrosesan AI. |
| SKPL-NF-006 | Kinerja | Sistem harus memberikan respons kesalahan apabila proses AI atau Speech-to-Text membutuhkan waktu terlalu lama. |
| SKPL-NF-007 | Keandalan | Reminder yang telah berhasil disimpan harus tetap tersedia meskipun pengguna menutup aplikasi. |
| SKPL-NF-008 | Keandalan | Kegagalan layanan AI tidak boleh mengganggu fungsi utama reminder manual. |
| SKPL-NF-009 | Keamanan | Sistem hanya boleh memberikan akses kepada pengguna terhadap reminder miliknya sendiri. |
| SKPL-NF-010 | Keamanan | Informasi autentikasi pengguna harus dilindungi dan tidak boleh disimpan atau dikirim dalam bentuk yang tidak aman. |
| SKPL-NF-011 | Keamanan | API key layanan AI tidak boleh disimpan secara langsung pada aplikasi mobile. |
| SKPL-NF-012 | Privasi | Data pengguna hanya digunakan sesuai kebutuhan aplikasi dan tidak dikirim ke layanan AI apabila tidak diperlukan. |
| SKPL-NF-013 | Kompatibilitas | Sistem harus dapat berjalan pada perangkat Android yang mendukung versi Flutter dan dependensi yang digunakan. |
| SKPL-NF-014 | Konsistensi | Tampilan, istilah, tombol, dan navigasi harus konsisten pada seluruh aplikasi. |
| SKPL-NF-015 | Validasi | Sistem harus memberikan validasi terhadap data reminder sebelum disimpan. |
| SKPL-NF-016 | Penanganan Kesalahan | Sistem harus menampilkan pesan kesalahan yang jelas ketika terjadi kegagalan penyimpanan, koneksi, Speech-to-Text, atau AI. |
| SKPL-NF-017 | Ketersediaan | Reminder yang telah dijadwalkan harus dapat menghasilkan notifikasi sesuai pengaturan perangkat dan izin pengguna. |
| SKPL-NF-018 | Pemeliharaan | Sistem harus memiliki struktur kode yang terorganisasi sehingga dapat dikembangkan dan dipelihara oleh tim pengembang. |

---

## 3.5 Kebutuhan Data

Eling membutuhkan beberapa entitas utama untuk mendukung fungsi sistem.

### 3.5.1 Data Pengguna

Data pengguna yang disimpan meliputi:

- ID pengguna;
- nama;
- email;
- kata sandi atau kredensial autentikasi;
- foto profil;
- informasi akun;
- waktu pembuatan akun.

### 3.5.2 Data Reminder

Data reminder meliputi:

- ID reminder;
- ID pengguna;
- judul atau aktivitas;
- tanggal;
- waktu;
- kategori;
- status reminder;
- informasi pengulangan;
- status alarm;
- waktu pembuatan;
- waktu perubahan.

### 3.5.3 Data Kategori

Data kategori meliputi:

- ID kategori;
- nama kategori;
- deskripsi kategori.

Kategori dapat digunakan untuk mengelompokkan reminder seperti:

- Kuliah;
- Tugas;
- Pribadi;
- Kesehatan;
- Pekerjaan;
- Lainnya.

### 3.5.4 Data Riwayat Reminder

Data riwayat reminder meliputi:

- ID riwayat;
- ID reminder;
- status reminder;
- waktu reminder selesai;
- waktu reminder terlewat;
- waktu pencatatan riwayat.

### 3.5.5 Data Pengaturan Notifikasi

Data pengaturan notifikasi meliputi:

- status notifikasi;
- status suara;
- status getaran;
- durasi snooze default;
- pengaturan alarm.

### 3.5.6 Data Pemrosesan AI

Data yang berkaitan dengan pemrosesan AI dapat meliputi:

- ID permintaan;
- ID pengguna;
- input teks pengguna;
- hasil pemrosesan AI;
- status pemrosesan;
- waktu permintaan.

> Struktur tabel, tipe data, primary key, foreign key, relasi antarentitas, dan rancangan basis data secara lebih rinci dibahas pada dokumen DPPL.

---

# 4. Matriks Keterlacakan

| Fitur Utama | Kebutuhan SKPL | Use Case |
| --- | --- | --- |
| Autentikasi dan manajemen pengguna | SKPL-F-001 s.d. SKPL-F-005 | UC-01, UC-02 |
| Manajemen reminder | SKPL-F-006 s.d. SKPL-F-015 | UC-03, UC-04, UC-05, UC-06, UC-07 |
| Alarm dan notifikasi | SKPL-F-016 s.d. SKPL-F-022 | UC-08, UC-09, UC-10 |
| Speech-to-Text | SKPL-F-023 s.d. SKPL-F-027 | UC-11 |
| AI Reminder Assistant | SKPL-F-028 s.d. SKPL-F-037 | UC-12, UC-13 |
| Kategori dan riwayat reminder | SKPL-F-038 s.d. SKPL-F-043 | UC-14, UC-15, UC-16 |
| Pengaturan dan profil | SKPL-F-044 s.d. SKPL-F-048 | UC-02, UC-17 |
