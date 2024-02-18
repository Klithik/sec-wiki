Herramienta usada para ataques de fuerza bruta, es capaz de usarse sobre formularios web y ssh
# Plantilla comando para formulario web
`sudo hydra -l/L <Username/List> -p/P <Password/List> <IP> <Method> "<Path>:<RequestBody>:<IncorrectVerbiage>"`
- para determinar si usar -l o -L, solo se debe saber si se quiere probar una lista de usuarios o un solo usuario, cuando se quiere usar un solo valor en lugar de una lista, se usa la minuscula, para la contraseña funciona exactamente igual
- El metodo puede ser http-post-form
- el contenido de la request suele ser `username=admin&password=^PASS^`, el contenido de cada variable depende de si se esta usando una lista o un valor estatico, y el nombre de cada variable se puede averiguar inspeccionando el post que envia el formulario