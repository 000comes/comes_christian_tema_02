| **#** | Sesión 1 — index.html  |   |
|-------|---|---|
| **1** | Objetivo  | Revisar semánticamente la portada (index.html) tras redactarla. |   |   
| **2** | Entrada | Versión de index.html con `<article>` envolviendo todo el contenido y `<ol>` de un único enlace en "Proyectos".  |   | 
| **3** | Respuesta relevante |  (1) Cambiar `<ol>` por `<ul>` en la lista de Proyectos, ya que no hay secuencia — utilizada parcialmente: la lista sigue como `<ol>`pero ahora con 2 entradas reales; no se cambió a `<ul>`. (2) Sustituir `<article>` por `<div>` si el contenido no tiene sentido fuera de la portada — rechazada/pendiente: se mantiene `<article>`, decisión editorial no confirmada explícitamente. |   | 
| **4** | Verificación  | Revisar en el árbol de accesibilidad si la lista se anuncia como ordenada o no; comprobar si el contenido tendría sentido distribuido aparte. |   | 
| **5** | Correcciones | Entendí que `<ol>` comunica orden/secuencia, no solo "lista de enlaces".  |   |
| **6** | Aprendizaje  |La diferencia principal entre `<ul>`y `<ol>` es que `<ol>` se utiliza cuando hay un orden concreto a seguir, como en unas instrucciones, o los pasos de una receta. |   | 



| **#** |  Sesión 2 — proyectos.html |   |
|-------|---|---|
| **1** | Objetivo  |Revisar semánticamente proyectos.html, centrado en identificadores y la lista de proyectos.  |   |  
| **2** | Entrada |	Versión con `id="proyectos"` duplicado entre `<article>` y `<h2>`, y `<ol>` con un único enlace sin proyecto real que enlazar.   |   |  
| **3** | Respuesta relevante |(1) Cambiar el id del `<article>` a uno único (p. ej. proyectos-articulo), conservando el del `<h2>` — utilizada. (2) Retirar la lista o dejarla pendiente hasta tener proyectos reales; cuando los haya, enlazarlos y decidir `<ul>/<ol>` según si el orden importa — aplicada parcialmente: ya hay un enlace real a Clúster 01, pero sigue sin decidirse `<ul>` vs `<ol>`.   |   |   
| **4** | Verificación  | 	Pasar el HTML por un validador y comprobar que no informe de IDs duplicados; confirmar que `aria-labelledby` y `#proyectoscatalogo/#proyectosrecientes` apuntan al elemento correcto.  |   |   
| **5** | Correcciones |`id` del `<article>` cambiado de `"proyectos"` a `"proyectoscatalogo"`. Enlace a `cluster01elgermen.html` añadido en la lista.  |   |   
| **6** | Aprendizaje  | Un id duplicado rompe las referencias ARIA y de anclaje aunque no lo parezca porque el navegador no parece bloquearlo visualmente.  |   |  

| **#** | Sesión 3 — cluster01elgermen.html (estructura de listas y párrafos)  |   |
|-------|---|---|
| **1** | Objetivo  | Revisar semánticamente el artículo del clúster, foco en listas y párrafos de Hardware y Documentación. |   |  
| **2** | Entrada | Versión con `<ol>` para componentes de hardware, lista del switch fuera de su `<li>`, lista y figura dentro del mismo `<p>` que "El hardware:", y un `<p>` anidado dentro de otro en "Sobre la Documentación".  |   |  
| **3** | Respuesta relevante |  (1) Separar "El hardware:" en párrafo propio, lista y figura fuera del `<p>` — utilizada. (2) Mover el `<ul>` del switch dentro de su `<li>` — rechazada/pendiente (sigue sin aplicarse). (3) Cerrar el primer párrafo de Documentación antes del texto "Todos los datos..." — utilizada. (4) Cambiar `<ol>` por `<ul>` en componentes de hardware, al no tener orden significativo — utilizada. |   |   
| **4** | Verificación  |Validar el documento; comprobar que la lista y la figura no son descendientes de un `<p>`; comprobar que los párrafos aparecen como hermanos en el DOM; confirmar si existe un criterio intencional de orden en la lista de hardware.|   |   
| **5** | Correcciones |  `<p>`El hardware:`</p>` separado de `<ul>` y `<figure>`. Lista de componentes cambiada de `<ol>` a `<ul>`. Los dos párrafos de Documentación separados correctamente. |   |   
| **6** | Aprendizaje  | Un `<p>` no debe contener listas ni figuras; el navegador cierra el párrafo implícitamente antes, lo que deja el DOM distinto de lo que parece en el código fuente.  |   |  

| **#** |  Sesión 4 — cluster01elgermen.html (jerarquía y cierre de artículo) |   |
|-------|---|---|
| **1** | Objetivo  |	Revisar semánticamente la jerarquía de encabezados y la estructura del `<article>` del clúster.  |   |  
| **2** | Entrada | 	Versión con `<article>` cerrándose justo tras abrirse (cierre duplicado más abajo), encabezado principal como `<h2>` en vez de `<h1>`, y una `<section>` vacía tras la figura.  |   |  
| **3** | Respuesta relevante | (1) Quitar el cierre inmediato del `<article>`, conservar el cierre tras el contenido — utilizada. (2) Cambiar el `<h2>` de "Clúster 01 - El germen" a `<h1>` — utilizada. (3) Eliminar la `<section>` vacía si no contiene nada previsto — utilizada.  |   |   
| **4** | Verificación  |Validar el HTML y comprobar en el árbol DOM que el encabezado, la sinopsis y la figura son descendientes del `<article>`; revisar el esquema de encabezados; confirmar que no queda ninguna `<section>` vacía.   |   |   
| **5** | Correcciones |  `<h1>`Clúster 01 - El germen`</h1>` como encabezado principal. Cierre de `<article>` movido al final del contenido. Sección vacía eliminada. |   |   
| **6** | Aprendizaje  | El navegador reconstruye el DOM aunque el HTML de origen tenga etiquetas mal cerradas, por lo que "verse bien" no garantiza una jerarquía correcta.  |   |   



| **#** | Sesión 5 — cluster01elgermen.html (sublista del switch, pendiente)  |   |
|-------|---|---|
| **1** | Objetivo  | Confirmar si quedaban problemas tras las correcciones de listas, párrafos y jerarquía. |   |  
| **2** | Entrada | Versión actual con hardware/arquitectura ya en `<ul>` y párrafos corregidos.  |   |  
| **3** | Respuesta relevante |Mantener la sublista de características dentro del `<li>` «Switch gestionable Zyxel GS1200-8», cerrando ese elemento después de la sublista — pendiente, no aplicada.   |   |   
| **4** | Verificación  |Pasar el documento por un validador y comprobar que el `<ul>` de características está dentro del `<li>` del switch en el DOM.   |   |   
| **5** | Correcciones |Corrijo la anidación ya que `<ul>` unifica los elementos de una lista y por eso debe identificarse la sublista dentro del `<li>` correspondiente al switch   |   |   
| **6** | Aprendizaje  |  Comprendo que `<ul>` identifica una lista o sublista según la anidación, pero si en una lista aparece una sublista, esta debe ir correctamente identificada con sus `<ul></ul>`. |   |  