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

# **Bab 10: Menggunakan PowerShell untuk Administrasi Sistem**

### **10.1 Menambahkan Pengguna Baru**
```powershell
net user penggunaBaru password123 /add
```

### **10.2 Menambahkan ke Grup Administrator**
```powershell
net localgroup administrators penggunaBaru /add
```

### **10.3 Melihat Informasi Sistem**
```powershell
Get-ComputerInfo
```

---

# **Bab 11: Pengenalan Modul PowerShell**

### **11.1 Apa itu Modul?**
Modul adalah kumpulan fungsi dan perintah tambahan untuk PowerShell.

### **11.2 Mengimpor Modul**
```powershell
Import-Module <NamaModul>
```

### **11.3 Menginstal Modul Baru**
Untuk PowerShell 5.0+:
```powershell
Install-Module -Name Az
```

### **11.4 Melihat Modul Terinstal**
```powershell
Get-Module -ListAvailable
```

---

# **Bab 12: PowerShell dan File CSV/JSON**

### **12.1 Membaca File CSV**
```powershell
$csv = Import-Csv "data.csv"
$csv
```

### **12.2 Menyimpan ke File CSV**
```powershell
Get-Process | Export-Csv "proses.csv" -NoTypeInformation
```

### **12.3 Membaca dan Menulis JSON**
```powershell
# Membaca
$data = Get-Content "data.json" | ConvertFrom-Json

# Menulis
$data | ConvertTo-Json | Out-File "hasil.json"
```

---

# **Penutup Tambahan**
PowerShell sangat cocok untuk:
- Otomatisasi backup dan monitoring.
- Pengelolaan sistem dan jaringan.
- Pengolahan file data (CSV, JSON).
- Integrasi dengan tool lain (Git, Azure, dll.).

---
