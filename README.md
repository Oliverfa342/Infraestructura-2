# Infraestructura 2 - VPN Site-to-Site FortiGate y Cisco

## Video demostrativo

https://youtu.be/n2tdpZlpy5Y?si=1uGPUrB9V_eTovj7

---

**Estudiante:** Oliver Eliam Aquino Paulino  
**Matrícula:** 20241571  
**Asignatura:** Seguridad de Redes

## Propósito de la infraestructura

El propósito de esta infraestructura es comunicar una red de usuarios con un servidor web remoto mediante una VPN Site-to-Site entre un FortiGate y un router Cisco. R1 representa al ISP entre ambos peers. La práctica valida que la comunicación hacia el servidor depende del túnel VPN y comprueba además DHCP, NAT, HTTPS y traceroute.

## Direccionamiento

| Segmento | Red / Dirección | Gateway / Peer |
|---|---|---|
| VLAN 10 - Usuarios | 10.15.72.0/25 | 10.15.72.1 |
| WAN FortiGate | 203.0.113.161/30 | R1 203.0.113.162 |
| R1 hacia R2 | 198.51.100.161/30 | R2 198.51.100.162 |
| Red del servidor | 10.15.72.128/28 | R2 10.15.72.129 |
| WEB-SRV | 10.15.72.130/28 | HTTPS/443 |
| Loopback ISP | 192.0.2.158/32 | Pruebas de NAT |

## Documentación

- [Documentación completa](Documentacion_Infraestructura2_VPN_Oliver_Aquino.pdf)

## Scripts y comandos

- [Configuración completa y pruebas](scripts/Configuracion_Completa_y_Pruebas_Infraestructura2.txt)
- [USER-PC DHCP](scripts/USER-PC_DHCP.txt)
- [Instalación Nginx/OpenSSL](scripts/WEB-SRV_instalar_nginx_openssl.txt)
- [Configuración WEB-SRV](scripts/WEB-SRV_configuracion.txt)
- [Direccionamiento y topología](scripts/DIRECCIONAMIENTO_Y_TOPOLOGIA.md)
- [Configuración GUI FortiGate](scripts/FortiGate_GUI_configuracion.md)
- [Comandos de verificación y demo](scripts/COMANDOS_VERIFICACION_Y_DEMO.txt)
- [Pruebas y resultados](scripts/PRUEBAS_Y_RESULTADOS.md)

## Running-Configs

- [R1 / ISP](running-configs/R1-ISP_running-config.txt)
- [R2-CISCO](running-configs/R2-CISCO_running-config_SANITIZADO.txt)
- [SW-USERS](running-configs/SW-USERS_running-config.txt)
- [FortiGate - configuración relevante sanitizada](running-configs/FortiGate_configuracion_relevante_SANITIZADA.conf)
- [USER-PC](running-configs/USER-PC_config.txt)
- [WEB-SRV](running-configs/WEB-SRV_config.txt)

## Implementación validada

- VLAN 10 con DHCP para la red de usuarios.
- NAT en FortiGate para salida hacia la WAN.
- NAT/PAT en R2 para la red del servidor.
- VPN IPsec Site-to-Site entre FortiGate y Cisco.
- IKE en estado `QM_IDLE / ACTIVE`.
- Tráfico IPsec encapsulado y desencapsulado en ambos sentidos.
- Servidor Nginx con HTTPS/443.
- Ping y traceroute desde USER-PC hacia WEB-SRV.
- Demostración VPN ON/OFF: con el túnel desactivado la comunicación falla; al restablecerlo vuelve a funcionar.

> Las PSK, contraseñas y claves privadas fueron reemplazadas por `<REDACTED>` en los archivos públicos.
