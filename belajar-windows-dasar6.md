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
