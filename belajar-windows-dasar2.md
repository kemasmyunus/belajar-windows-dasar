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

# **Bab 6: Tips dan Trik PowerShell**

### **6.1 Menggunakan Tab untuk Autocomplete**
Tekan `Tab` untuk melengkapi nama perintah, file, atau parameter secara otomatis.

### **6.2 Membaca Bantuan**
PowerShell menyediakan dokumentasi internal:
```powershell
Get-Help Get-Process
```

Untuk menampilkan contoh penggunaan:
```powershell
Get-Help Get-Process -Examples
```

### **6.3 Menyimpan Output ke File**
Simpan hasil perintah ke file teks:
```powershell
Get-Process > proses.txt
```

---

# **Bab 7: Praktik Mini Proyek**

### **7.1 Proyek: Backup Otomatis Folder**
Skrip untuk mencadangkan folder:
```powershell
$folderAsal = "C:\Data"
$folderTujuan = "D:\Backup\Data_$(Get-Date -Format yyyyMMdd)"
Copy-Item $folderAsal -Destination $folderTujuan -Recurse
Write-Output "Backup selesai ke $folderTujuan"
```

### **7.2 Proyek: Monitor Koneksi Internet**
```powershell
while ($true) {
    $ping = Test-Connection -ComputerName google.com -Count 1 -Quiet
    if ($ping) {
        Write-Output "$(Get-Date): Koneksi OK"
    } else {
        Write-Output "$(Get-Date): Koneksi Terputus"
    }
    Start-Sleep -Seconds 5
}
```

---

# **Penutup**
Dengan penguasaan CMD dan PowerShell, pengguna Windows bisa lebih produktif, memahami sistem lebih dalam, dan bahkan mengotomatisasi tugas-tugas harian secara efisien. Terus eksplorasi dan praktik untuk mengembangkan keterampilan!
