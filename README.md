# Infraestructura 2 - VPN Site-to-Site FortiGate y Cisco

## Video demostrativo

https://youtu.be/n2tdpZlpy5Y?si=1uGPUrB9V_eTovj7

---

**Estudiante:** Oliver Eliam Aquino Paulino  
**Matrícula:** 20241571  
**Asignatura:** Seguridad de Redes

## Propósito

Comunicar la red de usuarios con un servidor web remoto mediante una VPN Site-to-Site entre un FortiGate y un router Cisco, utilizando R1 como ISP simulado.

## Direccionamiento

| Segmento | Red / Dirección | Gateway / Peer |
|---|---|---|
| VLAN 10 - Usuarios | 10.15.72.0/25 | 10.15.72.1 |
| WAN FortiGate | 203.0.113.161/30 | R1 203.0.113.162 |
| R1 hacia R2 | 198.51.100.161/30 | R2 198.51.100.162 |
| Red del servidor | 10.15.72.128/28 | 10.15.72.129 |
| WEB-SRV | 10.15.72.130/28 | HTTPS/443 |
| Loopback ISP | 192.0.2.158/32 | Pruebas |

## Documentación

- [Documentación completa](Documentacion_Infraestructura2_VPN_Oliver_Aquino.md)

## Scripts y comandos

- [Direccionamiento y topología](scripts/DIRECCIONAMIENTO_Y_TOPOLOGIA.md)
- [Instalación Nginx/OpenSSL](scripts/WEB-SRV_instalar_nginx_openssl.txt)
- [Configuración GUI FortiGate](scripts/FortiGate_GUI_configuracion.md)
- [Comandos de verificación y demostración](scripts/COMANDOS_VERIFICACION_Y_DEMO.txt)
- [Pruebas y resultados](scripts/PRUEBAS_Y_RESULTADOS.md)
- [Índice de pruebas](scripts/README_PRUEBAS.txt)

## Running-Configs

- [R1 / ISP](running-configs/R1-ISP_running-config.txt)
- [R2-CISCO](running-configs/R2-CISCO_running-config_SANITIZADO.txt)
- [SW-USERS](running-configs/SW-USERS_running-config.txt)
- [USER-PC / DHCP](running-configs/USER-PC_DHCP_info.txt)
- [WEB-SRV](running-configs/WEB-SRV_config.txt)

## Validaciones

- VLAN 10 y DHCP.
- NAT en FortiGate y R2.
- VPN IPsec Site-to-Site.
- IKE en estado QM_IDLE / ACTIVE.
- Tráfico IPsec en ambos sentidos.
- HTTPS/443.
- Ping y traceroute.
- Demostración VPN activa e inactiva.
