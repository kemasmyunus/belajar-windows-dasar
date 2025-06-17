# **Belajar Windows Dasar: Terminal (CMD & PowerShell)**

## **Bab 1: Pengenalan Terminal di Windows**
### **1.1 Apa itu Terminal?**
Terminal di Windows merujuk pada antarmuka berbasis teks yang digunakan untuk menjalankan perintah sistem. Ada dua terminal utama di Windows:
- **Command Prompt (CMD)**: Terminal bawaan Windows yang sudah ada sejak versi lama.
- **PowerShell**: Terminal yang lebih canggih dengan dukungan scripting yang lebih kuat.

### **1.2 Membuka Terminal di Windows**
Untuk membuka terminal di Windows, gunakan salah satu cara berikut:
- **Command Prompt**: Tekan `Win + R`, ketik `cmd`, lalu tekan `Enter`.
- **PowerShell**: Tekan `Win + R`, ketik `powershell`, lalu tekan `Enter`.
- **Windows Terminal**: Tekan `Win + X`, lalu pilih `Windows Terminal`.

### **1.3 Perbedaan CMD dan PowerShell**
| Fitur | Command Prompt (CMD) | PowerShell |
|---|---|---|
| Perintah Dasar | Dukungan terbatas | Dukungan lebih luas |
| Scripting | Batch script (`.bat`) | PowerShell script (`.ps1`) |
| Ekstensi | Perintah dasar saja | Bisa menggunakan cmdlet dan modul tambahan |

---

## **Bab 2: Perintah Dasar di CMD dan PowerShell**

### **2.1 Perintah Navigasi File dan Folder**
| Perintah | Fungsi |
|---|---|
| `dir` | Menampilkan daftar file dan folder dalam direktori (CMD) |
| `ls` | Menampilkan daftar file dan folder (PowerShell) |
| `cd <folder>` | Berpindah ke folder tertentu |
| `cd ..` | Kembali ke folder sebelumnya |
| `mkdir <nama_folder>` | Membuat folder baru |
| `rmdir <nama_folder>` | Menghapus folder kosong |
| `del <nama_file>` | Menghapus file |

### **2.2 Perintah Manajemen Sistem**
| Perintah | Fungsi |
|---|---|
| `cls` | Membersihkan layar terminal |
| `echo <teks>` | Menampilkan teks ke terminal |
| `type <file>` | Menampilkan isi file teks (CMD) |
| `cat <file>` | Menampilkan isi file teks (PowerShell) |
| `tasklist` | Menampilkan daftar proses yang berjalan |
| `taskkill /IM <nama_proses>` | Menghentikan proses tertentu |
| `shutdown /s /t 0` | Mematikan komputer |
| `shutdown /r /t 0` | Merestart komputer |

### **2.3 Perintah Jaringan**
| Perintah | Fungsi |
|---|---|
| `ipconfig` | Menampilkan konfigurasi jaringan |
| `ping <alamat>` | Mengecek koneksi ke suatu alamat |
| `netstat -an` | Melihat koneksi jaringan yang aktif |
| `nslookup <domain>` | Melihat informasi DNS dari domain |

---

## **Bab 3: Pengenalan Scripting di PowerShell**

### **3.1 Membuat dan Menjalankan Skrip PowerShell**
1. Buka Notepad, tulis perintah berikut:
   ```powershell
   Write-Output "Halo, ini skrip PowerShell pertama saya!"
   ```
2. Simpan sebagai `script.ps1`.
3. Jalankan dengan perintah:
   ```powershell
   powershell -ExecutionPolicy Bypass -File script.ps1
   ```

### **3.2 Variabel dan Operasi Dasar**
```powershell
$nama = "Windows"
Write-Output "Selamat datang di $nama!"
```

### **3.3 Menggunakan Loop**
```powershell
for ($i=1; $i -le 5; $i++) {
    Write-Output "Perulangan ke-$i"
}
```

---
