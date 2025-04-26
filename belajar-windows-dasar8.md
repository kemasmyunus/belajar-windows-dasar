# Belajar Windows Dasar 8: Pengenalan Terminal (CMD)

## Apa Itu CMD?

Command Prompt (CMD) adalah program interpreter baris perintah di Windows yang memungkinkan pengguna berinteraksi dengan sistem menggunakan teks, bukan klik mouse. Ini penting untuk berbagai tugas teknis seperti navigasi file, pengelolaan sistem, dan troubleshooting.

---

## Membuka CMD

Ada beberapa cara membuka CMD:
- Tekan `Windows + R`, ketik `cmd`, lalu Enter.
- Klik kanan Start Menu → pilih "Command Prompt" atau "Windows Terminal" (di Windows 11).
- Search di Start Menu: ketik `cmd` → pilih "Run as administrator" (jika butuh akses lebih tinggi).

---

## Perintah Dasar CMD

| Perintah        | Fungsi                                    |
|-----------------|-------------------------------------------|
| `dir`           | Melihat daftar file dan folder            |
| `cd`            | Pindah directory/folder                   |
| `cd ..`         | Naik satu level folder                    |
| `mkdir nama`    | Membuat folder baru                       |
| `rmdir nama`    | Menghapus folder                          |
| `del nama.file` | Menghapus file                            |
| `copy file1 file2` | Menyalin file                         |
| `move file1 file2` | Memindahkan atau rename file/folder    |
| `cls`           | Membersihkan layar CMD                   |
| `exit`          | Menutup CMD                               |

---

## Navigasi Folder

Contoh:
```bash
cd Documents\Project
```
Artinya: Masuk ke folder `Documents`, lalu ke `Project`.

Kalau mau langsung ke drive lain, ketik:
```bash
D:
```
untuk pindah ke drive D:\.

---

## Manipulasi File dan Folder

Membuat folder:
```bash
mkdir BelajarCMD
```
Menghapus folder:
```bash
rmdir BelajarCMD
```
Menghapus file:
```bash
del laporan.txt
```

---

## Menjalankan Program Lewat CMD

Contoh:
```bash
notepad
```
Akan membuka aplikasi Notepad.

Kalau mau buka file dengan program tertentu:
```bash
start notepad laporan.txt
```
Ini akan membuka `laporan.txt` di Notepad.

---

## Tips Tambahan

- Gunakan `tab` untuk auto-complete nama file/folder.
- Tekan `Arrow Up` untuk mengulang perintah sebelumnya.
- CMD tidak case sensitive, jadi `DIR` dan `dir` sama saja.

---
