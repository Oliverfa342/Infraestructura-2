# FortiGate - configuración realizada por GUI

## Gestión
- port1: 192.168.200.2/24
- Acceso administrativo: PING, HTTPS y HTTP

## WAN
- port3 / alias WAN-FG
- Dirección: 203.0.113.161/30
- Gateway por defecto: 203.0.113.162

## VLAN 10 de usuarios
- Nombre: VLAN10-USERS
- Interfaz padre: port2
- VLAN ID: 10
- Dirección: 10.15.72.1/25
- DHCP: 10.15.72.2 hasta 10.15.72.126
- DNS: 8.8.8.8

## Objetos
- NET-USERS: 10.15.72.0/25
- NET-SERVER: 10.15.72.128/28

## Ruta hacia la red remota
- Destino: 10.15.72.128/28
- Interfaz: VPN-FG-CISCO

## Políticas
- USERS-to-WAN-NAT: tráfico de usuarios hacia la WAN con NAT habilitado.
- USERS-to-VPN: usuarios hacia la red del servidor por VPN, sin NAT.
- VPN-to-USERS: retorno desde la red del servidor hacia usuarios, sin NAT.

## VPN Site-to-Site
- Nombre: VPN-FG-CISCO
- Peer remoto: 198.51.100.162
- IKEv1 en modo Main
- Propuesta: DES / SHA1
- Diffie-Hellman: grupo 14
- Lifetime Phase 1: 86400 segundos
- Red local: 10.15.72.0/25
- Red remota: 10.15.72.128/28
- PFS deshabilitado en Phase 2
- Lifetime Phase 2: 3600 segundos

La clave precompartida no se publica en el repositorio.
