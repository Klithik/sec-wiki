_Secure SHell_ es una forma mas segura de enviar comandos a maquinas externas que nacio como respuesta al aumento de [[sniffing]] que afectaba a [[telnet]]. Al iniciar una conexion SSH se establece una conexion [[TCP]] (tambien es posible usar SSH sobre un [[web socket]] pero generalmente no es asi).
# Contenido del paquete de SSH
![[contenidossh.png]]
- La longitud del paquete simplemente es para informar que tan grande es el paquete que se esta enviando, contiene 4 [[byte]]s de informacion
- Cantidad de padding establece cuanto del mismo se puede esperar. El padding es informacion random que se mezclara con el paquete y la cantidad usada puede variar, ahi esta la importancia de este fragmente, el cual usa 1 [[byte]]
- El mensaje que desea enviar el usuario
- Padding, numero random de [[byte]]s de hasta 255 de longitud que se mezclan con el mensaje, de esta forma al encriptarlo se vuelve mas dificil de decifrar
- Codigo de autenticacion, tambien llamado tag, se usa para verificar que el contenido del paquete no ha sido modificado con tecnicas como [[MITM]]
Tambien es comun que se use alguna forma de comprension sobre el paquete

Una vez formado el paquete, se encripta de forma que si se usa [[sniffing]], lo unico en texto plano que se observaria son la longitud del paquete y el codigo de autenticacion. La forma de encriptacion a usar es negociada entre el cliente y el servidor, logicamente es posible para el servidor restringir la encriptacion a usar para no permitir algoritmos de encriptacion mas debiles.
# Canales
Es posible utilizar canales durante conexiones SSH, lo cual hace posible tener multiples conexiones SSH al mismo tiempo. Tambien permite redirigir casi cualquier cosa a traves de SSH, por ejemplo, en linux el administrador de ventanas mas comun es X11, el cual es tencnicamente posible enrutar a una maquina remota a traves de SSH, permitiendo una forma de pantalla remota.