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

# **Bab 20: Mengakses API dengan PowerShell**

### **20.1 Mengambil Data dari API**
Contoh ambil data dari API publik:
```powershell
$response = Invoke-RestMethod -Uri "https://api.agify.io/?name=andi"
$response
```

Output bisa seperti:
```json
{
  "name": "andi",
  "age": 33,
  "count": 1200
}
```

### **20.2 Mengirim Data ke API**
```powershell
$body = @{
  name = "andi"
  age = 25
} | ConvertTo-Json

Invoke-RestMethod -Uri "https://example.com/api" `
                  -Method POST `
                  -Body $body `
                  -ContentType "application/json"
```

---

# **Bab 21: PowerShell dan Database**

### **21.1 Koneksi ke SQL Server**
```powershell
$connectionString = "Server=localhost;Database=TestDB;Integrated Security=True;"
$query = "SELECT * FROM Users"

$connection = New-Object System.Data.SqlClient.SqlConnection
$connection.ConnectionString = $connectionString
$connection.Open()

$command = $connection.CreateCommand()
$command.CommandText = $query

$reader = $command.ExecuteReader()
while ($reader.Read()) {
    Write-Output $reader["Username"]
}
$connection.Close()
```

> Cocok buat admin sistem yang butuh akses langsung ke database internal.

---
