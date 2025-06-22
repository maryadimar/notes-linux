- Perintah Dasar Linux:

* perintah untuk melihat kita berada dipath mana ?
-- `pwd`
--- outputnya : '/Users/userx/Documents/'

* perintah untuk menampilkan isi folder ?
-- `ls`
--- outputnya : bakal keluar file atau folder didalamnya

* perintah untuk menampilkan semua file termasuk yang disembunyikan ?
-- `ls -a`
--- outputnya : bakal keluar file atau folder serta yang disembunyikan
---- biasanya folder/file yang dihidden itu diawali dengan tanda titik didepan, misal .git
---- ketika ketik perintah ls folder .git tidak akan tampil tapi begitu tambahkan flag -a .git akan tampil

* perintah untuk masuk dalam folder ?
-- `cd` diikuti dengan nama folder
--- contoh : cd Documents

* perintah untuk membuat file ?
-- `touch` diikuti dengan nama file
--- contoh : touch contoh_nama_file.txt

* perintah untuk menulis file ?
-- `nano` diikuti dengan nama file
--- contoh : nano contoh_nama_file.txt
---- silahkan tulis sesuatu layaknya anda menulis di notepad

* perintah untuk mencari kata ?
-- `grep` diikuti dengan kata yang ingin dicari
--- contoh : grep apel buah.txt
---- disini saya contohkan mencari kata dalam sebuah file

* perintah untuk mencari kata dengan flag -i ?
-- `grep -i` diikuti dengan kata yang ingin dicari
--- contoh : grep -i Apel buah.txt
---- dengan adanya flag -i pencarian tidak memperdulikan huruf besar/kecil

* perintah untuk mencari kata dengan flag -n ?
-- `grep -n` diikuti dengan kata yang ingin dicari
--- contoh : grep -n Apel buah.txt
---- untuk mengetahui kata yang dicari ada dibaris ke berapa
----- btw kalai bisa kombinasi flag -n -i juga >> grep -n -i apel buah.txt

* perintah untuk mencari kata dengan flag -r ?
-- `grep -r` diikuti dengan kata yang ingin dicari
--- contoh : grep -r "apel" .
---- -r ➜ recursive (cari di semua folder dan subfolder)
---- ➜ "apel" kata yang dicari
---- ➜ . mulai dari folder saat ini
---- akan menampilkan file yang mengandung kata apel

* perintah menggunakan pipeline "|" sebagai penghubung ?
-- `|` kita manfaatkan dengan melakukan pencarian
--- contoh : ls -a | grep txt
---- maka outputnya tampilkan semua folder/file baik yang hidden atau tidak dilanjutkan dengan mencari file/folder yang mengandung kata txt

* perintah menggunakan find ?
-- `find [lokasi_awal] [kriteria] [aksi]` kita manfaatkan dengan melakukan pencarian
--- contoh : find . -name buah.txt
---- . ➜ cari mulai dari folder saat ini
---- -name ➜ kriteria nama file
---- "buah.txt" ➜ nama file yang dicari
---- bisa juga dengan find /home/users/Documents -name "file_yang_dicari.txt"
---- ganti -name dengan -iname agar mengabaikan huruf besar/kecil
---- find /home/kamu -type d -name "project" , hanya mencari type folder dengan nama folder project
---- find /home/kamu -type f -name "*.txt*" , hanaya mencari file berformat .txt
---- find . -type f -mtime -1 , cari type file yang diubah 1 hari terakhir
---- find . -type f -mtime +5 , cari type file yang dibuat 5 hari yang lalu
---- find . -type f -size +10M , cari type file yang berukuran > 10MB
---- find . -type f -perm 0777, cari file dengan permission 0777
---- find . -type f -name "*.log" -size +5M , cari file semua yang berformat .log yang ukurannya > 5M
---- find . -type f -name "*.php" -exec chmod 644 {} \; , cari semua file berformat .php dilanjutkan dengan memberikan akses permission 644, tanda {} mewakili file yang ditemukan, \; menutuo perintah
---- find . -type f -name "*.sh" -exec mv {} backup_scripts \; , cari semua file berformat .sh kemudian pindahkan ke folder backup_scripts, 
notes: untuk pembuatan folder backup_scripts nya menggunakan -p artinya membuat parent folder beserta parent folder nya sehingga ketika dilakukan pembuatan nama folder yang sama Tidak error kalau sudah ada

* perintah untuk membuat folder ?
-- `mkdir` diikuti dengan nama folder
--- mkdir : touch contoh_nama_folder

* perintah untuk menghapus file ?
-- `rm` diikuti dengan nama file
--- contoh : rm contoh_nama_file.txt

* perintah untuk menghapus folder ?
-- `rmdir` diikuti dengan nama folder
--- contoh : rmdir contoh_nama_folder
---- Hapus folder (harus kosong)

* perintah who ?
-- `who` untuk mengetahui user yang login saat ini