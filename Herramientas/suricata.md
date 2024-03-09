software de [[IDPS]] [[open-source]] de alto rendimiento, conocido por su capacidad de examinar el trafico de red en tiempo real para detectar patrones maliciosos y responder a los mismos de forma pro activa.

# Modos de operación
- Modo pasivo: Observador no intrusivo, analiza el trafico sin interferir de ninguna forma con la entrega de datos, útil para monitorización y recopilación de información cuando no quiere afectarse en el rendimiento de la red
- Modo activo: Suricata toma medidas inmediatas para prevenir o mitigar amenazas, bloqueando conexión, enviando alertas o ejecutando otras acciones especificas según reglas pre configuradas
# Funcionamiento
- Motor de reglas flexible que permite definir patrones y comportamientos específicos asociados a amenazas conocidas o comportamientos anómalos
- Análisis de protocolos: Se analizan múltiples protocolos de red, incluidos [[TCP]], [[UDP]], [[ICMP]] y protocolos como [[HTTPS]] y [[DNS]]
- Inspección de contenido: Se inspecciona el contenido del trafico, identificando amenazas basadas en patrones de cadenas, [[exploits]] conocidos y firmas de [[malware]]
- Decodificacion de protocolos: Se analiza y comprende el trafico en diferentes niveles, es decir, capa de red, capa de aplicación, etc
- Captura de archivos: Es posible capturar archivos transmitidos a través de la red para su posterior análisis, permitiendo la detección de amenazas basadas en archivos maliciosos
- Compatibilidad con [[IPv6]]