# Jarkom-Modul-4-E06-2023
Berikut adalah repository dari kelompok E06 untuk pengerjaan Praktikum Modul 4 Jaringan Komputer. Repository ini akan berisikan dokumentasi pengerjaan subnetting dan routing.

# Anggota Kelompok
| Nama | NRP | 
| --- | --- |
| Muhammad Hafidh Rosyadi | 5025211013 |
| Kartika Diva Asmara Gita | 5025211039 |

# Dokumentasi Pengerjaan VLSM di GNS3
## Subnetting VLSM
Menentukan jumlah subnet pada topologi.
![image](Images/VLSM/subnetTopo.png)

Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet.
![image](Images/VLSM/subnetTabel.png)
Berdasarkan total IP dan netmask yang dibutuhkan, Subnet besar yang dibentuk memiliki NID `192.209.0.0` dengan Netmask `/19`.

## Tree VLSM
Menghitung pembagian IP berdasarkan NID dan Netmask yang didapatkan.
![image](Images/VLSM/tree.png)

Dari Tree di atas akan mendapat pembagian IP sebagai berikut.
![image](Images/VLSM/tabelIP.png)

## Configuration VLSM
Mengatur Network Configuration masing-masing interface pada setiap node.

### Router
- Aura
```
auto eth0
iface eth0 inet dhcp

#A16 Aura-Frieren
auto eth1
iface eth1 inet static
	address 192.209.0.17
	netmask 255.255.255.252

#A17 Aura-Denken
auto eth2
iface eth2 inet static
	address 192.209.0.21
	netmask 255.255.255.252

#A18 Aura-Eisen
auto eth3
iface eth3 inet static
	address 192.209.0.25
	netmask 255.255.255.252
```
- Frieren
```
#A16 Aura-Frieren
auto eth0
iface eth0 inet static
	address 192.209.0.18
	netmask 255.255.255.252
	gateway 192.209.0.17

#A15 Frieren-Flamme
auto eth1
iface eth1 inet static
	address 192.209.0.13
	netmask 255.255.255.252

#A4 Frieren-PC Lake Korridor
auto eth2
iface eth2 inet static
	address 192.209.0.65
	netmask 255.255.255.224
```
- Flamme
```
#A15 Frieren-Flamme
auto eth0
iface eth0 inet static
	address 192.209.0.14
	netmask 255.255.255.252
	gateway 192.209.0.13

#A13 Flamme-Fern
auto eth1
iface eth1 inet static
	address 192.209.0.5
	netmask 255.255.255.252

#A2 Flamme-PC Rohr Road
auto eth2
iface eth2 inet static
	address 192.209.8.1
	netmask 255.255.252.0

#A14 Flamme-Himmel
auto eth3
iface eth3 inet static
	address 192.209.0.9
	netmask 255.255.252.252
```
- Fern
```
#A13 Flamme-Fern
auto eth0
iface eth0 inet static
	address 192.209.0.6
	netmask 255.255.255.252
	gateway 192.209.0.5

#A1 Fern-Switch4 
#(PC Laub Hills, PC Appetit Region)
auto eth1
iface eth1 inet static
	address 192.209.24.1
	netmask 255.255.248.0
```
- Himmel
```
#A14 Flamme-Himmel
auto eth0
iface eth0 inet static
	address 192.209.0.10
	netmask 255.255.255.252
	gateway 192.209.0.9

#A3 Himmel-PC Schwer Mountains
auto eth1
iface eth1 inet static
	address 192.209.0.41
	netmask 255.255.255.248
```
- Denken
```
#A17 Aura-Denken
auto eth0
iface eth0 inet static
	address 192.209.0.22
	netmask 255.255.255.252
	gateway 192.209.0.21

#A9 Denken-Switch2 
#PC Royal Capital, PC Wille Region
auto eth1
iface eth1 inet static
	address 192.209.2.1
	netmask 255.255.255.0
```
- Eisen
```
#A18 Aura-Eisen
auto eth0
iface eth0 inet static
	address 192.209.0.26
	netmask 255.255.255.252
	gateway 192.209.0.25

#A10 Eisen-Switch1
#Server Ritcher, Server Revolte
auto eth1
iface eth1 inet static
	address 192.209.0.49
	netmask 255.255.255.248

#A12 Eisen-Stark
auto eth2
iface eth2 inet static
	address 192.209.0.1
	netmask 255.255.255.252

#A21 Eisen-Lugner
auto eth3
iface eth3 inet static
	address 192.209.0.37
	netmask 255.255.255.252

#A19 Eisen-Linie
auto eth4
iface eth4 inet static
	address 192.209.0.29
	netmask 255.255.255.252
```
- Lugner
```
#A21 Eisen-Lugner
auto eth0
iface eth0 inet static
	address 192.209.0.38
	netmask 255.255.255.252
	gateway 192.209.0.37

#A8 Lugner-PC Turki Region
auto eth1
iface eth1 inet static
	address 192.209.12.1
	netmask 255.255.252.0

#A7 Lugner-PC Grobe Forest
auto eth2
iface eth2 inet static
	address 192.209.1.1
	netmask 255.255.255.0
```
- Linie
```
#A19 Eisen-Linie
auto eth0
iface eth0 inet static
	address 192.209.0.30
	netmask 255.255.255.252
	gateway 192.209.0.29

#A20 Linie-Lawine
auto eth1
iface eth1 inet static
	address 192.209.0.33
	netmask 255.255.255.252

#A6 Linie-PC Granz Channel
auto eth2
iface eth2 inet static
	address 192.209.4.1
	netmask 255.255.254.0
```
- Lawine
```
#A20 Linie-Lawine
auto eth0
iface eth0 inet static
	address 192.209.0.34
	netmask 255.255.255.252
	gateway 192.209.0.33

#A5 Lawine-Switch7
#PC Breadt Region, Router Heiter
auto eth1
iface eth1 inet static
	address 192.209.0.129
	netmask 255.255.255.192
```
- Heiter
```
#A5 Lawine-Heiter
auto eth0
iface eth0 inet static
	address 192.209.0.131
	netmask 255.255.255.192
	gateway 192.209.0.129

#A11 Heiter-Switch8
#Server Sein, PC Riegel Canyon
auto eth1
iface eth1 inet static
	address 192.209.16.1
	netmask 255.255.252.0
```
### Client
- Lake Korridor
```
#A4 Frieren-PC Lake Korridor
auto eth0
iface eth0 inet static
	address 192.209.0.66
	netmask 255.255.255.224
	gateway 192.209.0.65
```
- Laub Hills
```
#A1 Fern-PC Laub Hills
auto eth0
iface eth0 inet static
	address 192.209.24.2
	netmask 255.255.248.0
	gateway 192.209.24.1
```
- Appetit Region
```
#A1 Fern-PC Appetit Region
auto eth0
iface eth0 inet static
	address 192.209.24.3
	netmask 255.255.248.0
	gateway 192.209.24.1
```
- Rohr Road
```
#A2 Flamme-PC Rohr Road
auto eth0
iface eth0 inet static
	address 192.209.8.2
	netmask 255.255.252.0
	gateway 192.209.8.1
```
- Schwer Mountains
```
#A3 PC Schwer Mountains
auto eth0
iface eth0 inet static
	address 192.209.0.42
	netmask 255.255.255.248
	gateway 192.209.0.41
```
- sss
