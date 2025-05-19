## 💡 Latihan Soal CMD

Berikut beberapa soal untuk menguji pemahamanmu:

### **Soal Teori:**

1. Apa fungsi perintah `cd ..`?
2. Bagaimana cara menghapus file bernama `catatan.txt` lewat CMD?
3. Apa perbedaan `copy` dan `move`?
4. Apa gunanya perintah `cls`?
5. Bagaimana cara menampilkan daftar proses yang sedang berjalan?

### **Soal Praktik:**

1. Buat folder bernama `LatihanCMD` di direktori saat ini.
2. Masuk ke folder tersebut, lalu buat file kosong bernama `data.txt`.
3. Salin file `data.txt` menjadi `data_backup.txt`.
4. Hapus file `data.txt` saja.
5. Buat batch file yang akan membuka Notepad dan menampilkan pesan “Selamat datang”.

---

## 🔧 Proyek Mini CMD

Berikut beberapa proyek mini yang bisa kamu coba untuk latihan:

### **1. Auto Backup Sederhana**

**Tujuan**: Menyalin isi folder penting ke folder backup.

```bat
@echo off
set sumber=C:\Users\%username%\Documents\Project
set tujuan=C:\Backup\ProjectBackup
xcopy "%sumber%" "%tujuan%" /s /i /y
echo Backup selesai.
pause
```

> Catatan: Pastikan folder `Project` dan `Backup` ada, atau gunakan `mkdir` dulu.

---

### **2. Menu Interaktif**

**Tujuan**: Memberi pilihan kepada pengguna untuk membuka aplikasi tertentu.

```bat
@echo off
:menu
cls
echo === MENU UTAMA ===
echo 1. Buka Notepad
echo 2. Buka Kalkulator
echo 3. Keluar
set /p pilihan=Pilih opsi [1-3]:

if "%pilihan%"=="1" (
    start notepad
    goto menu
)
if "%pilihan%"=="2" (
    start calc
    goto menu
)
if "%pilihan%"=="3" (
    exit
)
goto menu
```

---
