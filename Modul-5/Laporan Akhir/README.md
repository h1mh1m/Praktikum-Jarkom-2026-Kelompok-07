# Tugas Modul: Implementasi Jaringan Enterprise HQ–Branch dengan VRRP, ISC-DHCP, FortiGate, GRE Tunnel, dan OSPF
## Topologi Jaringan
<img width="1507" height="907" alt="Screenshot 2026-06-13 090951" src="https://github.com/user-attachments/assets/6c7b660e-51fd-4f6a-a335-f93f134d592a" />

## Tugas Modul 1 — Konfigurasi Cisco Switch Jakarta
1. Screenshot topologi Jakarta.
   <img width="698" height="842" alt="image" src="https://github.com/user-attachments/assets/7d8a6714-aa0c-43aa-b187-cb6f90eadc0d" />
2. Screenshot `show vlan brief`.
   <img width="951" height="652" alt="Screenshot 2026-06-13 073651" src="https://github.com/user-attachments/assets/4baaf72b-d29e-4cbb-b485-78b15e9e1d0b" />
3. Screenshot `show interfaces trunk`.
   <img width="947" height="438" alt="image" src="https://github.com/user-attachments/assets/3394ec43-56ff-4710-8eaa-cf1496901c07" />


## Tugas Modul 2 — Konfigurasi Cisco Router Jakarta
1. Screenshot `show ip interface brief`.
   <img width="1178" height="945" alt="Screenshot 2026-06-13 073833" src="https://github.com/user-attachments/assets/05dc2ff7-c735-419d-8bca-e59e5c57a3ef" />
2. Screenshot `show vrrp brief`.
   <img width="1206" height="164" alt="image" src="https://github.com/user-attachments/assets/7f791653-edbb-4dae-aa39-3a20012bf021" />
3. Screenshot konfigurasi subinterface.
   <img width="1203" height="453" alt="Screenshot 2026-06-13 074004" src="https://github.com/user-attachments/assets/cc73cbdc-2bea-4877-96be-2eb7351ad655" />
   <img width="1207" height="758" alt="image" src="https://github.com/user-attachments/assets/3f058df4-1bcc-49b9-a43c-954048f727f1" />
4. Screenshot ping dari Cisco Router ke FortiGate Jakarta.
   <img width="1211" height="178" alt="image" src="https://github.com/user-attachments/assets/b04c125f-50f0-42e1-a9e5-77106243533a" />

## Tugas Modul 3 — Konfigurasi MikroTik Router Jakarta
1. Screenshot `/ip address print`.
  <img width="1175" height="366" alt="Screenshot 2026-06-13 074235" src="https://github.com/user-attachments/assets/1fdd9708-b162-44a4-9db2-2a9840ed9132" />
2.  Screenshot `/interface vrrp print`.
   <img width="1033" height="250" alt="Screenshot 2026-06-13 074345" src="https://github.com/user-attachments/assets/5264bd7d-d625-469d-82cb-8a97f7a84ae3" />
3.  Screenshot `/ip dhcp-relay print`.
   <img width="1153" height="223" alt="Screenshot 2026-06-13 074400" src="https://github.com/user-attachments/assets/64a5bceb-ee1b-4e0d-8202-128790f462b1" />
4.  Screenshot `/ip route print`.
   <img width="1042" height="456" alt="Screenshot 2026-06-13 074415" src="https://github.com/user-attachments/assets/d17a9d10-62fa-4b1f-a747-6dc3bbd9c5d3" />
5.  Screenshot ping dari MikroTik ke FortiGate Jakarta.
    <img width="1117" height="328" alt="Screenshot 2026-06-13 074428" src="https://github.com/user-attachments/assets/0c1c25ee-4dee-4943-ba37-300a5b9afe96" />

## Tugas Modul 4 — Konfigurasi Ubuntu Server Jakarta
1. Screenshot `ip a`.
   <img width="1206" height="247" alt="image" src="https://github.com/user-attachments/assets/45a4d668-4a3f-44f4-b00c-b8150ccece41" />
2. Screenshot `ip route`.
   <img width="1071" height="92" alt="image" src="https://github.com/user-attachments/assets/0c064b7d-7f03-4142-913b-c84b50b4ed5f" />
3.  Screenshot isi file `/etc/dhcp/dhcpd.conf`.
   <img width="1202" height="966" alt="Screenshot 2026-06-13 074818" src="https://github.com/user-attachments/assets/c64b8559-f594-42d8-b7a4-a6ea9e8e83c9" />
4.   Sreenshot `ping 8.8.8.8`
   <img width="1202" height="321" alt="image" src="https://github.com/user-attachments/assets/5c0563c3-d9cd-499a-b1c2-d1a1d527b04c" />

## Tugas Modul 5 — Konfigurasi FortiGate Jakarta
1. Screenshot `get system interface physical`
   <img width="1168" height="935" alt="Screenshot 2026-06-13 075245" src="https://github.com/user-attachments/assets/2f2bb1e4-d1d0-47e6-bf28-fd7db5d88978" />
3. Screenshot `get router info routing-table all`
   
5. Screenshot firewall policy.
6. Screenshot ping ke 8.8.8.8.
7. Screenshot ping ke IP tunnel Surabaya.
8. Screenshot `get router info ospf neighbor`
9. Screenshot `get router info routing-table ospf`

## Tugas Modul 6 — Konfigurasi MikroTik ISP
1. Screenshot `/ip address print` **hasil di ether 1 bisa saja berbeda karena emang dinamic**.
2. Screenshot `/ip route print`.
3. Screenshot `/ip firewall nat print`.
4. Screenshot ping ke 8.8.8.8.
5. Screenshot ping antar-WAN FortiGate.

## Tugas Modul 7 — Konfigurasi Switch dan MikroTik Surabaya
1. Screenshot `show vlan brief`.
2. Screenshot `show interfaces trunk`.
3. Screenshot `/ip address print`.
4. Screenshot `/ip dhcp-server print`.
5. Screenshot `/ip pool print`.
6. Screenshot `/ip route print`.
7. Screenshot client VLAN 30 mendapat IP DHCP.
8. Screenshot ping client Surabaya ke 8.8.8.8.

## Tugas Modul 8 — Konfigurasi FortiGate Surabaya
1. Screenshot `get system interface physical`.
2. Screenshot `get router info routing-table all`.
3. Screenshot firewall policy.
4. Screenshot ping ke 8.8.8.8.
5. Screenshot ping ke IP tunnel Jakarta.
6. Screenshot `get router info ospf neighbor`.
7. Screenshot `get router info routing-table ospf`.

## Tugas Modul 9 — Konfigurasi GRE Tunnel dan OSPF over GRE
1. Screenshot ping WAN antar-FortiGate.
2. Screenshot ping tunnel antar-FortiGate.
3. Screenshot `get router info ospf neighbor`.
4. Screenshot `get router info routing-table ospf`.
5. Screenshot ping client Jakarta ke client Surabaya.
6. Screenshot ping client Surabaya ke client Jakarta.

## Tugas Modul 10 — Pengujian Akhir
1. Screenshot IP DHCP client Jakarta (Vlan 10).
2. Screenshot IP DHCP client Surabaya (Vlan 20).
3. Screenshot ping internet dari Jakarta.
4. Screenshot ping internet dari Surabaya.
5. Screenshot ping antar-site (ini aku tes dari vlan 10 ke vlan 40, nanti terserah kalian tes yang mana).
6. Screenshot akses web server Jakarta dari Surabaya.
7. Screenshot routing table OSPF.
8. Analisis singkat jalur traffic Jakarta ke Surabaya.


