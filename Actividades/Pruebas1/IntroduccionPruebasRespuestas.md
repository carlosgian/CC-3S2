**Ejercicios 5**

Supongamos que deseas dividir el espacio de entrada de esta función de raíz cuadrada:

```
/**
 * @param x debe ser no negativo
 * @retorna la raiz cuadrada de x
 */
public static int sqrt(int x)
```

Evalúe la calidad de cada una de las siguientes particiones candidatas. ¿Son los subdominios propuestos separados y completos, formando así una partición? ¿Son correctos, en el sentido de que cada subdominio puede ser cubierto por un caso de prueba legal? Para una buena partición debes marcar las tres alternativas.

```
// particion: x < 0; x >= 0
```

- Los subdominios son disjuntos ( VERDADERO )
- Los subdominios están completos ( VERDADERO ) sí, incluye todo el epacio de entrada.
- Los subdominios son correctos (FALSO)
No son correctos, puesto que no se puede evaluar los valores menores que 0.


```
// particion: x es un cuadrado perfecto; x es > 0 pero no es un cuadrado perfecto

```

- Los subdominios son disjuntos ( VERDADERO )
- Los subdominios están completos ( VERDADERO )
- Los subdominios son correctos ( VERDADERO )
Los subdominios son disjuntos, completos(incluyen todo el espacio de entrada) y se pueden construir pruebas legales para un elemento de cualquier subdominio.

```
// particion: x=0, x=1, x=7, x=16
``` 

- Los subdominios son disjuntos( VERDADERO )
- Los subdominios están completos (FALSO)
- Los subdominios son correctos (FALSO)

**Ejercicio 6**

Ahora considera esta especificación:

```
/**
 * @param x un entero 
 * @param y un entero, donde x, y no son ambos 0
 * @retorna el GCD de x e y
 */
/
public static int gcd(int x, int y);
```

Evalúa cada una de las siguientes particiones candidatas para gcd.

```
// particion: x e y no son  0
``` 

- Los subdominios son disjuntos (VERDADERO) Solo es un conjunto.
- Los subdominios están completos (VERDADERO) Es una partición trivial.
- Los subdominios son correctos (FALSO) Es demasiado trivial para ser de utilidad.

```
// particion: x es divisible por y; y es divisible por x; x e y son primeros relativos
```
`
- Los subdominios son disjuntos (FALSO)
- Los subdominios están completos (FALSO) Ejm: El par ordenado (4,6) no pertenece a ninguno de los subdominios.
- Los subdominios son correctos (FALSO)

**Ejercicio 7**

Para esta función: 

```
/**`
 * @param winsAndLosses una cadena de a lo más 5 de consistiendo de los caracteres 'W' o 'L'
 * @retorna la fraccion de caracteres en winsAndLosses que son 'W'
 */

double winLossRatio(String winsAndLosses);
```
¿Cuáles son los valores límite apropiados para probar esta función?
5 W's o 5 L's.
1 W y 4 L's
1 L y 4 W's
**Ejercicio 8**

Considera la partición de `a` anterior:

```
// particion en a:
//     a = 0
//     a = 1
//     a es un entero pequeño > 1
//     a es un entero pequeño < 0
//     a es un entero grande positivo
//      a es un entero grande negativo (donde "pequeño" encaja en long y "grande" no)
```

Esta partición en realidad combina varios intereses distintos: el signo de `a`, la magnitud de `a` (pequeño o grande) y los valores límite 0 y 1. Podemos pensar en estos intereses como particiones independientes.
De entre las opciones a continuación, elija un subconjunto que serían particiones legales y que juntas captarían los mismos intereses.

- particion en a: `0, 1`                       I
- particion en a: `0`                          II
- particion en a: `1`                          III
- particion en a: `0`, positivo, negativo      IV
- particion en a: positivo, negativo           V
- particion en a: `1, !=1`                     VI
- particion en a: (donde "pequeño" encaja en long y "grande" no)
II y V
V
VI
IV

**Ejercicio 9**

Considera nuevamente esta partición `a` en un desde arriba:

```
// particion en a:
//     a = 0
//     a = 1
//     a es un entero pequeño > 1
//     a es un entero pequeño < 0
//     a es un entero grande positivo
//      a es un entero grande negativo (donde "pequeño" encaja en long y "grande" no)
```

Esta partición tiene 6 subdominios, por lo que pueden cubrirla 6 valores diferentes de `a`, uno elegido para cada subdominio. 

Supongamos que usamos estas tres particiones de a en su lugar:

```
// particion en a: 0, positivo, negativo
// particion en a: 1, !=1
// particion on a: donde "pequeño" encaja en long y "grande" no)
```

Si solo queremos cubrir cada subdominio de las tres particiones, ¿cuántos valores diferentes de a necesitaríamos?.
Si escojo el 0 y el 1, cubro la partición 0, 1, !=1, y "Pequeño"(que encaja en long)
Y si agrego un número negativo muy grande entonces cubro, el "grande" que no encaja en long.
Es decir, solo necesito 3 números: 0, 1, (un número negativo muy grande)


**Ejercicio 10**

A veces es conveniente pensar y escribir una partición de espacio de entrada en términos de la salida de la función, porque las variaciones en el comportamiento pueden ser más visibles allí. Por ejemplo: 

```
// particion en a.multiply(b): 0, positivo, negativo

```
es la abreviatura de la partición de tres subdominios que consta de:

```
 { (a,b) | a.multiply(b) = 0 }
 { (a,b) | a.multiply(b) > 0 }
 { (a,b) | a.multiply(b) < 0 }

```
Con este enfoque, ¿cuántos casos de prueba se necesitan para cubrir las siguientes tres particiones? 

```
// particion en a: 0, positivo, negativo
// particion en b: 0, positive, negativo
// particion en a.multiply(b): 0, positivo, negativo
````
Solamente 3, una donde el resultado de a*b sea 0, otra donde sea positivo, y otro donde sea negativo.


