# Nombres estructurados

## Espacios de nombres

Por lo general, los nombres están organizados en lo que conocemos como espacio de nombre. Los espacios de nombre se pueden representar como un gráfico etiquetado y dirigido con dos tipos de nodos.
- Nodo hoja.
- Nodo directorio.

## Resolución de nombres

Los espacios de nombre ofrecen un mecanismo apropiado para almacenar y recuperar información con respecto a las entidades por medio de nombres. De manera más general, dado el nombre de una ruta, debiera ser posible buscar cualquier información almacenada en el nodo referido por dicho nombre. Al proceso de búsqueda de un nombre se le llama resolución de nombre.

### Mecanismo de clausura

Saber cómo y en dónde comenzar la resolución de nombres es conocido, por lo general, como el mecanismo de clausura. De manera esencial, un mecanismo de clausura trata con la selección del nodo inicial dentro de un espacio de nombres en el cual empieza la resolución de nombres

### Vinculación y montaje

El uso de un alias se encuentra fuertemente relacionado con la resolución de nombres. Un alias es otro nombre para la misma entidad. Se puede hacer de 2 formas:
- vínculos absolutos.
- Vínculos simbólicos

La resolución de nombres descrita hasta aquí tiene lugar por completo dentro de un solo espacio de nombres. Sin embargo, la resolución de nombres también se puede utilizar para mezclar diferentes espacios de nombre en forma transparente. Esto se hace con **puntos de montaje**. 

Para montar un espacio de nombres externo dentro de un sistema distribuido se requiere al menos la siguiente información:
- El nombre de un protocolo de acceso.
- El nombre de un servidor.
- El nombre del punto de montaje del espacio de nombres externo.

## Implementando espacios de nombres
Básicamente son servidores de nombre.

### Distribución de espacios de nombres
Se hace a traves de capas:
- Capa global
- Capa de administración
- Capa de direccionamiento

### Implementación de resolución de nombres
Tenemos de 2 tipos:
- Iterativa.
- Recursiva.