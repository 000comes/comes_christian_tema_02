# Problemas encontrados durante la práctica de UD2

## 1.- Fallo de redireccionamient mediante navegación relativa en la linea:
`<a href="cluster01elgermen.html">Entrada de muestra</a>`
Al probar la navegación en el navegador ontegrado de vsCode recibimos el siguiente error:
"`Failed to Load Page
ERR_UNEXPECTED (-9)
URL: file:///run/media/kolvert/Datos/ASIR/Primero/Lenguajes%20de%20Marcage/practica_ChristianComes/ChristianComes_Homlab_PortfolioV1/cluster01elgermen.html`"

Revisando el error y la ruta vemos que el problema es la ruta. a href = "cluster01elgermen.html" asume qe la página está en la misma carpeta que sobremi.html

Editamos a:
`<a href="/content/posts/cluster01elgermen.html">Entrada de muestra</a>`
