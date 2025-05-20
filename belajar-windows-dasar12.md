## 🛠️ Otomatisasi Tingkat Lanjut di CMD

CMD memang terbatas, tapi masih bisa digunakan untuk beberapa hal yang cukup kuat jika dikombinasikan dengan:

### 1. **Jadwal Tugas Otomatis (Task Scheduler)**

CMD bisa digunakan untuk menjadwalkan tugas, misalnya backup otomatis setiap hari:

```bat
schtasks /create /tn "BackupHarain" /tr "C:\Scripts\backup.bat" /sc daily /st 08:00
```

Keterangan:

* `/tn` = nama tugas
* `/tr` = jalur ke script batch
* `/sc` = schedule (daily, weekly, dll)
* `/st` = start time (08:00)

---

### 2. **Log Otomatis ke File**

Untuk mencatat aktivitas script:

```bat
echo Backup dimulai pada %date% %time% >> log_backup.txt
xcopy C:\Data D:\Backup /s /i /y >> log_backup.txt
echo Backup selesai pada %date% %time% >> log_backup.txt
```

---

### 3. **Deteksi dan Tanggapi Error**

```bat
@echo off
xcopy C:\Data D:\Backup /s /i /y
if errorlevel 1 (
    echo Terjadi error saat backup! >> log_error.txt
) else (
    echo Backup berhasil.
)
pause
```

---

### 4. **Membersihkan Folder Secara Otomatis**

Contoh: Menghapus semua file `.tmp` di folder tertentu.

```bat
del /s /q C:\Temp\*.tmp
```

* `/s` = semua subfolder
* `/q` = tanpa konfirmasi

---

## ⚡ Transisi ke PowerShell

Setelah kamu cukup mahir dengan CMD, **PowerShell** adalah langkah lanjutan yang alami.

### Apa Itu PowerShell?

PowerShell adalah shell baris perintah dan bahasa scripting modern yang:

* Lebih kuat daripada CMD.
* Bisa mengakses .NET Framework.
* Memproses *objek*, bukan sekadar teks.
* Mendukung otomatisasi Windows secara mendalam.

### Contoh Perbandingan:

| Tugas                          | CMD                | PowerShell                           |
| ------------------------------ | ------------------ | ------------------------------------ |
| Menampilkan daftar file        | `dir`              | `Get-ChildItem`                      |
| Menyalin file                  | `copy file1 file2` | `Copy-Item file1 -Destination file2` |
| Menjadwalkan tugas             | `schtasks`         | `Register-ScheduledTask`             |
| Menyaring berdasarkan ekstensi | Sulit              | `Get-ChildItem *.txt`                |
| Menampilkan info sistem        | `systeminfo`       | `Get-ComputerInfo`                   |

---

### Contoh Script PowerShell Sederhana

```powershell
$nama = Read-Host "Masukkan nama Anda"
Write-Output "Halo, $nama!"
```

**Backup Otomatis:**

```powershell
Copy-Item "C:\Data\*" -Destination "D:\Backup" -Recurse
```

---

## 🔄 Kapan Menggunakan CMD vs PowerShell?

| CMD                                 | PowerShell                              |
| ----------------------------------- | --------------------------------------- |
| Tugas dasar (file, folder, program) | Otomatisasi kompleks & scripting modern |
| Kompatibilitas lama                 | Integrasi dengan sistem dan cloud       |
| Scripting cepat, ringan             | Debugging, logging, manajemen sistem    |

---
