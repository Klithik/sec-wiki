_Transmission Control Protocol_ es uno de los principales protocolos de internet, orientado a establecer, mantener y finalizar una conexión entre dispositivos. El protocolo busca garantizar que la información se entregue de forma ordenada y sin errores, y realiza retransmisiones en caso de perdida o corrupción de información.

# Establecimiento de conexión con TCP
Cuando dos dispositivos buscan establecer conexión usan el el llamado _threeway handshake_, esta interacción se ve de la siguiente forma:
- El equipo que quiere establecer la conexión envía un [[paquete]] [[SYN]]
- El receptor de la conexión responde con [[SYN-ACK]]
- El equipo emisor de la conexión responde con [[ACK]]
Una vez finalizado este intercambio de [[paquete]]s, se entiende que ambos extremos de la conexión están sincronizados y listos para comenzar la transmisión de información.

# Transferencia de datos
Una vez establecida la conexión es posible iniciar la transferencia de datos, durante dicha transferencia se llevan a cabo diferentes procesos para mantener la fiabilidad y robustez del protocolo.

## Números de secuencia
Estos números de secuencia son usados para identificar los datos dentro del flujo de bytes y poder identificar los bytes de los datos de la aplicación.

En todo segmento TCP hay 2 números de secuencia; uno asociado al emisor y otro al receptor, los nombres de cada uno son dependientes del punto de vista, todo emisor se refiere a su numero de secuencia de esa misma forma, numero de secuencia, mientras que al del receptor se le llama numero de asentimiento. Para mantener la fiabilidad el receptor asiente a la transferencia de información para confirmar su recepción. Esta función fue mejorada añadiendo el [[SACK]].
# Diagrama de interacciones TCP
![[Diagrama_TCP.png]]