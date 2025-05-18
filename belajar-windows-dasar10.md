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
