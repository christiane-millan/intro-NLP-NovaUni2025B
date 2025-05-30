# 2. Representación del texto





## 1. Expresiones regulares


## Buscar y reemplazar

Un ejemplo común del uso de expresiones regulares (regex) es buscar y reemplazar. Por ejemplo, los editores de palabras como Microsoft Word incorporan esta característica. 

Existen algunas limitaciones de *buscar y reemplazar*.

```text
The cat chased the mouse. The cat caught the mouse.
```

Si se desea cambia *cat* por *dog*

```text
The dog chased the mouse. The dog caught the mouse.
```

Implementación:

```python
import re
text = "The cat chased the mouse. The cat caught the mouse."

new_text = text.replace('cat', 'dog')
new_text
```

salida

```text
'The dog chased the mouse. The dog caught the mouse.'
```

Qué pasa si aplicamos `replace` a una sentencia más compleja:

```python
text = "The cat chased the mouse deep down into the catacombs. The cat would reach a state of catharsis if it were to catch that mouse."

new_text = text.replace('cat', 'dog')
new_text
```

salida

```text
'The dog chased the mouse deep down into the dogacombs. The dog would reach a state of dogharsis if it were to dogch that mouse.'
```

El resultado no es el esperado, por que *cat* terminan correspondiendo no solo con *cat*, si no con toda palabra con *cat* en ella, incluyendo *catharsis* y *catacombs*.

Las expresiones regulares nos permiten trabajar con patrones, por lo que no estamos limitados solo a buscar correspondencias con *cat*, se puede buscar patrones que correspondan con:

- *cat* cuando esta al principio de la palabra
- *cat* cuando esta al final de la palabra
- *cat* cuando es una sola palabra
- *cat* cuando aparezca más de tres veces en una sola sentencia.

> En el ejemplo, se necesita encontrar *cat* como una sola palabra y no como parte de otras palabras, como *catharsis*.

**Con regex podemos resolver estos problemas.**

El poder de  regex es encontrar, si y donde, los patrones ocurren. Si tuviéramos un millón de facturas y no se pueden poner en un Excel y necesitamos filtrar rápidamente las cantidades de seis cifras, o se tiene un pdf de 500 páginas y se necesita resaltar los sustantivos propios, nombres de personas y lugares. Mediante expresiones regulares tenemos la posibilidad esos sustituir esos patrones.

[Ejemplo : `Expresiones regulares`](./code/01-2_regex_fundamentals.ipynb)