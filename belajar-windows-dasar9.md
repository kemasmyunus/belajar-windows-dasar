## Menyimpan Output CMD ke File

Kadang kamu ingin menyimpan hasil perintah CMD ke dalam file teks, contohnya untuk dokumentasi atau troubleshooting.

Contoh:

```bash
dir > daftar.txt
```

Artinya: Menyimpan hasil dari perintah `dir` ke file `daftar.txt` di folder saat ini.

Jika ingin menambahkan hasil ke file yang sudah ada:

```bash
dir >> daftar.txt
```

---

## Mengetahui Informasi Sistem

Beberapa perintah berguna untuk melihat informasi sistem:

| Perintah          | Fungsi                                  |
| ----------------- | --------------------------------------- |
| `systeminfo`      | Menampilkan informasi sistem lengkap    |
| `ipconfig`        | Melihat alamat IP dan info jaringan     |
| `tasklist`        | Menampilkan daftar proses yang berjalan |
| `hostname`        | Menampilkan nama komputer               |
| `echo %username%` | Menampilkan nama user yang aktif        |

---

## Menggunakan Bantuan CMD

Kalau kamu bingung fungsi suatu perintah, gunakan perintah `help`:

```bash
help
```

Untuk melihat daftar perintah dasar.

Atau gunakan:

```bash
help nama_perintah
```

Contoh:

```bash
help copy
```

Atau juga bisa:

```bash
perintah /?
```

Contoh:

```bash
xcopy /?
```

---

## Menjalankan CMD Sebagai Administrator

Beberapa perintah hanya bisa dijalankan dengan hak administrator. Untuk membuka CMD sebagai admin:

1. Klik Start Menu.
2. Ketik `cmd`.
3. Klik kanan → pilih **"Run as administrator"**.

CMD akan menampilkan label `Administrator:` di bagian atas jendela jika berhasil.

---

## CMD vs PowerShell vs Windows Terminal

* **CMD**: Interpreter baris perintah klasik, ringan, dan cocok untuk tugas dasar.
* **PowerShell**: Lebih canggih, mendukung scripting kompleks dan objek.
* **Windows Terminal**: Aplikasi baru yang mendukung tab, tema, dan bisa menjalankan CMD, PowerShell, dan WSL sekaligus.

---

## Penutup

CMD adalah alat yang kuat meskipun tampak sederhana. Dengan memahami perintah dasarnya, kamu bisa:

* Mengelola file dan folder lebih cepat.
* Melakukan troubleshooting sistem.
* Mempelajari pemrograman dan scripting lebih lanjut.

---
