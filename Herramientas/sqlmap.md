Herramienta que automatiza ataques con [[inyeccion SQL]]
# Ejemplos de uso

## Verificar si variable es inyectable
`sqlmap -r (archivo) -p username`
- -r es para especificar un archivo como entrada, este archivo puede ser la solicitud POST capturada con herramientas como burpsuite al momento de intentar iniciar sesion
- -p especifica parametros a revisar para saber si son inyectables, en este caso, se revisaria username