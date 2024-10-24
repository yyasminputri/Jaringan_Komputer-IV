[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/1zoHyFGp)
| Name           | NRP        | Kelas     |
| ---            | ---        | ----------|
| Rafli Raihan Pramudya | 5025221266 | Jaringan Komputer A |
| Yasmin Putri Sujono | 5025221273 | Jaringan Komputer A |

## Put your topology config image here!
<img width="880" alt="Screenshot 2024-10-23 at 01 44 06" src="https://github.com/user-attachments/assets/7fff8f4b-bec5-4813-afdc-ac57dbaf7596">

<br>

> Template testing report: https://docs.google.com/document/d/17T0fsnh_4zZTrG-lELDJ88intrc9mkwCzZ_s-23JLCc/edit?usp=sharing

## Put your testing report here! 
> The report is sent in PDF format, uploaded to Drive, and set to public view.

`put the link here`

## Soal 0

> Pada perlombaan akhir tahun kali ini, semua worker dan client ikut serta di dalamnya sebagai perwakilan dari masing-masing asrama. Persiapan yang dilakukan untuk perlombaan ini adalah dengan setup semua network configuration yang sesuai dengan tabel peran diatas. Khusus untuk client menggunakan konfigurasi dari DHCP Server.

**Answer**

- Dumbledore:

  ```
    auto eth0
    iface eth0 inet dhcp

    auto eth1
    iface eth1 inet static
	  address  10.4.1.1
	  netmask 255.255.255.0

    auto eth2
    iface eth2 inet static
	  address 10.4.2.1
  	netmask 255.255.255.0

    auto eth3
    iface eth3 inet static
	  address 10.4.3.1
	  netmask 255.255.255.0

    auto eth4
    iface eth4 inet static
	  address 10.4.4.1
	  netmask 255.255.255.0

    auto eth5
    iface eth5 inet static
	  address 10.4.5.1
	  netmask 255.255.255.0

    auto eth6
    iface eth6 inet static
	  address 10.4.6.1
	  netmask 255.255.255.0
  
    up iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.4.0.0/16
  ```

- SeverusSnape:

  ```
  auto eth0
  iface eth0 inet static
	address 10.4.3.2
	netmask 255.255.255.0
	gateway 10.4.3.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- McGonagall:

  ```
  auto eth0
  iface eth0 inet static
	address 10.4.3.3
	netmask 255.255.255.0
	gateway 10.4.3.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Hagrid:

  ```
  auto eth0
  iface eth0 inet static
	address 10.4.4.2
	netmask 255.255.255.0
	gateway 10.4.4.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Voldemort:

  ```
   auto eth0
  iface eth0 inet static
	address 10.4.4.3
	netmask 255.255.255.0
	gateway 10.4.4.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Dementor:

  ```
  auto eth0
  iface eth0 inet static
	address 10.4.4.4
	netmask 255.255.255.0
	gateway 10.4.4.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- HarryPotter:

  ```
    auto eth0
    iface eth0 inet static
  	address 10.4.1.2
  	netmask 255.255.255.0
  	gateway 10.4.1.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- RonWeasley:

  ```
  auto eth0
  iface eth0 inet static
	address 10.4.1.3
	netmask 255.255.255.0
	gateway 10.4.1.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- HermioneGranger:

  ```
    auto eth0
    iface eth0 inet static
  	address 10.4.1.4	
    netmask 255.255.255.0
	  gateway 10.4.1.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- LunaLovegood:

  ```
  auto eth0
  iface eth0 inet static
	address 10.4.6.4
	netmask 255.255.255.0
	gateway 10.4.6.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- FiliusFlitwick:

  ```
  auto eth0
  iface eth0 inet static
	address 10.4.6.3
	netmask 255.255.255.0
	gateway 10.4.6.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- ChoChang:

  ```
  auto eth0
  iface eth0 inet static
	address 10.4.6.2
	netmask 255.255.255.0
	gateway 10.4.6.1

  up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- DracoMalfoy:

  ```
  auto eth0 
  iface eth0 inet dhcp
  ```

- AstoriaGreengrass:

  ```
  auto eth0 
  iface eth0 inet dhcp
  ```

- SusanBones:

  ```
  auto eth0 
  iface eth0 inet dhcp
  ```

- HannahAbbott:

  ```
  auto eth0 
  iface eth0 inet dhcp
  ```

## Soal 1

> Melakukan registrasi subdomain untuk PHP worker bernama gryffindor.hogwarts.A03.com yang mengarah ke alamat IP load balancer Voldemort dan untuk laravel worker bernama ravenclaw.hogwarts.A03.com yang mengarah ke alamat IP load balancer Dementor. Seluruh domain ini berkumpul dalam suatu ruang atau folder bernama hogwarts

**Answer:**

- Screenshot 
<img width="652" alt="Screenshot 2024-10-23 at 02 08 31" src="https://github.com/user-attachments/assets/75407503-3444-43aa-aff7-bb4dea02b41b">

- Configuration

1. Pertama, menentukan nameserver dan memperbarui paket dan menginstal BIND9
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update
apt-get install bind9 -y
```

