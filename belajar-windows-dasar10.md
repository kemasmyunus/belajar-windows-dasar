## Pengenalan Batch Script

**Batch Script** adalah kumpulan perintah CMD yang disimpan dalam file dengan ekstensi `.bat` atau `.cmd`. Ketika dijalankan, file ini akan mengeksekusi semua perintah di dalamnya secara berurutan.

Contoh isi file `halo.bat`:

```bat
@echo off
echo Halo, dunia!
pause
```

Keterangan:

* `@echo off` : Menyembunyikan perintah agar yang terlihat hanya output-nya.
* `echo` : Menampilkan teks.
* `pause` : Menunggu hingga user menekan tombol sebelum menutup jendela.

---

## Menjalankan Batch File

1. Simpan file dengan ekstensi `.bat`, contoh: `halo.bat`.
2. Klik dua kali file tersebut, atau jalankan lewat CMD:

   ```bash
   halo.bat
   ```

---

## Variabel di CMD

CMD mendukung variabel sederhana.

Contoh:

```bat
@echo off
set nama=Andi
echo Halo %nama%
pause
```

Keluaran:

```
Halo Andi
```

---

## Input dari Pengguna

Gunakan `set /p` untuk meminta input dari pengguna.

Contoh:

```bat
@echo off
set /p nama=Siapa nama kamu? 
echo Halo %nama%
pause
```

---

## Struktur Kendali (If, Goto)

CMD juga mendukung struktur logika dasar.

### IF

```bat
@echo off
set /p nilai=Masukkan nilai: 
if %nilai% GEQ 75 (
    echo Lulus!
) else (
    echo Tidak lulus!
)
pause
```

### GOTO

```bat
@echo off
goto menu

:menu
echo === Menu Utama ===
echo 1. Mulai
echo 2. Keluar
pause
```

---

## Looping dengan FOR

CMD mendukung perulangan melalui perintah `FOR`.

Contoh:

```bat
@echo off
for %%i in (1 2 3 4 5) do (
    echo Nomor: %%i
)
pause
```

---

## Contoh Program Sederhana

**Program Batch: Kalkulator Penjumlahan**

```bat
@echo off
set /p a=Masukkan angka pertama: 
set /p b=Masukkan angka kedua: 
set /a hasil=%a% + %b%
echo Hasil: %hasil%
pause
```

---

## Kesimpulan

Dengan menguasai dasar CMD dan scripting batch, kamu bisa:

* Membuat tool otomatis sederhana.
* Mempermudah tugas rutin seperti backup, pembersihan folder, atau pengaturan sistem.
* Membangun fondasi untuk belajar scripting yang lebih canggih (PowerShell, Bash, Python, dll).

---
