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
![image](https://user-images.githubusercontent.com/40049149/186733186-e5587ea2-952a-4372-baca-74f5592abac8.png)

8. Cek __koneksi__ ke Github dengan command berikut

        ssh -T git@github.com
        
![image](https://user-images.githubusercontent.com/40049149/186733272-ffc2233e-b9d2-4b18-9597-8c4faa65e111.png)

