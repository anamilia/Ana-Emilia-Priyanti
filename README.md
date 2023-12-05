# Ana-Emilia-Priyanti
# MPI-Bubblesort menggunakan Python
Tugas Pemrosesan Paralel MPI Numerik

# Menyiapkan Ubuntu Server dan Linux Mint
## 1.	Pastikan sudah dalam satu jaringan yang sama untu setiap (Master , Worker, Worker1 dan Worker2)
## 2.	Melakukan upgrade OS 

$ sudo apt update && sudo apt upgrade
- Pada Master
![Screenshot_1](https://github.com/anamilia/mpi/assets/151103543/85ee1553-c463-4b96-b6c2-60cf9f38a25f)

- Pada Worker1
![Screenshot_2](https://github.com/anamilia/mpi/assets/151103543/a3d21c2e-5190-4a83-8d1d-557eb853622b)

- Pada Worker2
![Screenshot_3](https://github.com/anamilia/mpi/assets/151103543/8573f288-2dc8-4035-a6dd-860a2859e0a0)

- Pada Worker3
![Screenshot_4](https://github.com/anamilia/mpi/assets/151103543/bfbd1e80-0829-4dcd-b4e4-02f135059731)

## 3.	Melakukan penginstalan berikut: net-tools untuk ngecek IP, vim untuk teks editor.

$ sudo apt install net-tools vim
- Pada Master
  ![Screenshot_5](https://github.com/anamilia/mpi/assets/151103543/1df1612c-9373-43a4-999a-7be3426c8f6a)

- Pada Worker1
  ![Screenshot_6](https://github.com/anamilia/mpi/assets/151103543/3647150c-539b-46e4-a944-7b2402ab120a)

- Pada Worker2
  ![Screenshot_7](https://github.com/anamilia/mpi/assets/151103543/41a768e3-788b-4299-8313-0de96949b8fc)

- Pada Worker3
  ![Screenshot_8](https://github.com/anamilia/mpi/assets/151103543/22d939d1-5c88-4fd6-b1b0-ef9a90046239)

## 4.	Melakukan pengecekan IP dengan perintah berikut:

$ Ifconfig
| NAMA    | Master        | Worker        | Worker2       | Worker3       |
|---------|---------------|---------------|---------------|---------------|
| IP      |  10.9.59.106  |  10.9.57.99   |  10.9.59.115  |  10.9.59.211  |

# Membuat MPI Cluster
## 1.	Konfigurasi hosts file /etc/hosts
- Pada Master
  ![Screenshot_9](https://github.com/anamilia/mpi/assets/151103543/042e1a17-bc23-4292-acca-2ecb45f74efa)

- Pada Worker1
  ![Screenshot_10](https://github.com/anamilia/mpi/assets/151103543/e41c19ab-24b7-4210-af6d-192421a96b08)

- Pada Worker2
  ![Screenshot_11](https://github.com/anamilia/mpi/assets/151103543/8eac36d8-6ca2-4edb-ac24-5ccf84438c8b)

- Pada Worker3 
  ![Screenshot_12](https://github.com/anamilia/mpi/assets/151103543/47df0685-fd74-400d-93ad-166ebb232022)
  
## 2. Membuat User Baru
Buat user baru di SERVER dan CLIENT. Nama user harus samo semua di seluruh komputer.

$ sudo adduser <nama user>

$ sudo usermod -aG sudo <nama user>

$ su - <nama user>

Server
-	Master
  
 ![Screenshot_13](https://github.com/anamilia/mpi/assets/151103543/c0e8d132-ad98-4b0a-8c93-29cb7c006732)

Client
-	Worker1
  
 ![Screenshot_14](https://github.com/anamilia/mpi/assets/151103543/e1fd8b39-1a55-44b3-a208-80e99bcbc4cd)

 ![Screenshot_15](https://github.com/anamilia/mpi/assets/151103543/60f56e1e-5da0-4b01-82bf-aa2c5eb49642)

-	Worker2
  
  ![Screenshot_16](https://github.com/anamilia/mpi/assets/151103543/c5e3c7bb-2297-448a-9d28-62cf3387307e)

  ![Screenshot_17](https://github.com/anamilia/mpi/assets/151103543/10fa919e-e3a8-4972-acda-e2915fc7969e)

-	Worker3
  
  ![Screenshot_18](https://github.com/anamilia/mpi/assets/151103543/71fc0b18-8f26-49cd-a650-6b6a71447611)
 	
  ![Screenshot_19](https://github.com/anamilia/mpi/assets/151103543/b685a18e-117d-4dcc-bb12-f554e17f276f) 

## 3. Konfigurasi SSH
Setelah membuat dan masuk ke user, lakukan konfigurasi SSH.

1. Install SSH
   
$ sudo apt install openssh-server

-	Pada master
  ![Screenshot_20](https://github.com/anamilia/mpi/assets/151103543/8e155e88-d764-436c-a023-14e0b24c5c12)

-	Pada worker
  ![Screenshot_21](https://github.com/anamilia/mpi/assets/151103543/6375cec5-1ea7-48fc-9231-fb6facd3d784)

-	Pada worker2
  ![Screenshot_22](https://github.com/anamilia/mpi/assets/151103543/3a37e546-b4b7-4c06-b5da-9a03a63e7f42)

-	Pada worker3
  ![Screenshot_23](https://github.com/anamilia/mpi/assets/151103543/9cc0dad4-3916-413e-b3cd-3cbdefca0ee9)

2. Melakukan pengecekan SSH
   
$ ssh <nama user>@<host>

-	SSH dari Master ke Worker1
  ![Screenshot_24](https://github.com/anamilia/mpi/assets/151103543/90a0dde5-975b-4ffb-a661-a8f776b3adfa)

-	SSH dari Worker1 ke Master
  ![Screenshot_25](https://github.com/anamilia/mpi/assets/151103543/bccd2b58-4cea-4823-b477-ad3d76305c6e)

- SSH dari Worker2 ke Master
  ![Screenshot_26](https://github.com/anamilia/mpi/assets/151103543/2ef1442b-dae5-4227-b9df-a8ac753dac8c)

- SSH dari Worker3 ke Master
  ![Screenshot_27](https://github.com/anamilia/mpi/assets/151103543/cddba141-df6a-415b-b6ce-b9027b89e58f)

3. Generate Keygen
Lakukan di SERVER

$ ssh-keygen -t rsa

  ![Screenshot_28](https://github.com/anamilia/mpi/assets/151103543/b0840a4c-1a54-4123-82cd-2d3848915e27)

4. Copy key publik ke client
   
$ cd .ssh

$ cat id_rsa.pub | ssh <nama user>@<host> "mkdir .ssh; cat >> .ssh/authorized_keys"

![Screenshot_29](https://github.com/anamilia/mpi/assets/151103543/42c952ea-211b-4439-9569-e5c095d10b50)

## 5. Konfigurasi NFS

1. Buat shared folder

$ mkdir cloud

  ![Screenshot_30](https://github.com/anamilia/mpi/assets/151103543/bebfc0ba-081a-4f70-8a60-b7c6670ab57f)

2. Install NFS Server

$ sudo apt install nfs-kernel-server

![Screenshot_31](https://github.com/anamilia/mpi/assets/151103543/7cf6904f-ba4c-4e1c-81b3-76a63da20753)

3. Konfigurasi file /etc/exports

<lokasi shared folder> *(rw,sync,no_root_squash,no_subtree_check)

![Screenshot_32](https://github.com/anamilia/mpi/assets/151103543/b237f0c5-1f16-4efc-a215-8ff1c4e58ffc)

$ sudo exportfs -a

$ sudo systemctl restart nfs-kernel-server

![Screenshot_33](https://github.com/anamilia/mpi/assets/151103543/0cb1ce90-ab48-4103-b965-1e4a3560e5ba)

4. Install NFS Client
      
$ sudo apt install nfs-common

-	Worker1
  ![Screenshot_34](https://github.com/anamilia/mpi/assets/151103543/317903af-b161-4d56-ba4d-1f41c0760e9e)

-	Worker2
  ![Screenshot_35](https://github.com/anamilia/mpi/assets/151103543/bff03e72-86b0-4a9d-8247-99395533879c)

-	Worker3
  ![Screenshot_36](https://github.com/anamilia/mpi/assets/151103543/269ebfb5-f991-47fb-a261-ab682f3ba311)

5. Mounting

$ sudo mount <server host>:<lokasi shared folder di server> <lokasi shared folder di client>

![Screenshot_37](https://github.com/anamilia/mpi/assets/151103543/e33c9c82-c530-4254-b11b-39d953aa6ad6)

## 6. Instalasi MPI
1.	Install MPI

$ sudo apt install openmpi-bin libopenmpi-dev

-	Pada Master
  ![Screenshot_38](https://github.com/anamilia/mpi/assets/151103543/9597f488-05c7-411a-856c-ef8432da0a05)

-	Pada Worker1
  ![Screenshot_39](https://github.com/anamilia/mpi/assets/151103543/6e6b9250-daa6-435f-add6-2f45f941c862)

-	Pada Worker2
  ![Screenshot_40](https://github.com/anamilia/mpi/assets/151103543/494a2e2b-8f5b-4176-ac38-0f62aa7736fa)

-	Pada Worker3
  ![Screenshot_41](https://github.com/anamilia/mpi/assets/151103543/8dfdbeb9-ddb9-40a6-8b18-7bd5e86458ed)

# Menjalankan Program Bubblesort.py
## 1.	Membuat Program

$ touch bubblesort.py

$ sudo nano bubblesort.py
  ![Screenshot_43](https://github.com/anamilia/mpi/assets/151103543/3db99160-52c1-418e-bd94-ffc98cac6071)

## 2.	Instalasi Python

$ sudo apt install python3-pip

![Screenshot_42](https://github.com/anamilia/mpi/assets/151103543/8f97d832-0d0e-4512-b24e-2b9d094f5246)

## 3.	Eksekusi Numerik menggunakan Python

$ python3 bubblesort.py

  ![Screenshot_44](https://github.com/anamilia/mpi/assets/151103543/f584220a-af59-4831-93d4-b79eb11bee61)
