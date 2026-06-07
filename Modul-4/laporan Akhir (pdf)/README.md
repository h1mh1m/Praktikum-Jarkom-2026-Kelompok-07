# Konfigurasi DMZ Menggunakan MikroTik, FortiGate, dan Cisco di PNETLab
## 1. Topologi jaringan
<img width="870" height="828" alt="image" src="https://github.com/user-attachments/assets/fad820f6-66d6-4791-aaa9-25dc07d1a958" />

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
config firewall address
<img width="1193" height="918" alt="Screenshot 2026-06-08 021944" src="https://github.com/user-attachments/assets/98209f43-5dd1-429f-9642-ef0c0eba41a7" />
config firewall vip
<img width="1195" height="916" alt="Screenshot 2026-06-08 022218" src="https://github.com/user-attachments/assets/0795e72a-b45f-438a-a896-60c0f969b7fc" />
config firewall policy
<img width="1198" height="921" alt="Screenshot 2026-06-08 020018" src="https://github.com/user-attachments/assets/9e7ac648-33ea-40ac-ab87-93dd07f8ad37" />
<img width="1188" height="905" alt="Screenshot 2026-06-08 022530" src="https://github.com/user-attachments/assets/c39681b8-db88-4f45-8e1f-22ee1f5d5cf3" />
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

<img width="1196" height="578" alt="Screenshot 2026-06-08 022930" src="https://github.com/user-attachments/assets/af778f5e-94ac-4165-baf1-d468aa930967" />

---

4.5 Konfigurasi Client WAN *(Tiny Core Linux)*

| Parameter | Nilai |
|-----------|-------|
| IP | `172.16.100.10/24` |
| Gateway | `172.16.100.1` |
| DNS | `8.8.8.8` |

<img width="1193" height="544" alt="image" src="https://github.com/user-attachments/assets/1aff082e-0f96-4a91-a1e2-7f72f8f98d77" />

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

## 1. Pengujian client lan ke gateway cisco

<img width="1197" height="918" alt="image" src="https://github.com/user-attachments/assets/c4b4a734-93ed-4cbb-8847-75425f4bd71f" />

## 2. Pengujian client lan ke fortigate

<img width="1187" height="911" alt="image" src="https://github.com/user-attachments/assets/73c8b4fb-a687-4dea-bb63-b960d15bcd82" />

## 3. Pengujian client lan ke DMZ

<img width="1200" height="921" alt="Screenshot 2026-06-08 023659" src="https://github.com/user-attachments/assets/e24bd2af-812f-4b21-aaeb-bccb4a045a9b" />

## 4. Pengujian client  lan akses ip dmz

<img width="1192" height="918" alt="Screenshot 2026-06-08 023725" src="https://github.com/user-attachments/assets/a2cf2c21-0da5-48f9-bfed-39142aabbd09" />

## 5. Pengujian client wan ping ke isp mikrotik 

<img width="1190" height="918" alt="image" src="https://github.com/user-attachments/assets/8b52801e-fbc3-49bb-b30d-3ab3df99db1f" />

## 6. Penujian client wan ping ke fortigate

<img width="1187" height="907" alt="image" src="https://github.com/user-attachments/assets/50f95e83-ca6b-4a45-94d9-dd396a1a7d2f" />

## 7. Pengujian client wan akses http://10.10.10.2 harus muncul halaman web server.

<img width="1193" height="912" alt="Screenshot 2026-06-08 024050" src="https://github.com/user-attachments/assets/b5c9f5d8-ec73-415d-bb25-48fc0ff85bf9" />

## 8. Pengujian client wan ping client lan 

<img width="1186" height="926" alt="image" src="https://github.com/user-attachments/assets/3a8da3f2-4ac4-4c20-9a28-4682f0518dfb" />

## 9. Pengujian client wan ping IP asli DMZ

<img width="1160" height="911" alt="image" src="https://github.com/user-attachments/assets/7a2e2bc4-cd8a-410a-83c5-5f81d8295b0c" />

## 10. Pengujian server dmz ping lan 

<img width="1193" height="925" alt="Screenshot 2026-06-08 024328" src="https://github.com/user-attachments/assets/5e8f2087-e5c6-4fb5-af7d-af2be8d66fca" />



---
Analisis dan kesimpulan
