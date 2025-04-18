# **Bab 24: PowerShell untuk Backup Otomatis dan Pengelolaan File**

### **24.1 Backup Otomatis Folder Tertentu**

Backup folder `Dokumen` ke drive `D:` setiap hari:
```powershell
$source = "$env:USERPROFILE\Documents"
$destination = "D:\Backup\Documents_$(Get-Date -Format 'yyyyMMdd_HHmm')"

Copy-Item -Path $source -Destination $destination -Recurse -Force
```

### **24.2 Menghapus File Lama (Lebih dari 30 Hari)**
```powershell
$folder = "D:\Backup\Documents"
$limit = (Get-Date).AddDays(-30)

Get-ChildItem -Path $folder -Recurse |
Where-Object { $_.LastWriteTime -lt $limit } |
Remove-Item -Force
```

### **24.3 Menyimpan Log Backup**
```powershell
$logPath = "D:\Backup\log_backup.txt"
$logEntry = "$(Get-Date): Backup dari $source ke $destination berhasil.`n"
Add-Content -Path $logPath -Value $logEntry
```

### **24.4 Menjadwalkan Backup dengan Task Scheduler**
1. Buat skrip `backup.ps1` berisi perintah-perintah di atas.
2. Jalankan perintah ini via CMD untuk menjadwalkan:
```cmd
schtasks /create /tn "BackupHarian" /tr "powershell.exe -ExecutionPolicy Bypass -File D:\Script\backup.ps1" /sc daily /st 03:00
```

> 🔁 Backup berjalan otomatis setiap hari jam 03:00 pagi. Cocok buat server atau komputer kantor yang aktif 24 jam.

---
