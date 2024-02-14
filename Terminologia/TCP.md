_Transmission Control Protocol_ es uno de los principales protocolos de internet, orientado a establecer, mantener y finalizar una conexion entre dispositivos. El protocolo busca garantizar que la información se entregue de forma ordenada y sin errores, y realiza retransmisiones en caso de perdida o corrupción de información.

Cuando dos dispositivos buscan establecer conexion usan el el llamado _threeway handshake_, este consiste de tres tipos de paquetes:
- [[SYN]]
- [[SYN-ACK]]
- [[ACK]]
Una vez finalizado este intercambio de paquetes, se entiende que ambos extremos de la conexión estan sincronizados y listos para comenzar la transmisión de información.
# Diagrama de interacciones TCP
![[Diagrama_TCP.png]]