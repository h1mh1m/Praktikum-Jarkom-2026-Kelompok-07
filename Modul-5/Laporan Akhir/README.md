# Tugas Modul: Implementasi Jaringan Enterprise HQ–Branch dengan VRRP, ISC-DHCP, FortiGate, GRE Tunnel, dan OSPF
## Topologi Jaringan
<img width="1507" height="907" alt="Screenshot 2026-06-13 090951" src="https://github.com/user-attachments/assets/6c7b660e-51fd-4f6a-a335-f93f134d592a" />

## Tugas Modul 1 — Konfigurasi Cisco Switch Jakarta
1. Screenshot topologi Jakarta.
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
   <img width="1091" height="617" alt="Screenshot 2026-06-13 075336" src="https://github.com/user-attachments/assets/c98f13d1-4aed-44e8-b170-04f5b65f6db1" />
5. Screenshot firewall policy.
   <img width="1140" height="952" alt="Screenshot 2026-06-13 075350" src="https://github.com/user-attachments/assets/3d33d2a6-373b-4e8a-a248-2b85a616f37e" />
7. Screenshot ping ke 8.8.8.8.
   <img width="1093" height="382" alt="Screenshot 2026-06-13 075437" src="https://github.com/user-attachments/assets/f79a3a40-740a-4a57-9d0c-99cf0fbb02fa" />
9. Screenshot ping ke IP tunnel Surabaya.
    <img width="1096" height="378" alt="Screenshot 2026-06-13 075536" src="https://github.com/user-attachments/assets/e1b4a218-e9fd-482e-b056-3ff57c3c0469" />
11. Screenshot `get router info ospf neighbor`
    <img width="1103" height="251" alt="Screenshot 2026-06-13 075554" src="https://github.com/user-attachments/assets/64618e9c-56b6-4c4b-894b-d217f98dd05d" />
13. Screenshot `get router info routing-table ospf`
    <img width="1118" height="252" alt="Screenshot 2026-06-13 075603" src="https://github.com/user-attachments/assets/24069fbc-c471-4fe0-bfaf-a6af5a07d8ac" />

## Tugas Modul 6 — Konfigurasi MikroTik ISP
1. Screenshot `/ip address print` **hasil di ether 1 bisa saja berbeda karena emang dinamic**.
   <img width="1092" height="272" alt="Screenshot 2026-06-13 075812" src="https://github.com/user-attachments/assets/2740cdf2-4726-436b-8429-e020f66f2815" />
3. Screenshot `/ip route print`.
   <img width="1153" height="311" alt="Screenshot 2026-06-13 075828" src="https://github.com/user-attachments/assets/2ee5b125-6e34-4a72-8f9e-c8441b910289" />
5. Screenshot `/ip firewall nat print`.
   <img width="1110" height="177" alt="Screenshot 2026-06-13 075842" src="https://github.com/user-attachments/assets/e5681a25-4d5d-429c-b3e0-f283ace6258b" />
7. Screenshot ping ke 8.8.8.8.
   <img width="1043" height="381" alt="Screenshot 2026-06-13 075852" src="https://github.com/user-attachments/assets/a0392b25-c53f-4a1b-a178-068f6b2bc7a0" />
9. Screenshot ping antar-WAN FortiGate.
    <img width="1116" height="306" alt="Screenshot 2026-06-13 075900" src="https://github.com/user-attachments/assets/ace4a0c2-003f-40c1-a6ac-13395cc5a419" />
    <img width="1032" height="313" alt="Screenshot 2026-06-13 075910" src="https://github.com/user-attachments/assets/9b678d94-fffb-4616-a48b-1ab2e890a386" />

## Tugas Modul 7 — Konfigurasi Switch dan MikroTik Surabaya
1. Screenshot `show vlan brief`.
   <img width="1152" height="366" alt="Screenshot 2026-06-13 080053" src="https://github.com/user-attachments/assets/52079bb4-f739-4e55-b217-9056702de031" />
3. Screenshot `show interfaces trunk`.
   <img width="1151" height="413" alt="Screenshot 2026-06-13 080122" src="https://github.com/user-attachments/assets/eade3423-3e72-409c-8f89-de3f7fef9ec8" />
5. Screenshot `/ip address print`.
   <img width="1101" height="272" alt="Screenshot 2026-06-13 080347" src="https://github.com/user-attachments/assets/801fa5b6-ed22-45d2-86ed-02fa3594ecd2" />
7. Screenshot `/ip dhcp-server print`.
   
9. Screenshot `/ip pool print`.
10. Screenshot `/ip route print`.
    <img width="1176" height="396" alt="Screenshot 2026-06-13 080407" src="https://github.com/user-attachments/assets/53a005b8-db91-4503-abbc-ec945cf1a10b" />
12. Screenshot client VLAN 30 mendapat IP DHCP.
    <img width="1205" height="705" alt="image" src="https://github.com/user-attachments/assets/ddb7be9e-a036-45a2-9cd7-04fcb884b0d8" />
14. Screenshot ping client Surabaya ke 8.8.8.8.
    <img width="1205" height="958" alt="Screenshot 2026-06-13 081827" src="https://github.com/user-attachments/assets/f32e1a88-0e01-40e2-8b44-049217b64816" />

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


