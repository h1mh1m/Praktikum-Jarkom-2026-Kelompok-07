# Konfigurasi DMZ Menggunakan MikroTik, FortiGate, dan Cisco di PNETLab
## 1. Topologi jaringan
![](gambar/CnP_07062026_204157.png)
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

---

4.2 Konfigurasi FortiGate

| Interface | Peran | IP |
|-----------|-------|----|
| `port1` | WAN | `10.10.10.2/30` |
| `port2` | INSIDE | `10.20.20.1/30` |
| `port3` | DMZ | `192.168.20.1/24` |

---

4.3 Konfigurasi Cisco Router

| Interface | IP |
|-----------|----|
| ke FortiGate | `10.20.20.2/30` |
| ke LAN | `192.168.10.1/24` |

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

---

# 4. Hasil pengujian (+ screenshot)\
![](gambar/pengujian%201.png)
![](gambar/pengujian%202.png)
![](gambar/pengujian%203.png)
![](gambar/pengujian%204.png)
![](gambar/pengujian%205.png)


---
Analisis dan kesimpulan
