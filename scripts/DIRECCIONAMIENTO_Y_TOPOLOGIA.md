# Infraestructura 2 - Direccionamiento y topología

Ruta de datos:
USER-PC-1 -> SW-USERS -> FortiGate -> ISP (R1) -> R2-CISCO -> WEB-SRV-1

- Usuarios: 10.15.72.0/25
- FortiGate VLAN10-USERS: 10.15.72.1/25
- DHCP: 10.15.72.2 - 10.15.72.126
- FortiGate WAN: 203.0.113.161/30
- R1 hacia FortiGate: 203.0.113.162/30
- R1 hacia R2: 198.51.100.161/30
- R2 WAN: 198.51.100.162/30
- Red servidor: 10.15.72.128/28
- R2 LAN: 10.15.72.129/28
- WEB-SRV: 10.15.72.130/28
- Loopback ISP: 192.0.2.158/32
