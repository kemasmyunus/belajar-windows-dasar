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
