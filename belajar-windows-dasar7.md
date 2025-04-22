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
