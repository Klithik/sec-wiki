#recon #discovery
Herramienta usada principalmente para el escaneo de [[puerto]]s.
Para hacerlo envia solicitudes al objetivo, las cuales pueden ser en diferentes formatos dependiendo que se busca
# Opciones
## Tipo de escaneo -S
- Ss: Escaneo de tipo [[SYN]], durante este escaneo, el protocolo [[TCP]] es interrumpido al recibir al recibir el paquete [[SYN-ACK]], con lo cual se logra una mayor velocidad comparado a un escaneo [[TCP]]
- Su: Escaneo de tipo [[UDP]], normalmente usado para buscar servicios de streaming o similares
## Puertos objetivo -p
Existen varios formatos de establecer que [[puerto]]s se quieren escanear:
- Si no se especifica ningun puerto, nmap escaneara los 1,000 puertos mas comunes
- -p- es usado para que nmap escanee todos los puertos
- -p(especificacion): se puede especificar un [[puerto]] o un conjunto de estos para limitar el escaneo, su uso es el siguiente:
	- Para escanear SOLO el [[puerto]] 22 se usaria -p22, mientras que para establecer rango del 22 al 80 se usaria -p22-80, lo anterior escneara todos los [[puerto]]s en ese rango incluyendo ambos limites. Otra posibilidad es encadenar rangos o [[puerto]]s, por ej: -p80,443,8080-9090
-  -F para un escaneo rapido, la seleccion de [[puerto]]s es similar al escaneo predeterminado, pero con esta opcion se reduce aun mas la cantidad
- Para escanear solo los x [[puerto]]s mas comunes puede usarse la opcion --top-ports (numero)
## Verbose
Esta opcion es usada para controlar la cantidad de informacion que entrega nmap como output, si no se especifica esta opcion, se entrega la cantidad minima de informacion, a partir de ahi, se usa -v para aumentarlo, este puede ser usado hasta 3 veces (-vvv) para obtener la maxima salida de informacion
## Deteccion de versiones
Esta funcion intentara determinar los servicios presentes en los [[puerto]]s abiertos encontrados, y sus respectivas versiones, para activarlo se usa la opcion -Sv.
Tambien puede establecerse la intensidad de dicha busqueda, para especificar esto existen 2 formas:
- Nivel numerico de intensidad con --version-intensity (nivel). El nivel es un numero entero de 0 (baja intensidad) a 9 (maxima intensidad)
- Nivel expresado de forma literal:
	- Intensidad 2 con --version-light
	- Intensidad 9 con --version-all
# Ejemplo de comando

`nmap -Ss -p- -vvv --open -A 127.0.0.1 --max-rate 5000`
- -Ss: Establece tipo de escaneo [[SYN]]
- -p-: Escanear todos los [[puerto]]s
- -vvv: Entrega la mayor cantidad de informacion disponible
- --open: el resultado final solo incluye [[puerto]]s abiertos encontrados
- -A: Modo agresivo, usa todas las funciones de nmap para descubrir la mayor cantidad de informacion posible
- 127.0.0.1: [[ip]] de ejemplo, debe ser reemplazado por la del objetivo
- --max-rate 5000: Velocidad de envio de paquetes, en este caso se establece en 5000, si bien aumenta considerablemente la velocidad del escaneo, tambien lo hace mas "ruidoso" por lo que se recomienda precaucion al usarlo dependiendo del nivel de defensa esperado
