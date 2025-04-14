# **Bab 4: Pengelolaan File Lanjutan**

### **4.1 Menyalin dan Memindahkan File**
| Perintah | Fungsi |
|---|---|
| `copy <sumber> <tujuan>` | Menyalin file (CMD) |
| `Move-Item <sumber> <tujuan>` | Memindahkan atau mengganti nama file/folder (PowerShell) |
| `Copy-Item <sumber> <tujuan>` | Menyalin file atau folder (PowerShell) |

Contoh PowerShell:
```powershell
Copy-Item "C:\Data\file.txt" -Destination "D:\Backup\"
```

### **4.2 Menghapus File dan Folder**
| Perintah | Fungsi |
|---|---|
| `del <file>` | Menghapus file (CMD) |
| `Remove-Item <file/folder>` | Menghapus file/folder (PowerShell) |

Contoh PowerShell:
```powershell
Remove-Item "D:\Backup\file.txt"
```

### **4.3 Menangani File Secara Rekursif**
Untuk bekerja dengan file dalam subfolder:
```powershell
Get-ChildItem -Recurse
Remove-Item -Recurse -Force "C:\Folder\"
```

---

# **Bab 5: Pengenalan Alias dan Fungsi di PowerShell**

### **5.1 Alias di PowerShell**
Alias adalah nama pendek dari perintah PowerShell.

| Alias | Perintah Asli |
|---|---|
| `ls` | `Get-ChildItem` |
| `rm` | `Remove-Item` |
| `mv` | `Move-Item` |
| `cp` | `Copy-Item` |

Cek alias dengan:
```powershell
Get-Alias
```

### **5.2 Membuat Fungsi Sederhana**
Contoh fungsi untuk menyapa:
```powershell
function Sapa($nama) {
    Write-Output "Halo, $nama!"
}
Sapa "Andi"
```

---
