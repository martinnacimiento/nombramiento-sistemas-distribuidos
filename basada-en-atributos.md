# Nombres basados en atributos
Consiste en que cada entidad tendrá una colección de atributos con sus respectivos valores. Puede verse como registros de pares de (atributo, valor).

## Servicios de directorios
Con este tipo de nombres, en lugar de llamarlo "sistema de nombres", se lo llama "Servicio de directorios".

El diseño de un conjunto adecuado de atributos no es algo trivial. Para mitigar problemas, la investigación se ha encaminado a unificar las formas en que pueden describirse los recursos. Por eso, RDF (Marco de descripción de recursos) es importante. Los recursos se describen como tríos que constan de un sujeto, un predicado, y un objeto. Por ejemplo, (Persona, nombre, Alice) describe un recurso Persona cuyo nombre es Alice.

Si las descripciones de recursos se almacenan, se hace posible consultar ese almacén de una
forma común para muchos sistemas de nombres basados en atributos. Cuando se considera el rendimiento, tal búsqueda es un problema menor dentro de un solo almacén de datos, pero
se necesita aplicar técnicas por separado cuando los datos están distribuidos en diversas, y potencialmente dispersas, computadoras.

A continuación veremos diferentes métodos útiles para resolver
este problema en sistemas distribuidos.

## Implementaciones jerárquicas: LDAP
Un método común para abordar los servicios distribuidos de directorio es combinar nombres estructurados con nombres basados en atributos. Muchos de estos sistemas utilizan o se basan en el LDAP (protocolo ligero de acceso a directorios).

En forma conceptual, un servicio de directorio LDAP consta de cierto número de registros, generalmente conocidos como entradas de directorio. Cada registro se conforma con una colección de pares (atributo, valor), donde cada atributo tiene un tipo asociado. Toda esa colección recibe nombre de directorio de información base (DIB). Los aspectos del DIB son:
- cada registro tiene un nombre único para que pueda ser buscado, aparece como una secuencia de atributos de nombre en cada registro.
- Cada atributo de nombre se conoce como nombre relativo diferenciado, o RDN.

Como en DNS, el uso de nombres globalmente únicos listando RDN en secuencia conduce a una colección jerárquica de entradas de directorio, lo cual se conoce como árbol de información de directorio (DIT, por sus siglas en inglés). Un DIT forma, esencialmente, el grafo de nombres de un servicio de directorio LDAP, en la que cada nodo representa una entrada de directorio.

## Implementación distribuida
El punto clave aquí es que los pares (atributo, valor) necesitan estar mapeados de manera eficiente para que la búsqueda sea también eficiente, esto es, evitar una búsqueda exhaustiva a través de todo el espacio de atributos. A continuación daremos un vistazo a las diferentes formas de establecer dicho mapeo:
- Mapeo hacia tablas hash distribuidas.
- Redes sobrepuestas semánticas
