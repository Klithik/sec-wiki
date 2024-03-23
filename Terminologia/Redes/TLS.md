Originalmente conocido como [[SSL]] 3.1, TLS es un protocolo para encriptar las comunicaciones entre aplicaciones web y servidores, así como los navegadores cargando una pagina web. También es usado para encriptar otros servicios como VoIP, correos electrónicos  u otros.

[[http|https]] es, esencialmente, la aplicación de la encriptación TLS sobre [[http]], y el objetivo de su uso se divide en 3 partes:
- Ocultar la información transferida de terceros
- Garantizar la identidad de las partes, es decir, que sean quienes dicen ser
- Garantizar que el contenido de la comunicación no ha sido modificado (por ataques como [[MITM]])

# Funcionamiento
TLS inicia usando un _protocolo de enlace TLS_, en el cual tanto el cliente como el servidor:
- Especifican que versión de TLS van a utilizar
- Decidir la suite de cifrado a utilizar
- Autentican identidades
- Generan claves de sesión para cifrar la información una vez establecida la conexión
TLS utiliza claves de sesión para tener un conjunto de cifrado para cada sesión diferente. El conjunto o _suite_ de cifrado es una serie de algoritmos que especifica detalles como las claves de encriptación a utilizar, para poder usar esta función a través de una comunicación no encriptada, TLS emplea la [[criptografia de llave publica]].

Una vez los datos son encriptados y autenticados, se firman con un [[MAC]], el cual puede ser verificado por el destinatario para asegurar la integridad de los datos.

![[representacionTLS.png]]