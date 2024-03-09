#recon #discovery
Herramienta usada principalmente para el escaneo de [[puerto]]s.
Para hacerlo envía solicitudes al objetivo, las cuales pueden ser en diferentes formatos dependiendo que se busca
# Opciones
## Tipo de escaneo -S
- Ss: Escaneo de tipo [[SYN]], durante este escaneo, el protocolo [[TCP]] es interrumpido al recibir al recibir el [[paquete]] [[SYN-ACK]], con lo cual se logra una mayor velocidad comparado a un escaneo [[TCP]]
- Su: Escaneo de tipo [[UDP]], normalmente usado para buscar servicios de streaming o similares
## Puertos objetivo -p
Existen varios formatos para establecer que [[puerto]]s se quieren escanear:
- Si no se especifica ningún puerto, nmap escaneara los 1,000 puertos mas comunes
- -p- es usado para que nmap escanee todos los puertos
- -p(especificación): se puede especificar un [[puerto]] o un conjunto de estos para limitar el escaneo, su uso es el siguiente:
	- Para escanear SOLO el [[puerto]] 22 se usaría -p22, mientras que para establecer rango del 22 al 80 se usaría -p22-80, lo anterior escaneara todos los [[puerto]]s en ese rango incluyendo ambos limites. Otra posibilidad es encadenar rangos o [[puerto]]s, por ej: -p80,443,8080-9090
-  -F para un escaneo rápido, la selección de [[puerto]]s es similar al escaneo predeterminado, pero con esta opción se reduce aun mas la cantidad
- Para escanear solo los x [[puerto]]s mas comunes puede usarse la opción --top-ports (numero)
## Verbose
Esta opción es usada para controlar la cantidad de información que entrega nmap como output, si no se especifica esta opción, se entrega la cantidad mínima de información, a partir de ahí, se usa -v para aumentarlo, este puede ser usado hasta 3 veces (-vvv) para obtener la máxima salida de información

Es posible usar la bandera `--open` para limitar el output del resultado a solo los puertos abiertos, esto es recomendable a menos que se desee depurar algo.
## Detección de versiones
Esta función intentara determinar los servicios presentes en los [[puerto]]s abiertos encontrados, y sus respectivas versiones, para activarlo se usa la opcion -Sv.
También puede establecerse la intensidad de dicha búsqueda, para especificar esto existen 2 formas:
- Nivel numérico de intensidad con --version-intensity (nivel). El nivel es un numero entero de 0 (baja intensidad) a 9 (máxima intensidad)
- Nivel expresado de forma literal:
	- Intensidad 2 con --version-light
	- Intensidad 9 con --version-all
# Ejemplo de comando

`nmap -Ss -p- -vvv --open -A 127.0.0.1 --max-rate 5000`
- -Ss: Establece tipo de escaneo [[SYN]]
- -p-: Escanear todos los [[puerto]]s
- -vvv: Entrega la mayor cantidad de información disponible
- --open: el resultado final solo incluye [[puerto]]s abiertos encontrados
- -A: Modo agresivo, usa todas las funciones de nmap para descubrir la mayor cantidad de información posible
- 127.0.0.1: [[ip]] de ejemplo, debe ser reemplazado por la del objetivo
- --max-rate 5000: Velocidad de envio de [[paquete]]s, en este caso se establece en 5000, si bien aumenta considerablemente la velocidad del escaneo, también lo hace mas "ruidoso" por lo que se recomienda precaución al usarlo dependiendo del nivel de defensa esperado
