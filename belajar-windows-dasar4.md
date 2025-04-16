# **Bab 13: Integrasi PowerShell dengan Git**

### **13.1 Mengecek Git dari PowerShell**
Pastikan Git sudah diinstal dan bisa diakses dari PowerShell:
```powershell
git --version
```

### **13.2 Perintah Git Dasar di PowerShell**
| Perintah | Fungsi |
|---|---|
| `git init` | Membuat repo Git baru |
| `git clone <url>` | Mengunduh repo dari GitHub |
| `git status` | Melihat status file |
| `git add .` | Menambahkan semua perubahan |
| `git commit -m "pesan"` | Menyimpan perubahan |
| `git push` | Mengunggah ke GitHub |

### **13.3 Tips Git di PowerShell**
Agar terminal menampilkan branch Git aktif, gunakan [posh-git](https://github.com/dahlbyk/posh-git):
```powershell
Install-Module posh-git -Scope CurrentUser
Import-Module posh-git
```

---

# **Bab 14: PowerShell Remoting (Akses Jarak Jauh)**

### **14.1 Apa itu PowerShell Remoting?**
PowerShell Remoting memungkinkan kita menjalankan perintah di komputer lain melalui jaringan.

### **14.2 Mengaktifkan PowerShell Remoting**
Jalankan di komputer target:
```powershell
Enable-PSRemoting -Force
```

### **14.3 Mengakses Komputer Jarak Jauh**
```powershell
Enter-PSSession -ComputerName NAMA_KOMPUTER -Credential (Get-Credential)
```

Keluar dari sesi:
```powershell
Exit-PSSession
```

---

# **Bab 15: Pengenalan PowerShell Profile dan Kustomisasi**

### **15.1 Membuka Profil PowerShell**
```powershell
notepad $PROFILE
```

### **15.2 Contoh Isi Profile**
```powershell
Import-Module posh-git
Set-Alias gs git status
Set-Alias gc git commit
function salam {
    Write-Output "Selamat datang, $(whoami)!"
}
salam
```

### **15.3 Otomatisasi Kustom Terminal**
- Tambahkan alias
- Tema prompt
- Modul yang sering digunakan

---

# **Bab 16: Keamanan dan Praktik Baik PowerShell**

### **16.1 Execution Policy**
Cek kebijakan eksekusi:
```powershell
Get-ExecutionPolicy
```

Ubah agar bisa jalankan skrip:
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### **16.2 Tips Keamanan**
- Jangan jalankan skrip dari sumber tidak dikenal
- Selalu baca isi skrip sebelum eksekusi
- Gunakan `-WhatIf` untuk simulasi tanpa efek:
```powershell
Remove-Item C:\Data\* -Recurse -WhatIf
```

---
