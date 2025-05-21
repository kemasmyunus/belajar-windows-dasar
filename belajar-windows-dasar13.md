# 🧠 Belajar PowerShell Dasar: Modul Pemula

---

## 📌 Apa Itu PowerShell?

**PowerShell** adalah *command-line shell* dan *bahasa scripting* berbasis .NET yang:

* Bisa memproses **objek**, bukan cuma teks.
* Memiliki **banyak cmdlet** (command-let) bawaan.
* Digunakan untuk mengelola sistem Windows, jaringan, file, registry, dan lainnya.

---

## 🚀 Membuka PowerShell

### Cara membuka:

* Tekan `Windows + X` → pilih **Windows PowerShell** atau **Windows Terminal**.
* Ketik `powershell` di Start Menu → klik kanan → "Run as administrator".
* Jalankan `powershell` dari CMD untuk masuk ke PowerShell.

---

## 🛠️ Cmdlet PowerShell Dasar

| Cmdlet                    | Fungsi                   |
| ------------------------- | ------------------------ |
| `Get-Help`                | Menampilkan bantuan      |
| `Get-Command`             | Menampilkan semua cmdlet |
| `Get-ChildItem` atau `ls` | Melihat isi folder       |
| `Set-Location` atau `cd`  | Pindah folder            |
| `Copy-Item`               | Menyalin file/folder     |
| `Move-Item`               | Memindahkan file/folder  |
| `Remove-Item`             | Menghapus file/folder    |
| `New-Item`                | Membuat file atau folder |
| `Clear-Host` atau `cls`   | Membersihkan layar       |

---

## 📁 Contoh Navigasi File

```powershell
Set-Location -Path "C:\Users\Public"
Get-ChildItem
```

atau bisa singkat:

```powershell
cd "C:\Users\Public"
ls
```

---

## 🧪 Variabel di PowerShell

```powershell
$nama = "Andi"
Write-Output "Halo, $nama"
```

---

## 📥 Input dari Pengguna

```powershell
$umur = Read-Host "Masukkan umur Anda"
Write-Output "Umur kamu adalah $umur tahun"
```

---

## 🧠 Struktur Logika Dasar

### IF Statement

```powershell
$nilai = Read-Host "Masukkan nilai"
if ($nilai -ge 75) {
    Write-Output "Lulus"
} else {
    Write-Output "Tidak lulus"
}
```

---

### FOR dan FOREACH

```powershell
for ($i = 1; $i -le 5; $i++) {
    Write-Output "Angka: $i"
}
```

```powershell
$buah = @("apel", "jeruk", "pisang")
foreach ($item in $buah) {
    Write-Output "Buah: $item"
}
```

---

## 💡 Perbedaan Utama PowerShell vs CMD

| Fitur                  | CMD              | PowerShell                      |
| ---------------------- | ---------------- | ------------------------------- |
| Dukungan Object        | ❌ Tidak ada      | ✅ Mendukung objek penuh         |
| Scripting              | Dasar saja       | Sangat fleksibel dan kompleks   |
| Output Bisa Diproses   | Tidak            | Bisa filter, sort, export       |
| Modul Tambahan         | Tidak            | Ada banyak modul bisa di-import |
| Digunakan Profesional? | Untuk dasar saja | Dipakai SysAdmin & DevOps       |

---
