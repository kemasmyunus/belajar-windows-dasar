# **Bab 8: PowerShell dan Manajemen Proses**

### **8.1 Melihat Proses yang Berjalan**
Gunakan `Get-Process` untuk melihat semua proses:
```powershell
Get-Process
```

Filter proses berdasarkan nama:
```powershell
Get-Process -Name chrome
```

### **8.2 Menghentikan Proses**
Hentikan proses dengan `Stop-Process`:
```powershell
Stop-Process -Name notepad
```

Atau berdasarkan ID proses:
```powershell
Stop-Process -Id 1234
```

### **8.3 Menjalankan Aplikasi dari PowerShell**
Jalankan aplikasi dengan:
```powershell
Start-Process notepad
Start-Process "C:\Path\to\file.txt"
```

---

# **Bab 9: Otomatisasi Tugas Jadwal (Task Scheduler)**

### **9.1 Membuat Tugas Terjadwal lewat CMD**
```cmd
schtasks /create /tn "BackupData" /tr "powershell.exe -File D:\script\backup.ps1" /sc daily /st 08:00
```

### **9.2 Melihat dan Menghapus Tugas**
```cmd
schtasks /query
schtasks /delete /tn "BackupData"
```

---
