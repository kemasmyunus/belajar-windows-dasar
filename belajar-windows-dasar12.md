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
