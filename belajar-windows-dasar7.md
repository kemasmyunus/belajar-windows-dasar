## **24.8 Praktik Lanjutan: Enkripsi Backup**

Untuk melindungi data sensitif, backup bisa dienkripsi menggunakan software pihak ketiga seperti 7-Zip yang bisa diotomatisasi lewat PowerShell:

```powershell
$zipPath = "$destination.zip"
$password = "RahasiaBanget123"
& "C:\Program Files\7-Zip\7z.exe" a -tzip -p$password $zipPath $source\*
```

> 🔐 Pastikan password disimpan aman atau gunakan credential vault.

---

## **24.9 Tips Keamanan dan Pemeliharaan**

- 🔒 **Gunakan folder backup di drive terpisah** agar tidak ikut hilang jika drive utama rusak.
- 📁 **Batasi akses folder backup** hanya untuk admin atau user tertentu.
- 📦 **Hapus backup lama secara berkala** agar tidak memenuhi storage.
- 🔄 **Uji restore secara rutin** untuk memastikan backup valid.

---

## **24.10 Troubleshooting Umum**

| Masalah | Penyebab Umum | Solusi |
|--------|----------------|--------|
| File tidak ter-copy | Izin akses | Jalankan PowerShell sebagai Administrator |
| Jadwal tidak berjalan | Path atau policy salah | Gunakan `-ExecutionPolicy Bypass` |
| Backup overwrite | Nama folder tidak unik | Gunakan `$(Get-Date -Format ...)` dalam nama |
| Backup gagal | File sedang digunakan | Gunakan Volume Shadow Copy atau backup saat idle |

---

## **24.11 Penutup dan Referensi Tambahan**

PowerShell adalah alat yang sangat powerful untuk:

- 🛠️ Automatisasi backup
- 🧹 Manajemen file berskala besar
- 🕒 Penjadwalan rutin tanpa campur tangan user

### 📚 Referensi Tambahan:
- [Microsoft Docs – PowerShell Scripting](https://learn.microsoft.com/powershell/)
- [7-Zip CLI Manual](https://sevenzip.osdn.jp/chm/cmdline/)
- Komunitas PowerShell di StackOverflow dan Reddit

---

### ✅ Rangkuman Singkat:
| Fitur | Perintah Kunci |
|------|----------------|
| Backup harian | `Copy-Item` |
| Auto zip | `Compress-Archive` atau `7z.exe` |
| Pembersihan otomatis | `Remove-Item` + `Where-Object` |
| Logging | `Add-Content` |
| Penjadwalan | `schtasks /create` |

---
