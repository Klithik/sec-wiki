_Secure SHell_ es una forma mas segura de enviar comandos a maquinas externas que nació como respuesta al aumento de [[sniffing]] que afectaba a [[telnet]]. Al iniciar una conexión SSH se establece una conexión [[TCP]] (también es posible usar SSH sobre un [[web socket]] pero generalmente no es así).
# Contenido del paquete de SSH

|        Longitud de paquete         |
| :--------------------------------: |
|        Cantidad de padding         |
|              Mensaje               |
|              Padding               |
| Código de autenticación de mensaje |

- La longitud del [[paquete]] simplemente es para informar que tan grande es el [[paquete]] que se esta enviando, contiene 4 [[byte]]s de información
- Cantidad de padding establece cuanto del mismo se puede esperar. El padding es información random que se mezclara con el [[paquete]] y la cantidad usada puede variar, ahí esta la importancia de este fragmente, el cual usa 1 [[byte]]
- El mensaje que desea enviar el usuario
- Padding, numero random de [[byte]]s de hasta 255 de longitud que se mezclan con el mensaje, de esta forma al encriptarlo se vuelve mas difícil de descifrar
- Código de autenticación, también llamado tag, se usa para verificar que el contenido del [[paquete]] no ha sido modificado con técnicas como [[MITM]]
También es común que se use alguna forma de comprensión sobre el [[paquete]]

Una vez formado el [[paquete]], se encripta de forma que si se usa [[sniffing]], lo único en texto plano que se observaría son la longitud del [[paquete]] y el código de autenticación. La forma de encriptación a usar es negociada entre el cliente y el servidor, lógicamente es posible para el servidor restringir la encriptación a usar para no permitir algoritmos de encriptación más débiles.
# Canales
Es posible utilizar canales durante conexiones SSH, lo cual hace posible tener múltiples conexiones SSH al mismo tiempo. También permite redirigir casi cualquier cosa a través de SSH, por ejemplo, en linux el administrador de ventanas mas común es X11, el cual es técnicamente posible enrutar a una maquina remota a través de SSH, permitiendo una forma de pantalla remota.