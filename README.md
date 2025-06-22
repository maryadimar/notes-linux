# Perintah Dasar Linux

Berikut adalah daftar perintah dasar Linux beserta penjelasan dan contoh penggunaannya:

## 1. Mengetahui Posisi Path Saat Ini
- **Perintah**: `pwd`
- **Output**: `/Users/userx/Documents/`

## 2. Menampilkan Isi Folder
- **Perintah**: `ls`
- **Output**: Menampilkan file atau folder di dalam direktori saat ini.

## 3. Menampilkan Semua File (Termasuk yang Tersembunyi)
- **Perintah**: `ls -a`
- **Output**: Menampilkan semua file/folder, termasuk yang tersembunyi (diawali dengan titik, misal `.git`).
- **Catatan**: File/folder tersembunyi tidak tampil dengan `ls` biasa, tetapi muncul dengan flag `-a`.

## 4. Masuk ke Dalam Folder
- **Perintah**: `cd <nama_folder>`
- **Contoh**: `cd Documents`

## 5. Membuat File
- **Perintah**: `touch <nama_file>`
- **Contoh**: `touch contoh_nama_file.txt`

## 6. Menulis atau Mengedit File
- **Perintah**: `nano <nama_file>`
- **Contoh**: `nano contoh_nama_file.txt`
- **Catatan**: Memungkinkan penulisan seperti di notepad. Simpan dengan `Ctrl+O`, keluar dengan `Ctrl+X`.

## 7. Mencari Kata dalam File
- **Perintah**: `grep <kata> <nama_file>`
- **Contoh**: `grep apel buah.txt`
- **Penjelasan**: Mencari kata `apel` dalam file `buah.txt`.

### Flag untuk `grep`:
- **`-i`**: Mengabaikan huruf besar/kecil.
  - **Contoh**: `grep -i Apel buah.txt`
- **`-n`**: Menampilkan nomor baris tempat kata ditemukan.
  - **Contoh**: `grep -n Apel buah.txt`
  - **Kombinasi**: `grep -n -i apel buah.txt`
- **`-r`**: Pencarian rekursif di semua folder dan subfolder.
  - **Contoh**: `grep -r "apel" .`
  - **Penjelasan**: Mencari kata `apel` di semua file mulai dari direktori saat ini (`.`).

## 8. Menggunakan Pipeline (`|`)
- **Perintah**: `<perintah1> | <perintah2>`
- **Contoh**: `ls -a | grep txt`
- **Penjelasan**: Menampilkan semua file/folder (termasuk tersembunyi) lalu memfilter yang mengandung kata `txt`.

## 9. Mencari File dengan `find`
- **Format**: `find <lokasi_awal> <kriteria> <aksi>`
- **Contoh**:
  - `find . -name buah.txt`: Mencari file bernama `buah.txt` di direktori saat ini.
  - `find /home/users/Documents -name "file_yang_dicari.txt"`: Mencari file di lokasi spesifik.
  - `find . -iname "file.txt"`: Mengabaikan huruf besar/kecil.
  - `find /home/kamu -type d -name "project"`: Mencari folder bernama `project`.
  - `find /home/kamu -type f -name "*.txt"`: Mencari semua file berekstensi `.txt`.
  - `find . -type f -mtime -1`: Mencari file yang diubah dalam 1 hari terakhir.
  - `find . -type f -mtime +5`: Mencari file yang dibuat lebih dari 5 hari lalu.
  - `find . -type f -size +10M`: Mencari file berukuran lebih dari 10MB.
  - `find . -type f -perm 0777`: Mencari file dengan izin akses `0777`.
  - `find . -type f -name "*.log" -size +5M`: Mencari file `.log` berukuran lebih dari 5MB.
  - `find . -type f -name "*.php" -exec chmod 644 {} \;`: Mengubah izin file `.php` menjadi `644`.
  - `find . -type f -name "*.sh" -exec mv {} backup_scripts \;`: Memindahkan file `.sh` ke folder `backup_scripts`.

- **Catatan**: 
  - Gunakan `-p` saat membuat folder (`mkdir -p backup_scripts`) untuk menghindari error jika folder sudah ada.
  - `{}` mewakili file yang ditemukan, dan `\;` menutup perintah `-exec`.

## 10. Membuat Folder
- **Perintah**: `mkdir <nama_folder>`
- **Contoh**: `mkdir contoh_nama_folder`

## 11. Menghapus File
- **Perintah**: `rm <nama_file>`
- **Contoh**: `rm contoh_nama_file.txt`

## 12. Menghapus Folder
- **Perintah**: `rmdir <nama_folder>`
- **Contoh**: `rmdir contoh_nama_folder`
- **Catatan**: Folder harus kosong untuk dapat dihapus.

## 13. Mengetahui Pengguna yang Sedang Login
- **Perintah**: `who`
- **Penjelasan**: Menampilkan daftar pengguna yang sedang login.

---

**Catatan Tambahan**:
- Gunakan perintah dengan hati-hati, terutama `rm` dan `rmdir`, karena data yang dihapus tidak dapat dikembalikan.
- Untuk informasi lebih lanjut tentang perintah, gunakan `man <perintah>` (contoh: `man grep`).