2. Menkonfigurasi Zona DNS dengan membuat file konfigurasi lokal untuk zona gryffindor.hogwarts.A03.com dan ravenclaw.hogwarts.A03.com di /etc/bind/named.conf.local.
```
cat > /etc/bind/named.conf.local << EOF
zone "gryffindor.hogwarts.A03.com" {
        type master;
        file "/etc/bind/hogwarts/gryffindor.hogwarts.A03.com";
};

zone "ravenclaw.hogwarts.A03.com" {
        type master;
        file "/etc/bind/hogwarts/ravenclaw.hogwarts.A03.com";
};
EOF
```

3. Membuat direktori untuk zona : `mkdir /etc/bind/hogwarts`
4. Menyalin dan Menkonfigurasi file zona untuk gryffindor.hogwarts.A03.com. dan ravenclaw.hogwarts.A03.com.
```
cp /etc/bind/db.local /etc/bind/hogwarts/gryffindor.hogwarts.A03.com
cat > /etc/bind/hogwarts/gryffindor.hogwarts.A03.com << EOF

;
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     gryffindor.hogwarts.A03.com. root.gryffindor.hogwarts.A03.com. (
                        2024111301      ; Serial
                        604800          ; Refresh
                        86400           ; Retry
                        2419200         ; Expire
                        604800 )        ; Negative Cache TTL
;
@               IN      NS      gryffindor.hogwarts.A03.com.
@               IN      A       10.4.4.3 ; IP Load Balancer Voldemort
www     IN      CNAME   gryffindor.hogwarts.A03.com
EOF

cp /etc/bind/db.local /etc/bind/hogwarts/ravenclaw.hogwarts.A03.com
cat > /etc/bind/hogwarts/ravenclaw.hogwarts.A03.com << EOF

;
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     ravenclaw.hogwarts.A03.com. root.ravenclaw.hogwarts.A03.com. (
                        2024111301      ; Serial
                        604800          ; Refresh
                        86400           ; Retry
                        2419200         ; Expire
                        604800 )        ; Negative Cache TTL
;
@               IN      NS      ravenclaw.hogwarts.A03.com.
@               IN      A       10.4.4.4 ; IP Load Balancer Dementor
www     IN      CNAME   ravenclaw.hogwarts.A03.com
EOF 
```
5. Mengatur Opsi BIND dengan mengedit file /etc/bind/named.conf.options untuk mengatur opsi seperti direktori cache dan forwarders.
```
cat > /etc/bind/named.conf.options << EOF
options {
        directory "/var/cache/bind";

        forwarders {
                192.168.122.1;
        };

        dnssec-validation auto;
        allow-query{any;};
        auth-nxdomain no;    # conform to RFC1035
        listen-on-v6 { any; };
};
EOF
```
6. Restart Layanan BIND `service named restart`

<br>

## Soal 2 & 4

> Memberikan ketentuan khusus untuk DracoMalfoy dan AstoriaGreengrass yang mendapat range IP dari 10.4.2.64 - 10.4.2.65 dan 10.4.2.100 - 10.4.2.101

> Selain itu, untuk HannahAbbott dan SusanBones mendapat range IP dari 10.4.5.50 - 10.4.5.51 dan 10.4.5.155 - 10.4.5.156.

