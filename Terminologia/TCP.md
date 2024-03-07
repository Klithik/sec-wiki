_Transmission Control Protocol_ es uno de los principales protocolos de internet, orientado a establecer, mantener y finalizar una conexion entre dispositivos. El protocolo busca garantizar que la información se entregue de forma ordenada y sin errores, y realiza retransmisiones en caso de perdida o corrupción de información.

# Establecimiento de conexión con TCP
Cuando dos dispositivos buscan establecer conexión usan el el llamado _threeway handshake_, esta interacción se ve de la siguiente forma:
- El equipo que quiere establecer la conexión envía un [[paquete]] [[SYN]]
- El receptor de la conexión responde con [[SYN-ACK]]
- El equipo emisor de la conexión responde con [[ACK]]
Una vez finalizado este intercambio de [[paquete]]s, se entiende que ambos extremos de la conexión están sincronizados y listos para comenzar la transmisión de información.
# Diagrama de interacciones TCP
![[Diagrama_TCP.png]]