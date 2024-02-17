_Transmission Control Protocol_ es uno de los principales protocolos de internet, orientado a establecer, mantener y finalizar una conexion entre dispositivos. El protocolo busca garantizar que la información se entregue de forma ordenada y sin errores, y realiza retransmisiones en caso de perdida o corrupción de información.

# Establecimiento de conexion con TCP
Cuando dos dispositivos buscan establecer conexion usan el el llamado _threeway handshake_, esta interaccion se ve de la siguiente forma:
- El equipo que quiere establecer la conexion envia un [[paquete]] [[SYN]]
- El receptor de la conexion responde con [[SYN-ACK]]
- El equipo emisor de la conexion responde con [[ACK]]
Una vez finalizado este intercambio de [[paquete]]s, se entiende que ambos extremos de la conexión estan sincronizados y listos para comenzar la transmisión de información.
# Diagrama de interacciones TCP
![[Diagrama_TCP.png]]