**Answer:**

- Screenshot <br>
DracoMalfoy mendapatkan IP '10.4.2.65' <br>
![WhatsApp Image 2024-10-23 at 18 04 47](https://github.com/user-attachments/assets/bd57b3c9-c25e-4b09-b5c1-85dd48c40c1f)
<br>
HannahAbbott mendapatkan IP '10.4.5.51' <br> 
![WhatsApp Image 2024-10-23 at 18 06 01](https://github.com/user-attachments/assets/ed20f684-7bf5-4f0e-ac5f-65a40c7f0640) <br>

- Configuration & Explanation
  1. Pada **DUMBLEDORE** Sebagai Router (DHCP Relay),
  - Pertama, menentukan nameserver dan memperbarui paket dan menginstal paket DHCP relay:
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update
apt-get install isc-dhcp-relay -y
service isc-dhcp-relay start
```
  - Mengedit pada file konfigurasi di bagian /etc/default/isc-dhcp-relay menjadi
  ```
  SERVERS="10.4.3.2"
  INTERFACES="eth1 eth2 eth3 eth4 eth5 eth6"
  OPTIONS=""
  ```
  - Mengaktifkan IP forwarding untuk meneruskan paket antar antarmuka jaringan pada bagian /etc/sysctl.conf menjadi
    ```
    net.ipv4.ip_forward=1
    ```
  - Merestart layanan DHCP relay dengan `service isc-dhcp-relay restart`
  2. Pada **SEVERUS SNAPE** Sebagai DHCP Server,
  - Pertama, menentukan nameserver dan memperbarui paket dan menginstal DHCP server:
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update
apt-get install bind9 -y
```
  - Mengedit file konfigurasi antarmuka DHCP server pada /etc/default/isc-dhcp-server menjadi
    ` INTERFACESv4="eth0"`
  - Mengedit file konfigurasi DHCP:
```
# Range IP untuk Draco Malfoy dan Astoria Greengrass
subnet 10.4.2.0 netmask 255.255.255.0 {
    range 10.4.2.64 10.4.2.65;  # Draco Malfoy
    range 10.4.2.100 10.4.2.101; # Astoria Greengrass

    option routers 10.4.2.1;
    option broadcast-address 10.4.2.255;
    option domain-name-servers 10.4.3.3;

    default-lease-time 300;  
    max-lease-time 6000;
}
```
Dalam subnet ini, Draco Malfoy akan mendapatkan rentang IP 10.4.2.64 - 10.4.2.65, sedangkan Astoria Greengrass mendapat rentang IP 10.4.2.100 - 10.4.2.101. Parameter lain seperti routers, broadcast-address, dan domain-name-servers juga diatur untuk subnet ini. Dan sudah ditambah untuk menetapkan batasan waktu untuk DHCP server pada switch 2 selama 5 menit. 

```
# Range IP untuk Hannah Abbott dan Susan Bones
     subnet 10.4.5.0 netmask 255.255.255.0 {
    range 10.4.5.50 10.4.5.51;  
    range 10.4.5.155 10.4.5.156;  

    option routers 10.4.5.1;
    option broadcast-address 10.4.5.255;
    option domain-name-servers 10.4.3.3;

    default-lease-time 1200;  
    max-lease-time 6000;
}   
```
Di subnet ini, Hannah Abbott akan mendapatkan rentang IP 10.4.5.50 - 10.4.5.51, dan Susan Bones akan menerima IP dalam rentang 10.4.5.155 - 10.4.5.156. Konfigurasi DHCP diatur serupa dengan subnet lain. Dan sudah ditambah untuk menetapkan batasan waktu untuk DHCP server pada switch 5 selama 20 menit.
- Merestart layanan DHCP server dengan `service isc-dhcp-server restart`
<br>

## Soal 3 & 4

> Khusus untuk HermioneGranger yang berada di switch 1 mendapat range IP dari
[Prefix IP].1.10 - [Prefix IP].1.15 dan [Prefix IP].1.20 - [Prefix IP].1.25

> Khusus untuk ChoChang yang berada di switch 6 mendapat range IP dari 
[Prefix IP].6.10 - [Prefix IP].6.15 dan [Prefix IP].6.20 - [Prefix IP].6.25

**Answer:**

- Screenshot <br>
HermioneGranger mendapatkan IP '10.4.1.10' <br>
![WhatsApp Image 2024-10-23 at 18 19 57](https://github.com/user-attachments/assets/0c9b4185-dceb-49a6-8da4-7b395da333c1) <br>
ChoChang mendapatkan IP '10.4.6.10' <br>
![WhatsApp Image 2024-10-23 at 18 23 52](https://github.com/user-attachments/assets/e42fa7ce-404d-44c6-9a89-b99dd2631265) <br>

- Configuration & Explanation
  - Mengedit file konfigurasi DHCP:
  ```
    subnet 10.4.1.0 netmask 255.255.255.0 {
    range 10.4.1.10 10.4.1.15;
    range 10.4.1.20 10.4.1.25;

    option routers 10.4.1.1;
    option broadcast-address 10.4.1.255;
    option domain-name-servers 10.4.3.3;

    default-lease-time 600;  # Switch 6: 10 minutes
    max-lease-time 6000;
   }
  ```
  Di subnet ini, Hermione Granger akan mendapatkan rentang IP, 10.4.1.10 - 10.4.1.15 dan 10.4.1.20 - 10.4.1.25. Konfigurasi DHCP diatur serupa dengan subnet lain, yaitu memberikan IP dalam dua rentang yang ditentukan untuk perangkat yang terhubung ke Switch 1. Dan sudah ditambah untuk menetapkan batasan waktu untuk DHCP server pada Switch 1 memiliki batas waktu 10 menit dengan waktu maksimal 100 menit.
```
subnet 10.4.6.0 netmask 255.255.255.0 {
    range 10.4.6.10 10.4.6.15;  # Cho Chang
    range 10.4.6.20 10.4.6.25;  # Cho Chang

    option routers 10.4.6.1;
    option broadcast-address 10.4.6.255;
    option domain-name-servers 10.4.3.3;

    default-lease-time 600;  # Lease 10 minutes
    max-lease-time 6000;
}
```
Di subnet ini, Cho Chang akan menerima IP dalam rentang 10.4.6.10 - 10.4.6.15 dan 10.4.6.20 - 10.4.6.25. Konfigurasi DHCP diatur serupa dengan subnet lain, yaitu menetapkan dua rentang IP untuk perangkat yang terhubung ke Switch 6. Dan sudah ditambah untuk menetapkan batasan waktu untuk DHCP server pada Switch 6 memiliki batas waktu 10 menit dengan waktu maksimal 100 menit.
- Merestart layanan DHCP server `service isc-dhcp-server restart`
<br>

## Soal 5

> Memastikan bahwa semua CLIENT, HermioneGranger, dan ChoChang harus menggunakan konfigurasi dari DHCP server, menerima DNS dari Professor McGonagall dan dapat akses internet. Khusus untuk HermioneGranger dan ChoChang mendapatkan IP Statis dari DHCP dengan 10.1.x.14. hint: fixed address

**Answer:**

- Screenshot
HermioneGranger mendapatkan IP '10.4.1.14' <br>
![WhatsApp Image 2024-10-24 at 19 46 32](https://github.com/user-attachments/assets/44b0f531-2e45-4aca-a1c6-7e45ab1b325a)
ChoChang mendapatkan IP '10.4.6.14' <br>
![WhatsApp Image 2024-10-24 at 19 46 57](https://github.com/user-attachments/assets/eb1c5d8e-9ab0-4f62-b01d-cd864a6818d1)

- Configuration & Explanation
  1. Pada **HermioneGranger**, lihat link/ether pada eth0 melalui `ip a` lalu salin ke dalam `nano /etc/network/interfaces` untuk fiksasi address, maka dihasilkan
```
auto eth0
iface eth0 inet dhcp
hwaddress ether a2:5f:97:4c:8e:f3
```
2. Pada **ChoChang**, lihat link/ether pada eth0 melalui `ip a` lalu salin ke dalam `nano /etc/network/interfaces` untuk fiksasi address, maka dihasilkan
```
auto eth0
iface eth0 inet dhcp
hwaddress ether 9e:f4:36:0c:a0:54
```
3. Pada **Severus Snape**,
  - Mengedit dan menambahkan file konfigurasi DHCP pada `nano /etc/dhcp/dhcpd.conf`
```
host HermioneGranger {
	hardware ethernet a2:5f:97:4c:8e:f3;
	fixed-address 10.4.1.14;
}

host ChoChang{
	hardware ethernet 9e:f4:36:0c:a0:54;
	fixed-address 10.4.6.14;
}
```
- Merestart layanan DHCP server `service isc-dhcp-server restart`
<br>

## Soal 6

> Dimulai dari asrama Gryffindor yang menjadi PHP worker, mereka harus melakukan deployment untuk website berikut menggunakan PHP 7.4.

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration & Explanation
 - Pertama, menentukan nameserver dan memperbarui paket dan menginstal paket
   ```
	echo nameserver 192.168.122.1 > /etc/resolv.conf
	apt-get update
	apt-get install nginx -y
	apt-get install wget -y
	apt-get install unzip -y
	apt-get install lynx -y
	apt-get install apache2-utils -y
	apt-get install php7.4-fpm php7.4-common php7.4-mysql php7.4-gmp php7.4-curl php7.4-intl php7.4-mbstring php7.4-xmlrpc php7.4-gd php7.4-xml php7.4-cli php7.4-zip -y
   ```
	- Mengunduh dan Mengekstrak Website, Website diunduh dalam format ZIP dari Google Drive :
 ```
wget -O '/var/www/gryffindor.hogwarts.A03.com.zip' 'https://drive.google.com/uc?export=download&id=17R4Zcxm3emHq21WdMJzSfCxO8FHqvATM'
unzip -o /var/www/gryffindor.hogwarts.A03.com.zip -d /var/www/
rm /var/www/gryffindor.hogwarts.A03.com.zip
 ```
Mengekstrak ke dalam direktori /var/www/ dan kemudian struktur direktori diatur agar berada di folder yang tepat :
```
mkdir /var/www/gryffindor.hogwarts.A03.com
mv /var/www/php /var/www/gryffindor.hogwarts.A03.com/php
mv /var/www/index.php /var/www/gryffindor.hogwarts.A03.com
```
  - Mengatur Hak Akses, agar user www-data (default user untuk Nginx) memiliki akses penuh ke direktori website :
```
chown -R www-data:www-data /var/www/gryffindor.hogwarts.A03.com
chmod -R 755 /var/www/gryffindor.hogwarts.A03.com
```
- Membuat file konfigurasi Nginx untuk website:
```
cp /etc/nginx/sites-available/default /etc/nginx/sites-available/gryffindor.hogwarts.A03.com
ln -s /etc/nginx/sites-available/gryffindor.hogwarts.A03.com /etc/nginx/sites-enabled/
rm /etc/nginx/sites-enabled/default
```
- Mengonfigurasi virtual host untuk gryffindor.hogwarts.A03.com pada `/etc/nginx/sites-available/gryffindor.hogwarts.A03.com`
```
echo 'server {
    listen 80;
    server_name gryffindor.hogwarts.A03.com;

    root /var/www/gryffindor.hogwarts.A03.com;
    index index.php index.html index.htm;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php7.4-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }

    error_log /var/log/nginx/error.log;
    access_log /var/log/nginx/access.log;
}' > /etc/nginx/sites-available/gryffindor.hogwarts.A03.com
```
- Start PHP-FPM dan Restart Nginx
```
service php7.4-fpm start
service nginx restart
```
- Menambahkan entri ke file hosts `nano /etc/hosts` agar domain gryffindor.hogwarts.A03.com dapat diakses melalui localhost dengan `127.0.0.1 gryffindor.hogwarts.A03.com`
- Menggunakan browser berbasis teks lynx untuk memverifikasi bahwa website sudah berjalan `lynx localhost`
  
<br>

## Soal 7

> Khusus perlombaan ini, Voldemort sudah jinak dan dia menjadi load balancer untuk para penghuni asrama Gryffindor yang menjadi worker PHP. Aturlah agar Voldemort dapat membagi pekerjaan kepada worker PHP secara optimal. Sebagai pengetesan awal, terapkan algoritma round robin dan lakukan test index.php menggunakan apache benchmark dengan 1000 request dan 100 request/second. Lakukan test sebanyak 3 kali lalu hitung rata-rata dan standar deviasi dari time/request

> _Voldemort, who is now reformed, becomes the load balancer for the Gryffindor PHP workers. Optimize Voldemort to distribute tasks to the PHP workers. For the initial test, apply the round-robin algorithm and test it to the index.php page using Apache Benchmark with 1,000 requests and 100 requests/second. Do the test 3 times and calculate the mean and standard deviation of time/request._

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 8

> Dalam penilaian akhir tahun ini, dibutuhkan algoritma terbaik, cobalah tes 3 algoritma load balancer dengan menggunakan jmeter. Jmeter perlu melakukan login, akses home, dan terakhir logout. Lakukan test dengan 300 thread dan 3 sec ramp up period. Lakukan test sebanyak 3 kali per algoritma, lalu hitung rata-rata dan standar deviasi dari response time. (username: wingardium, password: leviosa)


> _For the final assessment, try three different load-balancing algorithms using JMeter with 300 threads and a 3-second ramp-up period. Jmeter have to be able to login, access homepage, and logout. Do the test 3 times for each algorithm, then calculate the mean and standard deviation of response time. (username: wingardium, password: leviosa)_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 9

> Tidak semua IP dapat akses asrama Gryffindor melalui IP Load balancer Voldemort. Untuk itu, berikan akses pada load balancer Voldemort. Autentikasi akan memerlukan username: “jarkom” dan password: “modul3”. Simpan file autentikasi pada  /etc/nginx/secretchamber 

> _Not all IPs can access Gryffindor's house through Voldemort’s load balancer. Grant access to the Voldemort load balancer. Authentication will require username: “jarkom” and password: “modul3”. Save the authentication file in /etc/nginx/secretchamber._

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 10

> Setelah menambahkan autentikasi ke Gryffindor, coba testing ulang dengan menggunakan JMeter (algoritma round robin) serta skenario, thread, dan ramp up period yang sama seperti no 8 (300 thread, 3 sec ramp up period, login-home-logout). Kali ini, coba juga jumlah worker yang berbeda: 3 worker, 2 worker, dan 1 worker. 

> _After adding authentication to Gryffindor, retest using JMeter (round-robin algorithm) with the same scenario, thread, and ramp up period as number 8 (300 thread, 3 sec ramp up period, login-home-logout). This time, test with different numbers of workers: 3 workers, 2 workers, and 1 worker._

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 11

> Hogwarts juga bekerjasama dengan ITS dalam perlombaan ini. Untuk itu, setiap request pada Voldemort yang mengandung /informatika pada akhir url akan di proxy passing menuju halaman https://www.its.ac.id/informatika/id/beranda/ 

> _Hogwarts has also partnered with ITS for this competition. Any request to Voldemort containing /informatika at the end of the URL should be proxied to the page at https://www.its.ac.id/informatika/id/beranda/._


**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 12

> Selain butuh autentikasi dalam pengaksesan asrama Gryffindor melalui LB Voldemort, juga perlu dibatasi dengan pembatasan IP.  LB Voldemort hanya boleh diakses oleh client dengan IP [Prefix IP].2.64, [Prefix IP].2.100, [Prefix IP].5.50, dan [Prefix IP].5.155. hint: (fixed in dulu clientnya) 


> _In addition to requiring authentication for access to Gryffindor through Voldemort’s load balancer, IP restrictions also need to be enforced. Voldemort's load balancer can only be accessed by clients with IPs: [Prefix IP].2.64, [Prefix IP].2.100, [Prefix IP].5.50, and [Prefix IP].5.155. (hint: fixed client IPs first)._

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 13

> Pengaturan database yang dibutuhkan dalam perlombaan ini wajib diatur di Hagrid. Pastikan pengaturan database tersebut dapat diakses oleh Lunalovegood, FiliusFlitwick, dan ChoChang dengan menggunakan username: kelompokyyy dan password: passwordyyy 

> _Database setup for this competition is managed by Hagrid. Ensure that this database can be accessed by LunaLovegood, FiliusFlitwick, and ChoChang using the username: "kelompokyyy" and password: "passwordyyy”_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 14

> Selain itu, untuk Lunalovegood, FiliusFlitwick, dan ChoChang memiliki website sesuai dengan https://github.com/lodaogos/laravel-jarkom-modul-3/tree/main  berikut. Jangan lupa melakukan instalasi PHP8.0 dan Composer! Pastikan database di Hagrid sudah ada isinya sekarang dan server Laravel sudah running di localhost!

> _Additionally, LunaLovegood, FiliusFlitwick, and ChoChang have websites following this GitHub link: Laravel Jarkom Modul 3. Install PHP 8.0 and Composer! Make sure Hagrid's data storage is populated, and the Laravel servers are running on localhost!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 15

> Lakukan testing endpoint /register sebanyak 100 request dengan 10 request/second di salah satu worker menggunakan apache benchmark dari SusanBones! Kenapa failed 99x? Jelaskan! 

> _Test the /register endpoint with 100 requests and 10 requests per second on one of the workers using Apache Benchmark from SusanBones! Why did 99 tests fail? Explain!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 16

> Lakukan juga testing pada endpoint /login sebanyak 100 request dengan 10 request/second di salah satu worker menggunakan apache benchmark dari SusanBones! Dapatkan token melalui responsenya juga!

> _Test the /login endpoint with 100 requests and 10 requests per second on one of the workers using Apache Benchmark from SusanBones! Collect the token from the response!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 17

> Coba testing pada endpont /me sebanyak 100 request dengan 10 request/second di salah satu worker menggunakan apache benchmark dari SusanBones! Periksa responsenya apakah sudah sesuai dengan yang diloginkan? 

> _Test the /me endpoint with 100 requests and 10 requests per second on one of the workers using Apache Benchmark from SusanBones! Check if the response matches the logged-in user!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 18

> Mendekati tugas akhir perlombaan ini, mari seimbangkan kekuatan LunaLovegood, FiliusFlitwick, dan ChoChang untuk bekerja sama secara adil! Buatkan load balancer Laravel dengan Dementor dan implementasikan Proxy Bind untuk mengaitkan IP dari ketiga worker tersebut!

> _As the competition nears its end, balance the workload of LunaLovegood, FiliusFlitwick, and ChoChang! Create a Laravel load balancer using Dementor and implement Proxy Bind to link the IPs of the three workers!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 19

> Untuk menguatkan para Laravel Worker, coba implementasikan PHP-FPM pada LunaLovegood, FiliusFlitwick, dan ChoChang. Untuk testing kinerja naikkan: 
pm.max_children
pm.start_servers
pm.min_spare_servers
pm.max_spare_servers
sebanyak tiga percobaan dan lakukan analisis testing menggunakan apache benchmark sebanyak 100 request dengan 10 request/second atau menggunakan jmeter dengan 100 threads! (Pilih 1 metode testing)

> _To strengthen the Laravel workers, implement PHP-FPM on LunaLovegood, FiliusFlitwick, and ChoChang. For performance testing, adjust: pm.max_children, pm.start_servers, pm.min_spare_servers, pm.max_spare_servers. Run the tests three times and analyze the performance by using Apache Benchmark with 100 requests at a rate of 10 requests per second or using JMeter with 100 threads! (Choose 1 testing method)_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 20

> Yey terakhir. Menurut Professor Dumbledore, sepertinya menggunakan PHP-FPM tidak cukup untuk meningkatkan performa worker-worker. Implementasikan Least-Conn pada Dementor. Lakukan analisis pada testing kinerja menggunakan apache benchmark sebanyak 100 request dengan 10 request/second atau menggunakan jmeter dengan 100 threads! (Pilih 1 metode testing)

> _Finally, Professor Dumbledore suggests that PHP-FPM might not be enough to improve the workers' performance. Implement the Least-Conn algorithm on Dementor. Analyze the performance by using Apache Benchmark with 100 requests at a rate of 10 requests per second or using JMeter with 100 threads! (Choose 1 testing method)_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>
  
## Problems

## Revisions (if any)
