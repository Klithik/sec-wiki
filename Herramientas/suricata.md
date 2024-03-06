software de [[IDPS]] [[open-source]] de alto rendimiento, conocido por su capacidad de examinar el trafico de red en tiempo real para detectar patrones maliciosos y responder a los mismos de forma proactiva.

# Modos de operacion
- Modo pasivo: Observador no intrusivo, analiza el trafico sin interferir de ninguna forma con la entrega de datos, util para monitorizacion y recopilacion de informacion cuando no quiere afectarse en el rendimiento de la red
- Modo activo: Suricata toma medidas inmediatas para prevenir o mitigar amenazas, bloqueando conexion, enviando alertas o ejecutando otras acciones especificas segun reglas pre configuradas
# Funcionamiento
- Motor de reglas flexible que permite definir patrones y comportamientos especificos asociados a amenazas conocidas o comportamientos anomalos
- Analisis de protocolos: Se analizan multiples protocolos de red, incluidos [[TCP]], [[UDP]], [[ICMP]] y protocolos como [[HTTPS]] y [[DNS]]
- Inspeccion de contenido: Se inspecciona el contenido del trafico, identificando amenazas basadas en patrones de cadenas, [[exploits]] conocidos y firmas de [[malware]]
- Decodificacion de protocolos: Se analiza y comprende el trafico en diferentes niveles, es decir, capa de red, capa de aplicacion, etc
- Captura de archivos: Es posible capturar archivos transmitidos a traves de la red para su posterior analisis, permitiendo la deteccion de amenazas basadas en archivos maliciosos
- Compativilidad con [[IPv6]]