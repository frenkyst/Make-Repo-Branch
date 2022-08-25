# Make-Repo-Branch

Menyiapkan environtment Git di Ubuntu

Konfigurasi user, email, dan SSH Key

1. Pastikan __git__ sudah terinstall dengan command:

        git --version

![image](https://user-images.githubusercontent.com/40049149/186727954-87f23a9c-cd15-4fa1-9041-0d8f7504d1fb.png)

2. Isikan __username__ dan __email__ github dengan command berikut (isi username dan email dengan benar)

        git config --global user.name "your.github-user.name"        
        git config --global user.email "your.github-user.email"
        git config --list
        
![image](https://user-images.githubusercontent.com/40049149/186728898-14625b5c-3be6-428c-a459-f84d171aa5f7.png)

3. Buat __private key__ dan __public key__ dengan command berikut:

        ssh-keygen

![image](https://user-images.githubusercontent.com/40049149/186729545-21c43575-3000-4152-80d6-131fd849bf13.png)

4. Buka file ~/.ssh/id_rsa.pub yang digenerate dari command __ssh-keygen__ sebelumnya. Copy isinya lalu simpan untuk sementara

        cat .ssh/id_rsa.pub

![image](https://user-images.githubusercontent.com/40049149/186731321-4b97a6a3-e628-4122-b4b1-feb468f044e0.png)

5. Buka [github.com](https://github.com/settings/keys)

![image](https://user-images.githubusercontent.com/40049149/186731274-d76e5838-fa74-4518-ad27-b0ba305e7637.png)

6. Pilih bagian SSH and GPG keys, lalu klik __New SSH Key__

![image](https://user-images.githubusercontent.com/40049149/186732335-198f9f7f-f975-4149-bb11-fc613e01224b.png)

7. Beri nama dan masukkan public key yang dicopy sebelumya ke kotak Key. Jika sudah klik __Add SSH Key__

![image](https://user-images.githubusercontent.com/40049149/186732608-76da5e05-74a8-4b87-8562-beebd1a8447b.png)

8. Jika Key sudah di tambahkan makan tampilannya seperti ini

![image](https://user-images.githubusercontent.com/40049149/186733186-e5587ea2-952a-4372-baca-74f5592abac8.png)

9. Cek __koneksi__ ke Github dengan command berikut

        ssh -T git@github.com
        
![image](https://user-images.githubusercontent.com/40049149/186733272-ffc2233e-b9d2-4b18-9597-8c4faa65e111.png)



### Membuat dan Mengisi Repository+Branch dengan Aplikasi

1. Masuk ke folder yang akan di upload ke github

![image](https://user-images.githubusercontent.com/40049149/186735356-a6b60977-40e0-429e-8f8f-515094645fd6.png)

2. Ketikkan command berikut. Command ini akan membuat folder .git di folder aplikasi

        touch file1 file2 file3
        git init

![image](https://user-images.githubusercontent.com/40049149/186737271-80c2d0b6-0cc6-4cd7-ac24-c211a43d4b01.png)

3. Sebelum upload, kita harus memilih file yang ingin kita upload. Kita akan membuat file .gitignore. File ini berisi file atau direktori yang tidak akan di upload. Contoh, kita tidak akan mengupload direktori node_modules

        touch .gitignore fileignore
        echo "fileignore" > .gitignore
        cat .gitignore

![image](https://user-images.githubusercontent.com/40049149/186737640-8326ecbf-c9df-4d4e-955d-4aa397ac9fe7.png)


4. Setelah itu, kita akan memilih __file__ yang akan kita upload. Ini akan membuat file memasuki fase staged dimana file siap untuk di commit(ditulis ke repository)

        git add .
        git status

![image](https://user-images.githubusercontent.com/40049149/186738923-7f138510-5e06-4f45-8e6c-7cf52199e2e8.png)

Jalankan __git status__ untuk mengecek apakah file sudah ditambahkan (ditandai dengan warna hijau)

5. Buka github, lalu buat repository baru dengan klik tanda + di pojok kanan atas memilih __New repository__ (Jika sudah membuat repo, skip ke step 7)

![image](https://user-images.githubusercontent.com/40049149/186738681-2661193c-769e-4892-95d3-cc98680f0b02.png)

6. Isikan nama repo lalu klik __create repository__ dibawah

![image](https://user-images.githubusercontent.com/40049149/186739134-ccccc37f-745a-4fbd-991c-394a5c024be4.png)

7. Pilih SSH, lalu copy baris berikut

![image](https://user-images.githubusercontent.com/40049149/186739574-7c007da0-d94c-4c58-af61-2c06824f7ccc.png)

Jika sudah membuat repository, klik code lalu pilih berikut

![image](https://user-images.githubusercontent.com/40049149/186739779-fa76b410-b7e4-4178-a4cd-c764de1bab80.png)

8. Buka terminal kembali, lalu isikan kode berikut

        git remote add origin git@github.com:frenkyst/deploy-nodejs-ubuntu.git
        git remote -v

![image](https://user-images.githubusercontent.com/40049149/186740229-c31853e5-cbf6-4023-9fbf-bb646d62b1af.png)

Cek dengan command __git remote -v__ untuk melihat daftar remote yang sudah terdaftar didalam repository lokal

9. Lakukan commit untuk menulis file kedalam repository lokal dengan command berikut

        git commit -m "penting komitmen"

![image](https://user-images.githubusercontent.com/40049149/186740547-69e7e808-adbb-44ba-a818-40101c921645.png)

10. Lakukan push untuk mengirim file yang berada di repository lokal ke repository github.

        git push origin master

![image](https://user-images.githubusercontent.com/40049149/186740875-a24755b9-8597-4ca1-9969-9b7f2323bec5.png)

Isikan <remote-name> dengan nama remote yang dibuat sebelumnya. <branch-name> secara default jika tidak disebutkan saat git init, akan menggunakan master

11. Jika kita cek di github, maka file yang kita buat sudah muncul

![image](https://user-images.githubusercontent.com/40049149/186741090-09bc0988-4a4b-42e1-9d6d-e7c3fd336a5d.png)

12. Buat branch baru dengan command berikut

        git branch develop

![image](https://user-images.githubusercontent.com/40049149/186741797-a0159c68-d10e-47e9-981a-3ca096e7ee41.png)

Lihat daftar branch yang sudah ada dengan command git branch -a

13. Saat ini kita masih di branch master. Untuk berpindah ke branch lain, gunakan command berikut

        git checkout develop

![image](https://user-images.githubusercontent.com/40049149/186741876-7bf270ef-7823-4ac9-9ef9-53274eddf543.png)

14. Lalu kita akan push branch tersebut ke github. Gunakan command berikut

        git push origin develop

![image](https://user-images.githubusercontent.com/40049149/186742423-bc2ec361-9802-409b-b1a0-805ffb7d2924.png)

15. Kita cek di github. Akan muncul branch baru beserta isinya
        
![image](https://user-images.githubusercontent.com/40049149/186742485-df1af723-a155-4fa3-affa-0962ad29a7b7.png)

