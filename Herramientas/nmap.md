Herramienta usada principalmente para el escaneo de [[puerto]]s.
Para hacerlo envia solicitudes al objetivo, las cuales pueden ser en diferentes formatos dependiendo que se busca, el tipo de solicitud enviada es definida por el argumento -S, las principales opciones son:
- *Ss*: Protocolo [[SYN]]
- *Su*: Protocolo [[UDP]]
- *Sx*: Escaneo de tipo [[Xmas]]
# Ejemplo de comando

_nmap -Ss -p- -vvv --open -A 127.0.0.1 --max-rate 5000_
- -Ss: Establece tipo de escaneo [[SYN]]
- -p-: Escanear todos los [[puerto]]s
- -vvv: Entrega la mayor cantidad de informacion disponible
- --open: el resultado final solo incluye [[puerto]]s abiertos encontrados
- -A: Modo agresivo, ademas del escaneo de [[puerto]]s, intenta determinar la version de [[OS]] en el objetivo, y ejecuta scripts para determinar versiones de servicios presentes
- 127.0.0.1: [[ip]] de ejemplo, debe ser reemplazado por la del objetivo
- --max-rate 5000: Velocidad de envio de paquetes, en este caso se establece en 5000, si bien aumenta considerablemente la velocidad del escaneo, tambien lo hace mas "ruidoso" por lo que se recomienda precaucion al usarlo dependiendo del nivel de defensa esperado