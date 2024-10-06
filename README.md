# Servidor-DHCP-en-Debian

## Descripción:

Este documento explica cómo configurar un servidor DHCP en Debian 12, con detalles sobre la instalación y configuración inicial. Abarca aspectos como la creación de un relay DHCP para gestionar redes internas y cómo implementar una configuración de failover para asegurar la continuidad del servicio DHCP. A continuación se presenta un resumen de los temas principales:

  1. Instalación de DHCP en Debian 12: Pasos para instalar el paquete isc-dhcp-server, configurar la IP estática del servidor y ajustar los archivos de configuración necesarios.
  
  2. Configuración del Relay DHCP: Se detalla cómo configurar un relay DHCP, que permite asignar direcciones IP a dispositivos en subredes remotas.
  
  3. Configuración de Failover: Implementación de un servidor secundario de DHCP (Failover) para garantizar la alta disponibilidad, incluyendo cómo sincronizar las configuraciones entre el servidor principal y el de failover.
  
  4. Clientes DHCP: Configuración de clientes en Debian y Windows para probar la asignación automática de direcciones IP desde el servidor DHCP y el relay.


