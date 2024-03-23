# Funciones
## Enumeración
### SMB
`nxc smb <ip de red>/<mascara de red>`
Esta función lista todos los equipos dentro de la red que tienen un servicio [[SMB]] activo. Es posible agregarle mas argumentos que actúan como filtro en la búsqueda
#### Usuario
Al comando de ejemplo de enumeración [[SMB]] es posible agregarle filtro de usuario con `-u '<user>'`. Este flag hará que NetExec busque servicios [[SMB]] dentro de la red que tengan dicho usuario habilitado, podría ser interesante buscar usuarios nulos con un string vacío, o el usuario "guest".
#### Contraseña
Es posible que NetExec pruebe alguna contraseña en cada resultado de busqueda, por lo que si se combina con el filtro de usuario puede usarse para revisar credenciales por defecto, para filtrar por contraseña simplemente se usa `-p '<contraseña>'`.