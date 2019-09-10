### Praktikum Minggu 01 (175410158 / Syaiful Mustafa)

#### 1. Git Version
Pastikan bahwa Git sudah terinstall, dapat kita cek melalui Microsoft Powershell, kemudian mengetikkan perintah ```git --version```
![alt text](./pic01.PNG "Git version")

#### 2. Konfigurasi Git
Lakukan konfigurasi User dan Email menggunakan perintah
```
git config --global user.name "Syaiful Mustafa"
git config --global user.email sfmusta@gmail.com
```
Pastikan bahwa konfigurasi sudah sesuai menggunakan perintah ``` git config --list ```
![alt text](./pic02.PNG "Git config")

#### 3. Buat Repository di Github
Akses https://github.com lalu buat repository baru dengan nama **tcc**, klik tombol Create Repository
![alt text](./pic03.PNG "Buat Repository")
salin alamat repository git yang baru saja kita buat
![alt text](./pic04.PNG "Repository")

#### 4. Jalankan Git client
Untuk mempermudah, kita akan menggunakan **Visual Studio Code** sebagai git client

Tekan tombol ```Ctrl``` + ```~``` , maka terminal akan tertampil
![alt text](./pic05.PNG "Repository")

jalankan perintah untuk clone repo
```
git clone https://github.com/sfmusta/tcc.git

```
buat folder minggu-01 dibawah tcc
```
cd tcc
md minggu-01
cd minggu-01
```
isi folder minggu-01 dengan file **README.md** ini
![alt text](./pic07.PNG "Repository")

#### 5. Push Repository
jalankan perintah untuk menambahkan file apa saja yang akan ditambahkan
```
git add -A
```
lihat status
```
git status
```
![alt text](./pic08.PNG "Repository")
commit perubahan
```
git commit -m "tambah repo minggu-01"
```
![alt text](./pic09.PNG "Repository")
lalu push ke github
ketik perintah 
```
git push origin master
```
Muncul windows login
![alt text](./pic10.PNG "Repository")
Jika berhasil nanti akan seperti ini
![alt text](./pic11.PNG "Repository")