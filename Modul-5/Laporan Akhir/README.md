# Tugas Modul: Implementasi Jaringan Enterprise HQ–Branch dengan VRRP, ISC-DHCP, FortiGate, GRE Tunnel, dan OSPF
## Topologi Jaringan
<img width="1507" height="907" alt="Screenshot 2026-06-13 090951" src="https://github.com/user-attachments/assets/6c7b660e-51fd-4f6a-a335-f93f134d592a" />

## Tugas Modul 1 — Konfigurasi Cisco Switch Jakarta
1. Screenshot topologi Jakarta.
2. Screenshot `show vlan brief`.
3. Screenshot `show interfaces trunk`.

# Tugas Modul 2 — Konfigurasi Cisco Router Jakarta
1. Screenshot `show ip interface brief`.
2. Screenshot `show vrrp brief`.
3. Screenshot konfigurasi subinterface.
4. Screenshot ping dari Cisco Router ke FortiGate Jakarta.

# Tugas Modul 3 — Konfigurasi MikroTik Router Jakarta
1. Screenshot `/ip address print`.
2.  Screenshot `/interface vrrp print`.
3.  Screenshot `/ip dhcp-relay print`.
4.  Screenshot `/ip route print`.
5.  Screenshot ping dari MikroTik ke FortiGate Jakarta.

# Tugas Modul 4 — Konfigurasi Ubuntu Server Jakarta
1. Screenshot `ip a`.
2. Screenshot `ip route`.
3.  Screenshot isi file `/etc/dhcp/dhcpd.conf`.
4.   Sreenshot `ping 8.8.8.8`

# Tugas Modul 5 — Konfigurasi FortiGate Jakarta
1. Screenshot `get system interface physical`.
2. Screenshot `get router info routing-table all`.
3. Screenshot firewall policy.
4. Screenshot ping ke 8.8.8.8.
5. Screenshot ping ke IP tunnel Surabaya.
6. Screenshot `get router info ospf neighbor`.
7. Screenshot `get router info routing-table ospf`.

# Tugas Modul 6 — Konfigurasi MikroTik ISP
1. Screenshot `/ip address print` **hasil di ether 1 bisa saja berbeda karena emang dinamic**.
2. Screenshot `/ip route print`.
3. Screenshot `/ip firewall nat print`.
4. Screenshot ping ke 8.8.8.8.
5. Screenshot ping antar-WAN FortiGate.

# Tugas Modul 7 — Konfigurasi Switch dan MikroTik Surabaya
1. Screenshot `show vlan brief`.
2. Screenshot `show interfaces trunk`.
3. Screenshot `/ip address print`.
4. Screenshot `/ip dhcp-server print`.
5. Screenshot `/ip pool print`.
6. Screenshot `/ip route print`.
7. Screenshot client VLAN 30 mendapat IP DHCP.
8. Screenshot ping client Surabaya ke 8.8.8.8.

# Tugas Modul 8 — Konfigurasi FortiGate Surabaya

1. Screenshot `get system interface physical`.
2. Screenshot `get router info routing-table all`.
3. Screenshot firewall policy.
4. Screenshot ping ke 8.8.8.8.
5. Screenshot ping ke IP tunnel Jakarta.
6. Screenshot `get router info ospf neighbor`.
7. Screenshot `get router info routing-table ospf`.

# Tugas Modul 9 — Konfigurasi GRE Tunnel dan OSPF over GRE
1. Screenshot ping WAN antar-FortiGate.
2. Screenshot ping tunnel antar-FortiGate.
3. Screenshot `get router info ospf neighbor`.
4. Screenshot `get router info routing-table ospf`.
5. Screenshot ping client Jakarta ke client Surabaya.
6. Screenshot ping client Surabaya ke client Jakarta.

# Tugas Modul 10 — Pengujian Akhir
1. Screenshot IP DHCP client Jakarta (Vlan 10).
2. Screenshot IP DHCP client Surabaya (Vlan 20).
3. Screenshot ping internet dari Jakarta.
4. Screenshot ping internet dari Surabaya.
5. Screenshot ping antar-site (ini aku tes dari vlan 10 ke vlan 40, nanti terserah kalian tes yang mana).
6. Screenshot akses web server Jakarta dari Surabaya.
7. Screenshot routing table OSPF.
8. Analisis singkat jalur traffic Jakarta ke Surabaya.


