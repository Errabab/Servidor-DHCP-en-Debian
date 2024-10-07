# Relay 
Para poder instalar el paquete DHCP en Relay  debemos de instalarnos el
paquete llamado:
`apt install isc-dhcp-relay`
Pero antes **actalizaremos** el sistema y los paquetes.
` sudo apt update`
`sudo apt upgrade`

Al instalarlo **automaticamente** se nos abrirá esta pantalla, donde tendremos que poner la **IP DEL SERVER**, que en mi caso es la 192.168.1.10 :

![relay](img/R1.png)

A continuacion nos pedira las interfaces de red por donde escuchara el servidor dhcp,que en mi caso son **enp0s3** y **enp0s8**:

![relay](img/R2.png)

En especificaciones adicionales no pondremos nada.

![relay](img/R3.png)

Una vez instalado apagamos la máquina y configuramos dos tarjetas de red:
  1. Para la red de cliente 
  *El nombre de la red interna tiene que coincidir la del cliente.*

  ![relay](img/R4.png)
  
  2. Para la red del servidor
     
  ![relay](img/R4.png)

Arrancamos la maquina y configuramos las direcciones de ambas tarjetas de red
`nano /etv/network/interfaces`

---
**enp0s3 → Red de servidor
enp0s8 → Red de cliente**

---
![relay](img/R6.png)

Cuando lo hagamos, reiniciamos el servicio networking
`systemctl restart networking`

![relay](img/R6.png)

Comprobamos que se han cambiado las ips corectamente 

![relay](img/R7.png)

Vamos a: 
 `nano /etc/sysctl.conf `

para habilitar el fowarding, descomentamos la linea de ipv4forward. (reenvio de paquetes)

 ![relay](img/R8.png)

Una vez hecho  comprobampos los cambios con el comando `sysctl -f /etc/sysctl.conf`

![relay](img/R9.png)

En relay ponemos la ip del fairlover en `/etc/default/isc-dhcp-relay`

![relay](img/R10.png)

y reiniciamos isc-dhcp-relay
`systemctl restart isc-dhcp-relay.service`
