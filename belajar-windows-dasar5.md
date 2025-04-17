# **Bab 18: PowerShell untuk Otomatisasi Sistem**

### **18.1 Mengecek Kapasitas Drive Secara Otomatis**
```powershell
Get-PSDrive -PSProvider 'FileSystem' |
Select-Object Name, @{Name='Free(GB)';Expression={"{0:N2}" -f ($_.Free/1GB)}}, @{Name='Used(GB)';Expression={"{0:N2}" -f (($_.Used)/1GB)}}
```

### **18.2 Menyimpan Informasi Sistem ke File**
```powershell
Get-ComputerInfo | Out-File "info_sistem.txt"
```

### **18.3 Otomatisasi Pembersihan Temp Folder**
```powershell
$folder = "$env:TEMP"
Remove-Item "$folder\*" -Recurse -Force -ErrorAction SilentlyContinue
```

---

# **Bab 19: PowerShell dalam Dunia DevOps (CI/CD & Monitoring)**

### **19.1 Men-deploy Aplikasi Sederhana**
Contoh: Copy folder build web ke server lokal
```powershell
Copy-Item "C:\MyApp\dist\*" -Destination "\\Server\webapp\" -Recurse -Force
```

### **19.2 Notifikasi Otomatis lewat Email**
```powershell
Send-MailMessage -From "admin@domain.com" `
                 -To "tim@domain.com" `
                 -Subject "Backup Berhasil" `
                 -Body "Backup selesai jam $(Get-Date)" `
                 -SmtpServer "smtp.domain.com"
```

> ⚠️ Butuh SMTP server aktif dan konfigurasi autentikasi tambahan jika pakai layanan seperti Gmail.

---
