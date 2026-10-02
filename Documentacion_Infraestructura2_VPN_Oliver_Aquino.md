# Documentación - Infraestructura 2

**Estudiante:** Oliver Eliam Aquino Paulino  
**Matrícula:** 20241571

## Propósito

La infraestructura conecta una red de usuarios con un servidor web remoto mediante una VPN Site-to-Site entre FortiGate y Cisco, utilizando R1 como ISP simulado.

## Topología

USER-PC-1 -> SW-USERS -> FortiGate -> R1 -> R2-CISCO -> WEB-SRV-1

## Direccionamiento

- Usuarios: 10.15.72.0/25
- Gateway usuarios: 10.15.72.1
- FortiGate WAN: 203.0.113.161/30
- R1 hacia FortiGate: 203.0.113.162/30
- R1 hacia R2: 198.51.100.161/30
- R2 WAN: 198.51.100.162/30
- Red del servidor: 10.15.72.128/28
- Gateway servidor: 10.15.72.129
- WEB-SRV: 10.15.72.130/28

## Servicios y controles

- VLAN 10 con DHCP para usuarios.
- NAT en el FortiGate y en R2.
- VPN Site-to-Site entre ambos extremos.
- Servidor Nginx con HTTPS en TCP/443.
- Rutas específicas para alcanzar la red remota.

## Pruebas realizadas

Se validó DHCP, conectividad hacia el servidor, HTTPS, traceroute, estado de la VPN, tráfico cifrado y NAT. También se comprobó que al desactivar la VPN la comunicación con el servidor deja de funcionar y se recupera al volver a activarla.

## Conclusión

La infraestructura cumple el objetivo del laboratorio al mantener la comunicación entre ambas redes privadas a través del túnel VPN y demostrar que el acceso al servidor depende directamente de que la VPN esté activa.
