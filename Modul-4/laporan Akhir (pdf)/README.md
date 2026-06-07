# Konfigurasi DMZ Menggunakan MikroTik, FortiGate, dan Cisco di PNETLab
## 1. Topologi jaringan
<img width="912" height="837" alt="image" src="https://github.com/user-attachments/assets/89c6b9fe-5a65-444b-b212-be14b853180f" />

---

## 2. Segmentasi Jaringan

Pada topologi ini terdapat beberapa segment jaringan:

| Segment | Network | Keterangan |
|---------|---------|-----------|
| Jaringan Lab / Internet | DHCP dari jaringan lab | Sumber koneksi luar |
| ISP ke FortiGate | 10.10.10.0/30 | Link antara MikroTik ISP dan FortiGate |
| Client WAN | 172.16.100.0/24 | Jaringan client dari sisi luar |
| FortiGate ke Cisco | 10.20.20.0/30 | Link antara FortiGate dan Cisco Router |
| LAN | 192.168.10.0/24 | Jaringan internal client |
| DMZ | 192.168.20.0/24 | Jaringan server DMZ |

## 3. Tabel IP Address

| Perangkat | Interface | IP Address | Gateway | Keterangan |
|:----------|:----------|:-----------|:--------|:-----------|
| MikroTik ISP | ether1 | DHCP Client | DHCP dari jaringan lab | Terhubung ke Cloud / jaringan lab |
| MikroTik ISP | ether2 | `10.10.10.1/30` | - | Terhubung ke FortiGate port1 |
| MikroTik ISP | ether3 | `172.16.100.1/24` | - | Gateway untuk Client-WAN |
| FortiGate | port1 | `10.10.10.2/30` | `10.10.10.1` | Interface WAN |
| FortiGate | port2 | `10.20.20.1/30` | - | Interface INSIDE ke Cisco |
| FortiGate | port3 | `192.168.20.1/24` | - | Interface DMZ |
| Cisco Router | G0/0 | `10.20.20.2/30` | - | Terhubung ke FortiGate port2 |
| Cisco Router | G0/1 | `192.168.10.1/24` | - | Gateway LAN |
| Client LAN **Tinycore Linux**| eth0 | `192.168.10.10/24` | `192.168.10.1` | Client internal |
| Client WAN **Tinycore Linux**| eth0 | `172.16.100.10/24` | `172.16.100.1` | Client luar |
| Ubuntu Server DMZ | eth0 / ens3 | `192.168.20.10/24` | `192.168.20.1` | Web server DMZ |

---

## 4. Konfigurasi tiap perangkat (+ screenshot)
4.1 Konfigurasi MikroTik ISP

| Interface | IP |
|-----------|----|
| ke Cloud/lab | DHCP Client |
| ke FortiGate | `10.10.10.1/30` |
| ke Client WAN | `172.16.100.1/24` |

<img width="1195" height="892" alt="Screenshot 2026-06-08 015259" src="https://github.com/user-attachments/assets/7b09e9df-d347-4830-81e7-640cf9865677" />

---

4.2 Konfigurasi FortiGate

| Interface | Peran | IP |
|-----------|-------|----|
| `port1` | WAN | `10.10.10.2/30` |
| `port2` | INSIDE | `10.20.20.1/30` |
| `port3` | DMZ | `192.168.20.1/24` |

config system interface
<img width="1200" height="916" alt="Screenshot 2026-06-08 015642" src="https://github.com/user-attachments/assets/9989d3fe-a8dc-43c5-ba41-bc8213585923" />
config router static
<img width="1192" height="916" alt="Screenshot 2026-06-08 015807" src="https://github.com/user-attachments/assets/2ac76dd3-ca6b-416c-930a-f3e9da983047" />
config firewall policy
<img width="1198" height="921" alt="Screenshot 2026-06-08 020018" src="https://github.com/user-attachments/assets/9e7ac648-33ea-40ac-ab87-93dd07f8ad37" />
cek PING 
<img width="1206" height="917" alt="Screenshot 2026-06-08 020058" src="https://github.com/user-attachments/assets/727bb858-54f1-4cda-a999-a0e44e1ae3ff" />

---

4.3 Konfigurasi Cisco Router

| Interface | IP |
|-----------|----|
| ke FortiGate | `10.20.20.2/30` |
| ke LAN | `192.168.10.1/24` |

<img width="1197" height="916" alt="Screenshot 2026-06-08 020742" src="https://github.com/user-attachments/assets/95b6ffc1-1477-4b23-97b9-fc87ad38d814" />

---

4.4 Konfigurasi Client LAN *(Tiny Core Linux)*

| Parameter | Nilai |
|-----------|-------|
| IP | `192.168.10.10/24` |
| Gateway | `192.168.10.1` |
| DNS | `8.8.8.8` |

---

4.5 Konfigurasi Client WAN *(Tiny Core Linux)*

| Parameter | Nilai |
|-----------|-------|
| IP | `172.16.100.10/24` |
| Gateway | `172.16.100.1` |
| DNS | `8.8.8.8` |

---

4.6 Konfigurasi Ubuntu Server DMZ

| Parameter | Nilai |
|-----------|-------|
| IP | `192.168.20.10/24` |
| Gateway | `192.168.20.1` |
| DNS | `8.8.8.8` |

install nginx:
<img width="1188" height="912" alt="Screenshot 2026-06-08 020723" src="https://github.com/user-attachments/assets/1989d3c6-5b9f-4fc9-b800-8ec604fbb87c" />
nginx berhasil diinstal:
<img width="1186" height="972" alt="Screenshot 2026-06-08 021330" src="https://github.com/user-attachments/assets/36dc726b-3486-4e69-a8bf-deb7de21a6ee" />
set halaman default:
<img width="1187" height="957" alt="Screenshot 2026-06-08 021553" src="https://github.com/user-attachments/assets/71b9b450-ea84-4293-81b0-3efd3e3ac597" />

---

# 4. Hasil pengujian (+ screenshot)\
![](gambar/pengujian%201.png)
![](gambar/pengujian%202.png)
![](gambar/pengujian%203.png)
![](gambar/pengujian%204.png)
![](gambar/pengujian%205.png)


---
Analisis dan kesimpulan
