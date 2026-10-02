# Configuración completa y pruebas - Infraestructura 2

## Topología
USER-PC-1 -> SW-USERS -> FortiGate -> R1 ISP -> R2-CISCO -> WEB-SRV-1

## Red de usuarios
- VLAN 10
- Red 10.15.72.0/25
- Gateway 10.15.72.1
- DHCP 10.15.72.2 a 10.15.72.126

## WAN
- FortiGate 203.0.113.161/30
- R1 hacia FortiGate 203.0.113.162/30
- R1 hacia R2 198.51.100.161/30
- R2 198.51.100.162/30

## Red del servidor
- Red 10.15.72.128/28
- R2 LAN 10.15.72.129/28
- WEB-SRV 10.15.72.130/28
- HTTPS TCP/443

## VPN
- Peer FortiGate: 198.51.100.162
- Peer Cisco: 203.0.113.161
- IKEv1 Main
- DES / SHA1
- DH14
- Phase 2 entre 10.15.72.0/25 y 10.15.72.128/28

## NAT
- FortiGate aplica NAT a usuarios hacia WAN.
- R2 aplica PAT a la red del servidor.
- El tráfico de VPN queda excluido del NAT en R2.

## Pruebas
- DHCP correcto en USER-PC.
- VPN IKE activa.
- Tráfico IPsec en ambos sentidos.
- Ping USER-PC hacia WEB-SRV exitoso.
- HTTPS exitoso.
- Traceroute llega a 10.15.72.130.
- NAT del servidor validado.
- VPN desactivada: 100% de pérdida de paquetes.
- VPN reactivada: comunicación restablecida.
