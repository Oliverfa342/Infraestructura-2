# Pruebas y resultados - Infraestructura 2

## VPN
La asociación IKE fue verificada en estado `QM_IDLE / ACTIVE`. La asociación IPsec presentó tráfico cifrado en ambos sentidos, con contadores de encapsulación y desencapsulación incrementándose durante las pruebas.

## Conectividad
El USER-PC obtuvo la dirección 10.15.72.2/25 por DHCP, con gateway 10.15.72.1. El servidor WEB utiliza 10.15.72.130/28 con gateway 10.15.72.129.

El ping desde USER-PC hacia WEB-SRV respondió sin pérdida de paquetes. El servicio HTTPS en TCP/443 respondió correctamente y el traceroute llegó al servidor remoto.

## NAT
En R2 se comprobó la traducción de 10.15.72.130 hacia 198.51.100.162 mediante PAT/NAT overload. Durante la evidencia registrada hubo 8 hits y 0 misses.

## VPN desactivada
Al retirar temporalmente el crypto map del enlace WAN de R2, la prueba desde USER-PC hacia WEB-SRV registró 100% de pérdida de paquetes. Al volver a habilitar la VPN, la comunicación se restableció.
