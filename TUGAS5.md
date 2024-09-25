#TUGAS 5


**1. Eksekusi seluruh profile yang ada :**


a. Edit file profile /etc/profile dan tampilkan pesan sebagai berikut :

    echo “Profile dari /etc/profile”

![1 a 1](https://github.com/user-attachments/assets/70922af4-d532-48d3-bcfb-f298d7a25f89)


![1 a 2](https://github.com/user-attachments/assets/370630b6-9608-4471-8feb-1c3d6a3a799d)


b. Asumsi nama anda stD02001, maka edit semua profile yang ada yaitu :

   
    /home/stD02001/.bash_profile 
    /home/. stD02001/.bash_login 
    /home/mahasiswa/.profile 
    /home/mahasiswa/.bashrc

   
Ganti nama /home/mahasiswa dengan nama anda sendiri. Pada setiap 
file tersebut, cantumkan instruksi echo, misalnya pada /home/ mahasiswa/.bash_profile : 

    echo “Profile dari .bash_profile”
  

Disini saya memakai 2 user account sendiri, yakni satu dengan nama "angga"🤖 dan satunya "guest"🙍‍♂️


![1 b 1](https://github.com/user-attachments/assets/7ae785c9-4263-4fbf-a204-008c9f3fd53d)

    nano /home/angga/.bash_profile
![1 b 2](https://github.com/user-attachments/assets/e0d7f8c4-2006-4f40-8056-8ae1d6e59b37)
    
    nano /home/angga/.bash_login
![1 b 3](https://github.com/user-attachments/assets/cf4570d6-0f21-4893-b31a-761867444554)

    nano /home/guest/.profile
![1 b 4](https://github.com/user-attachments/assets/06b45f5d-63fc-4b83-8ccd-2f23f6e21bb5)

    nano /home/guest/.bashrc
![1 b 5](https://github.com/user-attachments/assets/fd62b374-17e4-4be2-be93-15b01c2dd6fe)


c. Jalankan instruksi subtitute user, kemudian keluar dengan perintah exit sebagai berikut:

    $ su mahasiswa 
    $ exit
    
kemudian gunakan opsi – sebagai berikut :

    $ su – mahasiswa 
    $ exit
    
Jelaskan perbedaan kedua utilitas tersebut.

Jawab : perbedaan dari kedua Utilitas tersebut adalah pada :


    $ su mahasiswa
itu tidak memuat profil login pengguna baru, dan hanya mengganti pengguna saja.


sedangkan :

    $ su - mahasiswa
itu mengganti pengguna sekaligus memuat profil pengguna tersebut sehingga seperti benar benar login dari awal.


![1 c](https://github.com/user-attachments/assets/b9194fe8-de74-452e-a2a0-bf6cc9f274ac)


**2. Prompt String (PS)**

 
a. Edit file .bash_profile, ganti prompt PS1 dengan ‘>’. Instruksi export diperlukan dengan 
parameter nama variable tersebut, agar perubahan variable PS1 dikenal oleh semua shell

    PS1='>' 
    export PS1 
    
![2 a](https://github.com/user-attachments/assets/68457ca2-963b-4daf-ba1d-52bb1f5415ca)



b. Eksperimen hasil PS1 : 


command line dan keterangannya :


Mengubah prompt String menjadi urutan perintah :

    $ PS1=“\! > “ 

Mengubah prompt String menjadi tanggal :

    $ PS1=”\d > “ 
    
Mengubah prompt String menjadi waktu :

    $ PS1=”\t > “ 

Mengubah prompt String menjadi nama pengguna :

    $ PS1="\u > “ 

Mengubah prompt String menjadi dir saat ini :

    $ PS1=”\w >” 

    
Mengubah prompt String menjadi nama host :

    $ PS1="\h >”


![2 b](https://github.com/user-attachments/assets/a975fbc2-648b-491a-8fb1-e5bdfb85f540)


**3. Logout **

Edit file .bash_logout, tampilkan pesan dan tahan selama 5 detik, sebelum eksekusi logout

      Echo “Terima kasih atas sesi yang diberikan”
      Sleep 5 
      clear

![3](https://github.com/user-attachments/assets/a34895ac-2f6d-4840-a3d7-e5247923a169)


![3 5](https://github.com/user-attachments/assets/69422b2a-e55c-4c97-a09c-e47dbfeda5a4)


**4. Bash script**

   
a. Buat 3 buah script p1.sh, p2.sh, p3.sh dengan isi masing-masing : 


![4](https://github.com/user-attachments/assets/62f119b3-67ee-4ca8-9aba-b231e285ef72)


  #p1.sh
  
    #! /bin/bash 
    echo “Program p1” 
    ls –l   
    
![4 a 1](https://github.com/user-attachments/assets/d20df42d-487a-467a-9332-1fa9ca040dcc)


  #p2.sh
  
    #! /bin/bash 
    echo “Program p2” 
    who 

![4 a 2](https://github.com/user-attachments/assets/a956adb0-5727-4995-999d-e019ed444c18)


  #p3.sh
  
    #! /bin/bash 
    echo “Program p3” 
    ps x
    
![4 a 3](https://github.com/user-attachments/assets/07c1fed6-0821-44ff-8a66-4306d8f9af30)


b. Jalankan script tersebut sebagai berikut : 

      $ ./p1.sh ; ./p3.sh ; ./p2.sh 
      $ ./p1.sh & 
      $ ./p1.sh $ ./p2.sh & ./p3.sh & 
      $ ( ./p1.sh ; ./p3.sh ) & 


Disini saya mengubah dulu izin dari ketiga file tersebut menggunakan chmod, agar dapat di execute atau jalankan


kemudian baru memasukan command line yg diatas :
      
      $ ./p1.sh ; ./p3.sh ; ./p2.sh
![4 b 1](https://github.com/user-attachments/assets/2f07d8ab-02f8-4711-a1f4-acd19f502e98)

    
      $ ./p1.sh & 
![4 b 2](https://github.com/user-attachments/assets/d06e29b3-7c41-4ef3-a86b-988239710276)

pada command ketiga saya mengalami kebingungan karena command tersebut tidak valid, jadi saya berasumsi

    $ ./p1.sh $ ./p2.sh & ./p3.sh &
Command tersebut harusnya :


jika merupakan sambungan dari command sebelumnya
    
    $ ./p1.sh & ./p1.sh
![4 b 3](https://github.com/user-attachments/assets/ee0cae61-e73f-4629-bc28-4e97917e4239)
atau seperti ini :

    $ ./p1.sh & ./p2.sh & ./p3.sh & 
![VirtualBox_PRIMER_25_09_2024_23_08_24](https://github.com/user-attachments/assets/cb5b7646-8216-4c18-8e32-5ac735d394d6)


dan ini command line selanjutnya jika itu merupakan sambungan command line satu
![4 b 4](https://github.com/user-attachments/assets/41b3d14c-3f7c-46af-8651-469eda35d30b)


    $ ( ./p1.sh ; ./p3.sh ) & 
![4 b 5](https://github.com/user-attachments/assets/e4669f27-d18c-4d58-b703-0889b62c4476)


**5. Jobs**


a. Buat shell-script yang melakukan loop dengan nama pwaktu.sh, 
setiap 10 detik, kemudian menyimpan tanggal dan jam pada file hasil.

      #!/bin/bash 
      while [ true ] 
      do 
      date >> hasil 
      sleep 10 
      done 
![5 a 1](https://github.com/user-attachments/assets/d8c4057e-2ec0-494d-8f2d-a0c987e9eedb)
![5 a 2](https://github.com/user-attachments/assets/7686f0a3-aa5e-4728-987c-74fecff587c0)

ternyata jika command line kosong itu dia sedang running, dan untuk kembali ke terminal harus menekan ctrl+c, dan akan muncul file hasil pada direktori
![5 a 3](https://github.com/user-attachments/assets/4029782d-ce83-411c-a1b3-deb4de7914fb)


b. Jalankan sebagai background; kemudian jalankan satu program (utilitas find) di background 
sebagai berikut : 

    $ jobs 
    $ find / -print > files 2>/dev/null & 
    $ jobs 
![5 b](https://github.com/user-attachments/assets/b0ec387e-fb90-47f2-83bf-50db1add8508)


c. Jadikan program ke 1 sebagai foreground, tekan ^Z dan kembalikan program tersebut ke 
background 
    
    $ fg %1 
    $ bg 
![5 c](https://github.com/user-attachments/assets/042a8325-bbb7-4e5e-9236-a5f5db3724ba)


d. Stop program background dengan utilitas kil

    $ ps x 
    $ kill [Nomor PID] 

![5 d 1](https://github.com/user-attachments/assets/ea8fc7d0-7194-44e5-956c-8a8df790f088)


disini nomor proses untuk pwaktu.sh ada pada nomor 6235, sehingga kita akan kill PID tersebut
![5 d 2](https://github.com/user-attachments/assets/753c4e42-419f-44ba-b4b3-499b6bc2c647)


PID 6235 hilang setelah di kill, dan pwaktu.sh ke terminated
![5 d 3](https://github.com/user-attachments/assets/8d89fa68-942c-4760-a1d3-49da45447f70)


**6. History**

a. Ganti nilai HISTSIZE dari 1000 menjadi 20 

    $ HISTSIZE=20 
    $ h
Disini command untuk menampilkan history itu bukan :

    $ h
melainkan :

    $ history
![6 a 1](https://github.com/user-attachments/assets/519375df-37a5-4909-a198-651ab980b418)

Disini saya memiliki banyak history
![6 a 2](https://github.com/user-attachments/assets/9d0a9b73-f4b9-4cda-bfbf-478ecf8d3f5f)


yang dimana ketika :
    
    $ HISTSIZE=20
dia hanya akan menampilkan 20 history sebelumnya dari command sekarang( alasan kenapa tidak di perintah yang ke 200 dst, karena saya buat history baru, dikarenakan terlalu kompleks untuk history yg 200 tersebut)
![6 a 3](https://github.com/user-attachments/assets/4b0a71f8-ceab-47c5-9319-4959af254759)


b. Gunakan fasilitas history dengan mengedit instruksi baris ke 5 dari instruksi yang terakhir
dilakukan 

    $ !-5
![6 b](https://github.com/user-attachments/assets/e9d071ab-21f5-45e5-8d86-5a1cf2d8073c)


c. Ulangi instruksi yang terakhir. Gunakan juga ^P dan ^N untuk bernavigasi pada history bufer 

    $ !! 
![6 c](https://github.com/user-attachments/assets/85a39362-bcf7-4602-b7b1-3381b411f265)


d. Ulangi instruksi pada history bufer nomor 150 
    
    $ !150
Disini saya membuat history baru dengan echo sampai command ke 150, karena history saya yang terbaru tidak sampai ke angka 150
![6 d](https://github.com/user-attachments/assets/940e99ba-a923-4e7e-8e42-aa433f26ce6a)


e. Ulangi instruksi dengan prefix “ls” 
   
    $ !ls 
![6 e](https://github.com/user-attachments/assets/1b92a3f7-af36-4617-9b1d-58632984d075)
