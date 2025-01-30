| Name           | NRP        | Class     |
| ---            | ---        | ----------|
| Yasmin Putri Sujono | 5025221273 | Jaringan Komputer (A) |

<br>

<b> Letakkan link excel hasil perhitungan di sini </b>
<br>
<b> _Place the excel calculation results link here_ </b>
https://docs.google.com/spreadsheets/d/1g4KVZQW-UkkqUzavVGY4KYOOg8FTgLHtGy_W88vu9M8/edit?gid=671499381#gid=671499381



# Laporan Praktikum Modul 4 Non Terraform

## Prefix IP
Letakkan prefix IP yang digunakan di bawah:

_Put IP prefix used below:_
```
10.4.0.0
```

## Topology

- GNS3 <br>
<img width="784" alt="Screenshot 2024-11-18 at 20 06 50" src="https://github.com/user-attachments/assets/bb06ef74-1254-466c-b6ed-a80b236dacac">

- CPT <br>
  ![image](https://github.com/user-attachments/assets/8d79b54a-e5d0-40c8-96a7-f1253e747ee9)

<br>

## Routing

- Routing table
  - GNS3
  <img width="677" alt="Screenshot 2024-11-18 at 20 06 11" src="https://github.com/user-attachments/assets/8e769742-633b-450e-856c-6cc2546749e0">

  - CPT <br> 
  ![image](https://github.com/user-attachments/assets/fc53e282-8479-40cf-a420-552e4cb18cd1)

- Route visualization in topology
  - GNS3 <br> 
<img width="698" alt="Screenshot 2024-11-18 at 21 01 29" src="https://github.com/user-attachments/assets/7d8e0732-3257-4f90-a447-95d999dddaed">

  - CPT
<br> (https://www.canva.com/design/DAGWnS4IQzg/srsfCG1Adj9fTFy8Ne3eyg/edit?utm_content=DAGWnS4IQzg&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton) <br>
  ![image](https://github.com/user-attachments/assets/2a4c063d-fa27-4166-afad-bd76a0040d89)

<br>

## VLSM

### Tree

- Tree image <br> (https://miro.com/welcomeonboard/M1dLTGQyVEQ3RkozS0pRL3ptN3FQUnp2N2krMHJtSCtNVXBrWjJxaGM5cnlDRWh3aytoQWVrZ0NaOE9IdFFzK0d0dFVLTS9YNFdUakwzQk1NenNMVG92OXE1S0FIQWdJWjJxaUxTM2ZXUlVEQ0Era2UwMEhxYitSdE1ZcnFRTmshZQ==?share_link_id=675352500835)  <br>

<img width="1016" alt="Screenshot 2024-11-18 at 20 13 54" src="https://github.com/user-attachments/assets/6ea31fe8-2002-4ee5-90e8-c0600aab7e4d">

- IP distribution table
<img width="656" alt="Screenshot 2024-11-18 at 20 22 40" src="https://github.com/user-attachments/assets/7df21678-870c-467e-b698-6dd910631937">


### Subnetting (If you use GNS3)

Configuration to every router, client, and server for subnetting.

- Kamachi:

```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth0 inet static
address 10.4.0.1
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 10.4.0.13
netmask 255.255.255.252

auto eth3
iface eth3 inet static
address 10.4.0.65
netmask 255.255.255.252

auto eth4
iface eth4 inet static
address 10.4.0.85
netmask 255.255.255.252

auto eth5
iface eth5 inet static
address 10.4.0.93
netmask 255.255.255.252
```

- Fiamma:

```
auto eth0
iface eth0 inet static
address 10.4.0.94
netmask 255.255.255.252
gateway 10.4.0.93
```

- GoldenDawn:

```
auto eth0
iface eth0 inet static
address 10.4.0.86
netmask 255.255.255.252
gateway 10.4.0.85

auto eth1
iface eth1 inet static
address 10.4.8.1
netmask 255.255.248.0

auto eth2
iface eth2 inet static
address 10.4.0.89
netmask 255.255.255.252
```

- Necessarius:

```
auto eth0
iface eth0 inet static
address 10.4.0.66
netmask 255.255.255.252
gateway 10.4.0.65

auto eth1
iface eth1 inet static
address 10.4.0.69
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 10.4.0.73
netmask 255.255.255.252
```

- Alice:

```
auto eth0
iface eth0 inet static
address 10.4.0.14
netmask 255.255.255.252
gateway 10.4.0.13

auto eth1
iface eth1 inet static
address 10.4.2.1
netmask 255.255.254.0
```

- Kihara:

```
auto eth0
iface eth0 inet static
address 10.4.0.2
netmask 255.255.255.252
gateway 10.4.0.1

auto eth1
iface eth1 inet static
address 10.4.0.5
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 10.4.0.9
netmask 255.255.255.252
```

- Vento:

```
auto eth0
iface eth0 inet static
address 10.4.4.3
netmask 255.255.254.0
gateway 10.4.4.1
```

- Terra:

```
auto eth0
iface eth0 inet static
address 10.4.0.98
netmask 255.255.255.224
gateway 10.4.0.97
```

- Acqua:

```
auto eth0
iface eth0 inet static
address 10.4.4.2
netmask 255.255.254.0
gateway 10.4.4.1
```

- Aiwass:

```
auto eth0
iface eth0 inet static
address 10.4.8.2
netmask 255.255.248.0
gateway 10.4.8.1
```

- Aleister:

```
auto eth0
iface eth0 inet static
address 10.4.8.3
netmask 255.255.248.0
gateway 10.4.8.1
```

- Mathers:

```
auto eth0
iface eth0 inet static
address 10.4.0.90
netmask 255.255.255.252
gateway 10.4.0.89
```

- Coronzon:

```
auto eth0
iface eth0 inet static
address 10.4.0.74
netmask  255.255.255.252
gateway 10.4.0.73
```

- Elizard:

```
auto eth0
iface eth0 inet static
address 10.4.0.82
netmask 255.255.255.252
gateway 10.4.0.81
```

- Index:

```
auto eth0
iface eth0 inet static
address 10.4.0.78
netmask  255.255.255.252
gateway 10.4.0.77

#A14
auto eth1
iface eth1 inet static
address 10.4.0.17
netmask  255.255.255.240
```

- Magnus:

```
auto eth0
iface eth0 inet static
address 10.4.0.18
netmask  255.255.255.240
gateway 10.4.0.17
```

- Gremlin:

 ```
auto eth0
iface eth0 inet static
address 10.4.0.70
netmask 255.255.255.252
gateway 10.4.0.69

auto eth1
iface eth1 inet static
address 10.4.6.1
netmask 255.255.254.0
 ```

- Thor:

```
auto eth0
iface eth0 inet static
address 10.4.6.3
netmask  255.255.254.0
gateway 10.4.6.1
```

- Othinus:

```
auto eth0
iface eth0 inet static
address 10.4.6.2
netmask  255.255.254.0
gateway 10.4.6.1
```

- LastOrder:

```
auto eth0
iface eth0 inet static
address 10.4.2.3
netmask 255.255.254.0
gateway 10.4.2.1

auto eth1
iface eth1 inet static
address 10.4.1.129
netmask 255.255.255.128
```

- Leivinia:

```
auto eth0
iface eth0 inet static
address 10.4.1.130
netmask 255.255.255.128
gateway 10.4.1.129
```

- Fuze:

```
auto eth0
iface eth0 inet static
address 10.4.2.2
netmask 255.255.254.0
gateway 10.4.2.1
```

- Accel:

```
auto eth0
iface eth0 inet static
address 10.4.0.10
netmask 255.255.255.252
gateway 10.4.0.9

auto eth1
iface eth1 inet static
address 10.4.0.129
netmask 255.255.255.128
```

- Railgun:

```
auto eth0
iface eth0 inet static
address 10.4.0.131
netmask 255.255.255.128
gateway 10.4.0.129

auto eth1
iface eth1 inet static
address 10.4.0.33
netmask 255.255.255.224
```

- MeltDowner:

```
auto eth0
iface eth0 inet static
address 10.4.0.34
netmask 255.255.255.224
gateway 10.4.0.33
```

- MentalOut:

```
auto eth0
iface eth0 inet static
address 10.4.0.35
netmask 255.255.255.224
gateway 10.4.0.33
```

- DarkMatter:

```
auto eth0
iface eth0 inet static
address 10.4.0.130
netmask 255.255.255.128
gateway 10.4.0.129
```

- Noukan:

```
auto eth0
iface eth0 inet static
address 10.4.0.6
netmask 255.255.255.252
gateway 10.4.0.5
```

### Routing

Configuration to every router for routing.

- Kamachi:

```
up route add -net 10.4.0.4 netmask 255.255.255.252 gw 10.4.0.2
up route add -net 10.4.0.8 netmask 255.255.255.252 gw 10.4.0.2
up route add -net 10.4.0.128 netmask 255.255.255.128 gw 10.4.0.2
up route add -net 10.4.0.32 netmask 255.255.255.224 gw 10.4.0.2

up route add -net 10.4.2.0 netmask 255.255.254.0 gw 10.4.0.14
up route add -net 10.4.1.128 netmask 255.255.255.128 gw 10.4.0.14

up route add -net 10.4.0.68 netmask 255.255.255.252 gw 10.4.0.66
up route add -net 10.4.6.0 netmask 255.255.254.0 gw 10.4.0.66
up route add -net 10.4.0.72 netmask 255.255.255.252 gw 10.4.0.66
up route add -net 10.4.0.76 netmask 255.255.255.252 gw 10.4.0.66
up route add -net 10.4.0.16 netmask 255.255.255.240 gw 10.4.0.66
up route add -net 10.4.0.80 netmask 255.255.255.252 gw 10.4.0.66

#GoldenDawn : A17, A18
up route add -net 10.4.8.0 netmask 255.255.248.0 gw 10.4.0.86
up route add -net 10.4.0.88 netmask 255.255.255.252 gw 10.4.0.86

# Fiamma : A20, A21
Up route add -net 10.4.4.0 netmask 255.255.254.0 gw 10.4.0.94
Up route add -net 10.4.0.96 netmask 255.255.255.224 gw 10.4.0.94
```

- Fiamma:

```
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.93
up route add -net 10.4.0.96 netmask 255.255.255.224 gw 10.4.4.3
```

- GoldenDawn:

```
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.85
```

- Necessarius:

```
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.65

up route add -net 10.4.6.0 netmask 255.255.254.0 gw 10.4.0.70

up route add -net 10.4.0.76 netmask 255.255.255.252  gw 10.4.0.74
up route add -net 10.4.0.16 netmask 255.255.255.240 gw 10.4.0.74
up route add -net 10.4.0.80 netmask 255.255.255.252 gw 10.4.0.74  
```

- Alice:

```
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.13
up route add -net 10.4.1.128 netmask 255.255.255.128 gw 10.4.2.3
```

- Kihara:

```
up route add -net 10.4.0.128 netmask 255.255.255.128 gw 10.4.0.10
up route add -net 10.4.0.32 netmask 255.255.255.224 gw 10.4.0.10
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.1
```

- Vento:

  ```
  up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.4.1
  ```

- Coronzon:

  ```
  up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.73
  up route add -net 10.4.0.16 netmask 255.255.255.240 gw 10.4.0.78
  ```

- Index:

  ```
  up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.77
  ```

- Gremlin:

  ```
  up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.69
  ```

- LastOrder:

  ```
  up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.2.1
  ```

- Accel:

  ```
  up route add -net 10.4.0.32 netmask 255.255.255.224 gw 10.4.0.131
  up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.9
  ```

- Railgun:

  ```
  up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.4.0.129
  ```

### Testing

- Client - client
C: DarkMeter - MeltDowner
<img width="692" alt="Screenshot 2024-11-18 at 21 17 24" src="https://github.com/user-attachments/assets/aca71912-443f-46a6-996f-1e8c9f080e8e">

- Client - Server
C: DarkMetter - MentalOut
<img width="697" alt="Screenshot 2024-11-18 at 21 24 28" src="https://github.com/user-attachments/assets/ff0aa7f7-5241-430c-b09d-378152c485b0">

- Client - Router
C : DarkMeter - Railgun
<img width="627" alt="Screenshot 2024-11-18 at 21 15 39" src="https://github.com/user-attachments/assets/832a72b6-0779-4634-bd49-faa580f11b78">

- Server - Server
C: Noukan - MentalOut
<img width="612" alt="Screenshot 2024-11-18 at 21 21 08" src="https://github.com/user-attachments/assets/156d09d5-187e-4f90-b906-1620eee51a61">

- Server - Router
C: Elizard - Corozon
<img width="619" alt="Screenshot 2024-11-18 at 21 22 11" src="https://github.com/user-attachments/assets/f10875f6-9bb3-4abd-9612-b3481db20e54">

- Router - Router
C: Kamachi - Kihara
<img width="616" alt="Screenshot 2024-11-18 at 21 13 27" src="https://github.com/user-attachments/assets/b82fd4ad-5b54-4ea6-b76e-e25f1010018c">

<br>

## CIDR

### Tree

- Tree image (https://miro.com/app/board/uXjVLEOxbRM=/?share_link_id=451151855279)

  ![image](https://github.com/user-attachments/assets/73288da2-6ed6-47d8-88f3-6bebaac469e8)

- IP distribution table

  ![image](https://github.com/user-attachments/assets/b332a3f2-f870-44b3-8945-d52d39b5ba36)


### Subnet Merging Iteration

---

### Iterasi 1
| ID   | Value | Depth |
|------|-------|-------|
| A1   | 30    | 1     |
| A2   | 23    | 2     |
| A3   | 27    | 3     |
| A4   | 30    | 1     |
| A5   | 21    | 2     |
| A6   | 30    | 2     |
| A7   | 30    | 1     |
| A8   | 30    | 2     |
| A9   | 30    | 3     |
| A10  | 30    | 3     |
| A11  | 28    | 4     |
| A12  | 30    | 2     |
| A13  | 23    | 3     |
| A14  | 30    | 1     |
| A15  | 23    | 2     |
| A16  | 25    | 3     |
| A17  | 30    | 1     |
| A18  | 30    | 2     |
| A19  | 30    | 2     |
| A20  | 25    | 3     |
| A21  | 27    | 4     |

**Terpanjang**: A11, A21  

**Check Sibling**: ~

**Transformasi**:  
- A21 / 27 * A20 / 25 = B1 / 24  
- A11 / 28 * A10 / 30 = B2 / 27  

---

### Iterasi 2
| ID   | Value | Depth |
|------|-------|-------|
| A1   | 30    | 1     |
| A2   | 23    | 2     |
| A3   | 27    | 3     |
| A4   | 30    | 1     |
| A5   | 21    | 2     |
| A6   | 30    | 2     |
| A7   | 30    | 1     |
| A8   | 30    | 2     |
| A9   | 30    | 3     |
| B2   | 27    | 3     |
| A12  | 30    | 2     |
| A13  | 23    | 3     |
| A14  | 30    | 1     |
| A15  | 23    | 2     |
| A16  | 25    | 3     |
| A17  | 30    | 1     |
| A18  | 30    | 2     |
| A19  | 30    | 2     |
| B1   | 24    | 3     |

**Terpanjang**: A3, A9, B2, A13, A16, B1 

**Check Sibling**: A9 B2 

**Transformasi**:  
- A9 / 30 * B2 / 27 = C1 / 26  

---

### Iterasi 3
| ID   | Value | Depth |
|------|-------|-------|
| A1   | 30    | 1     |
| A2   | 23    | 2     |
| A3   | 27    | 3     |
| A4   | 30    | 1     |
| A5   | 21    | 2     |
| A6   | 30    | 2     |
| A7   | 30    | 1     |
| A8   | 30    | 2     |
| C1   | 26    | 3     |
| A12  | 30    | 2     |
| A13  | 23    | 3     |
| A14  | 30    | 1     |
| A15  | 23    | 2     |
| A16  | 25    | 3     |
| A17  | 30    | 1     |
| A18  | 30    | 2     |
| A19  | 30    | 2     |
| B1   | 24    | 3     |

**Terpanjang**: A3, C1, A13, A16, B1

**Check Sibling**: ~

**Transformasi**:  
- A3 / 27 * A2 / 23 = D1 / 22  
- C1 / 26 * A8 / 30 = D2 / 25  
- A13 / 23 * A12 / 30 = D3 / 22  
- A16 / 25 * A15 / 23 = D4 / 22  
- B1 / 24 * A19 / 30 = D5 / 23  

---

### Iterasi 4
| ID   | Value | Depth |
|------|-------|-------|
| A1   | 30    | 1     |
| D1   | 22    | 2     |
| A4   | 30    | 1     |
| A5   | 21    | 2     |
| A6   | 30    | 2     |
| A7   | 30    | 1     |
| D2   | 25    | 2     |
| D3   | 22    | 2     |
| A14  | 30    | 1     |
| D4   | 22    | 2     |
| A17  | 30    | 1     |
| A18  | 30    | 2     |
| D5   | 23    | 2     |

**Terpanjang**: D1, A5, A6, D2, D3, D4, A18, D5 

**Check Sibling**: A5 , A6 , D2 , D3 , A18 , D5

**Transformasi**:  
- A5 / 21 * A6 / 30 = E1 / 20  
- D2 / 25 * D3 / 22 = E2 / 21  
- A18 / 30 * D5 / 23 = E3 / 22  

---

### Iterasi 5
| ID   | Value | Depth |
|------|-------|-------|
| A1   | 30    | 1     |
| D1   | 22    | 2     |
| A4   | 30    | 1     |
| E1   | 20    | 2     |
| A7   | 30    | 1     |
| E2   | 21    | 2     |
| A14  | 30    | 1     |
| D4   | 22    | 2     |
| A17  | 30    | 1     |
| E3   | 22    | 2     |

**Terpanjang**: D1, E1, E2, D4, E3 

**Check Sibling**: ~

**Transformasi**:  
- D1 / 22 * A1 / 30 = F1 / 21  
- E1 / 20 * A4 / 30 = F2 / 19  
- E2 / 21 * A7 / 30 = F3 / 20  
- D4 / 22 * A14 / 30 = F4 / 21  
- E3 / 22 * A17 / 30 = F5 / 21  

---

### Iterasi 6
| ID   | Value | Depth |
|------|-------|-------|
| F1   | 21    | 1     |
| F2   | 19    | 1     |
| F3   | 20    | 1     |
| F4   | 21    | 1     |
| F5   | 21    | 1     |

**Terpanjang**: F1, F2, F3, F4, F5 

**Check Sibling**: F1 , F2 , F3 , F4 , F5

**Transformasi**:  
- F1 / 21 * F2 / 19 = G1 / 18  
- F3 / 20 * F4 / 21 = G2 / 19  

---

### Iterasi 7
| ID   | Value | Depth |
|------|-------|-------|
| G1   | 18    | 1     |
| G2   | 19    | 1     |
| F5   | 21    | 1     |

**Terpanjang**: G1, G2, F5 

**Check Sibling**: G1 , G2 , F5

**Transformasi**:  
- G2 / 19 * F5 / 21 = H1 / 18  

---

### Iterasi 8
| ID   | Value | Depth |
|------|-------|-------|
| G1   | 18    | 1     |
| H1   | 18    | 1     |

**Terpanjang**: G1, H1  

**Check Sibling**: G1 , H1

**Transformasi**:  
- G1 / 18 * H1 / 18 = I1 / 17  

---

### Iterasi 9
| ID   | Value | Depth |
|------|-------|-------|
| I1   | 17    | 1     |

**Root**: / 17  

--- 

### Subnetting (If you use CPT)

- Link video
  https://youtu.be/5UlLv_aMML4

### Routing

Configuration to every router for routing.

- Kamachi:
  
  ![image](https://github.com/user-attachments/assets/40c1feb9-57e9-4666-8af2-fe7fcadd2fb5)
  ![image](https://github.com/user-attachments/assets/4fffc053-76aa-4389-9fbd-df9a00fa67c5)

- Fiamma:
  
  ![image](https://github.com/user-attachments/assets/5401ef60-81bd-4b06-bec4-3cae67aa5aa4)

- GoldenDawn:
  
  ![image](https://github.com/user-attachments/assets/549ca79f-25cd-4605-945f-0537baafb354)

- Necessarius:

  ![image](https://github.com/user-attachments/assets/492c2f53-1fed-40f1-bd09-41ac9079673f)

- Alice:
  
  ![image](https://github.com/user-attachments/assets/6b6ec42c-3863-422f-84c3-3a757afd8712)

- Kihara:
  
  ![image](https://github.com/user-attachments/assets/208265f1-da90-4519-b984-3857417cee9f)

- Vento:
  
  ![image](https://github.com/user-attachments/assets/e2818077-0aab-48e9-bf17-7352ef531b5a)

- Coronzon:

  ![image](https://github.com/user-attachments/assets/82100d2d-8e28-4582-9e3d-0555a7803394)

- Index:

  ![image](https://github.com/user-attachments/assets/4648ac53-e10c-4f7d-bca5-c7917750e61b)

- Gremlin:

  ![image](https://github.com/user-attachments/assets/51b27222-f42b-42d2-8886-194e44b74540)


- LastOrder:

  ![image](https://github.com/user-attachments/assets/c09ce760-0558-43e6-9696-c0851e5845e3)

- Accel:

  ![image](https://github.com/user-attachments/assets/3abc3510-af4e-4e33-ba1b-8b4a54332326)

- Railgun:

  ![image](https://github.com/user-attachments/assets/420c3e7d-1ea8-45d3-9233-a0cce238ccda)


### Testing

- Client - client

  ![image](https://github.com/user-attachments/assets/17503292-fc6d-468d-be94-547677b071f0)

- Client - Server

  ![image](https://github.com/user-attachments/assets/7ecf3cfe-3bef-44a5-8752-0865c1e42e3b)

- Client - Router

  ![image](https://github.com/user-attachments/assets/043d3e46-2700-4aca-8a43-eb4fb2a876c3)

- Server - Server

  ![image](https://github.com/user-attachments/assets/b38aeb97-aba1-43c8-a11c-498c607f5363)

- Server - Router

  ![image](https://github.com/user-attachments/assets/8270f163-c608-41fe-b7cf-b5a33ca7edbd)


- Router - Router

  ![image](https://github.com/user-attachments/assets/f9b075be-82b7-48f5-8ac1-d4e203f7f5fb)

<br>
  
## Problems

Modulnya terkadang ambigu penjelasaknnya

<br>

## Revisions (if any)
