# Ubuntu & Git

## INSTALL UBUNTU DUAL BOOT ALONGSIDE WINDOWS
1. for complete tutorial view this tutorial on youtube
[VIEW TOTORIAL](https://youtu.be/vaEYeQkTgzQ?si=LReSMUBBTf4cnAzJ)

3. we recommend you to install Ubuntu 22.0
4. if any issue occours about installation u can come to sekre bayucaraka for help 	

## Ubuntu Basic Command
Berikut adalah beberapa perintah atau command yang umum digunakan pada sistem operasi Linux.

> Catatan: contoh yang digunakan di sini berbasis shell `bash` pada distribusi Ubuntu.

### **Perintah Navigasi File dan Direktori**

| Command            | Usage                               |
| ------------------ | ----------------------------------- |
| `cd`               | pindah direktori                    |
| `ls`               | melihat isi direktori               |
| `ll`               | melihat isi direktori dengan detail |
| `pwd`              | melihat direktori aktif             |
| `find <nama file>` | mencari file                        |
| `locate`           | mencari file                        |

**Contoh latihan:**
- Pindah ke direktori home: `cd ~`
- Lihat isi direktori saat ini dalam bentuk list: `ls -lah`
- Cari file bernama `README.md` mulai dari direktori saat ini: `find . -name "README.md"`

### **Perintah Manipulasi File dan Direktori**

| Command               | Usage                  |
| --------------------- | ---------------------- |
| `cp <asal> <tujuan>`  | menyalin file          |
| `mv <asal> <tujuan>`  | memindahkan file       |
| `rm <file>`           | menghapus file         |
| `rmdir <nama folder>` | menghapus folder       |
| `touch <file>`        | membuat file           |
| `mkdir <nama folder>` | membuat folder         |
| `cat`                 | melihat isi file       |
| `echo`                | menampilkan baris teks |
| `nano <nama file>`          | membuka dan mengedit file di nano editor |

**Contoh latihan:**
- Buat folder `projek-pertama` kemudian masuk ke dalamnya.
- Buat file `main.py` kosong dengan `touch main.py` lalu isi dengan editor favoritmu.
- Salin file `main.py` menjadi `main_backup.py` lalu hapus kembali `main_backup.py`.

> Tips keamanan: hati-hati menggunakan `rm -rf` karena bisa menghapus banyak file tanpa konfirmasi.

### **Perintah User dan Permission**

| Command           | Usage                                     |
| ----------------- | ----------------------------------------- |
| `sudo <perintah>` | melakukan perintah lain dengan super user |
| `su`              | mengganti user                            |
| `passwd`          | mengganti password                        |
| `who`             | menampilkan user                          |
| `chmod`           | mengganti hak akses                       |
| `chown`           | mengganti hak milik                       |

**Hal penting untuk programmer:**
- Saat menjalankan skrip, kamu sering perlu memberi hak eksekusi: `chmod +x script.sh`.
- Untuk menjalankan file Python biasanya cukup: `python3 script.py` (tidak perlu `chmod`).

**Contoh latihan:**
- Buat file `hello.sh`, isi dengan `echo "Hello"`, lalu ubah agar bisa dieksekusi dan jalankan.

### **Perintah Lainnya**

| Command                     | Usage                        |
| --------------------------- | ---------------------------- |
| `history`                   | melihat riwayat perintah     |
| `grep`                      | mencari kata                 |
| `sort`                      | mengurutkan                  |
| `ps`                        | menampilkan proses berjalan  |
| `kill`                      | menghentikan program         |
| `tar`                       | mengumpulkan file            |
| `zip`                       | mengkompres file             |
| `unzip`                     | mengekstrak file             |
| `ssh`                       | akses jarak jauh             |
| `ifconfig`                  | melihat ip                   |
| `date`                      | menampilkan tanggal          |
| `clear`                     | membersihkan terminal        |

**Hal penting untuk debugging:**
- `history | grep <kata>` untuk mencari perintah yang pernah kamu jalankan.
- `ps aux | grep python` untuk melihat proses Python yang sedang berjalan.
- `grep -R "teks" .` untuk mencari teks di dalam banyak file (sangat berguna untuk cari kode).

---

### **Perintah yang Sering Dipakai Programmer**

Bagian ini merangkum command yang sangat sering dipakai saat ngoding di Linux.

#### Manajemen Paket & Environment

Tergantung bahasa pemrograman yang kamu pakai, tetapi pola dasarnya mirip.

**APT (Ubuntu):**

- `sudo apt update` — memperbarui daftar paket.
- `sudo apt upgrade` — memperbarui paket yang terinstal.
- `sudo apt install <nama-paket>` — menginstal paket baru.

**Python:**

- `python3 --version` — cek versi Python.
- `python3 -m venv venv` — membuat virtual environment bernama `venv`.
- `source venv/bin/activate` — mengaktifkan virtual environment.
- `pip install <package>` — menginstal library Python.

#### Bekerja dengan File Kode

- `head <file>` — melihat beberapa baris pertama file.
- `tail <file>` — melihat beberapa baris terakhir file.
- `tail -f <logfile>` — memantau log secara real-time (penting untuk debugging).

#### Monitoring Sistem Saat Development

- `top` atau `htop` (jika diinstal) — melihat penggunaan CPU/memori.
- `df -h` — melihat penggunaan disk.
- `du -sh <folder>` — melihat ukuran suatu folder.

---

### **Latihan: Membuat Script Bash Sederhana**

Pada latihan ini kamu akan membuat file bash yang menjalankan beberapa perintah dasar.

#### 1. Struktur dasar script bash

Script bash biasanya punya struktur minimal seperti ini:

```bash
#!/usr/bin/env bash

echo "Halo dari script bash!"
```

Penjelasan singkat:
- `#!/usr/bin/env bash` disebut *shebang*, untuk memberi tahu sistem bahwa file ini dijalankan dengan `bash`.
- Baris-baris di bawahnya adalah perintah yang sama seperti yang kamu ketik di terminal.

#### 2. Langkah membuat script `latihan.sh`

1. Pindah ke direktori kerja (misalnya `projek-pertama`):
	```bash
	cd ~/projek-pertama
	```
2. Buat file baru bernama `latihan.sh`:
	```bash
	touch latihan.sh
	```
3. Buka file tersebut dengan editor (misalnya `nano`):
	```bash
	nano latihan.sh
	```
4. Isi file dengan contoh script berikut:

	```bash
	#!/usr/bin/env bash

	echo "=== Info Direktori Saat Ini ==="
	pwd
	ls -lah

	echo
	echo "=== Membuat Folder logs (jika belum ada) ==="
	mkdir -p logs

	echo
	echo "=== Menyimpan daftar file ke logs/files.txt ==="
	ls -lah > logs/files.txt

	echo
	echo "Selesai. Cek isi folder logs/ dan file files.txt"
	```

5. Simpan dan keluar dari editor (`Ctrl+O`, `Enter`, lalu `Ctrl+X` jika menggunakan `nano`).

#### 3. Memberi izin eksekusi dan menjalankan script

1. Beri hak eksekusi pada file script:
	```bash
	chmod +x latihan.sh
	```
2. Jalankan script dengan:
	```bash
	./latihan.sh
	```

Jika muncul error `Permission denied`, pastikan perintah `chmod +x latihan.sh` sudah dijalankan.

#### 4. Modifikasi latihan

Cobalah modifikasi script di atas, misalnya:
- Menampilkan tanggal saat ini dengan `date`.
- Menambahkan perintah `history | tail -5` untuk melihat 5 perintah terakhir.
- Menambahkan pesan jika folder `logs` sudah ada.

### **Notes**

Untuk detail dari tiap command, dapat menggunakan `--help` pada bagian belakang dari command seperti `<command> --help`.

Untuk dokumentasi yang lebih lengkap, kamu juga bisa pakai:
- `man <command>` — manual lengkap (misal: `man ls`).
- `info <command>` — dokumentasi alternatif jika tersedia.

## Git
### Getting & Creating Projects
| Command           | Usage                                      |
| ----------------- | ------------------------------------------ |
| `git init`        | initialize a local Git repository          |
| `git clone <url>` | create a local copy of a remote repository |

### Staging and Committing
| Command                            | Usage                             |
| ---------------------------------- | --------------------------------- |
| `git status`                       | check repository status           |
| `git add <filename>`               | add a file to the staging area    |
| `git add .`                        | add all files to the staging area |
| `git commit`                       | commit changes                    |
| git commit -m "[commit message](https://gist.github.com/nyancodeid/63f19941c81252bb0cca9c14497cf9f7#file-commit-message-md)" | commit changes & add a message |

### Branching
| Command                                              | Usage                                                                        |
| ---------------------------------------------------- | ---------------------------------------------------------------------------- |
| `git branch`                                         | display all local branches, current branch is indicated with an asterisk (*) |
| `git branch -a`                                      | display all branches (local and remote)                                      |
| `git branch <branch name>`                           | create a new branch                                                          |
| `git checkout -b <branch name>`                      | create a new branch and switch to it                                         |
| `git checkout -b <branch name> origin/<branch name>` | clone a remote branch and switch to it                                       |
| `git branch -m <old branch name> <new branch name>`  | rename a local branch                                                        |
| `git checkout <branch name>`                         | switch branch                                                                |

### Merging and Stashing
| Command                                     | Usage                                        |
| ------------------------------------------- | -----------                                  |
| `git merge <branch name>`                   | merge branch into the current branch         |
| `git merge <source branch> <target branch>` | merge branch into a target branch            |
| `git stash`                                 | stash current changes in a temporary storage |

### Remote Operations
| Command                                    | Usage                                                                      |
| ------------------------------------------ | -------------------------------------------------------------------------- |
| `git push origin <branch name>`            | push a branch to your remote repository                                    |
| `git push`                                 | push changes to remote repository                                          |
| `git pull`                                 | update the local repository with the latest changes from the remote branch |
| `git diff <source branch> <target branch>` | preview changes before merging                                             |

Made by **"bayucaraka programmer team"** © 2026
### [Commit Message Guidelines](https://gist.github.com/nyancodeid/63f19941c81252bb0cca9c14497cf9f7#file-commit-message-md)
