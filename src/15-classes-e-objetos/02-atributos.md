## 15.2 - Atributos

Você pode atribuir valores a uma [instância](08-glossario.md#instância) usando a notação de ponto:

```python
>>> blank.x = 3.0
>>> blank.y = 4.0
```

Essa sintaxe é semelhante à usada para selecionar uma variável de um módulo, como math.pi ou string.whitespace. Nesse caso, entretanto, estamos atribuindo valores a elementos nomeados de um objeto. Esses elementos chamam-se atributos.

Em inglês, quando é um substantivo, a palavra “AT-trib-ute” é pronunciada com ênfase na primeira sílaba, ao contrário de “a-TRIB-ute”, que é um verbo.

O diagrama seguinte mostra o resultado dessas atribuições. Um diagrama de estado que mostra um objeto e seus atributos chama-se [diagrama de objeto](08-glossario.md#diagrama-de-objeto); veja a Figura 15.1.

![Figura 15.1 – Diagrama de um objeto Point](/fig/tnkp_1501.png).
<br>_Figura 15.1 – Diagrama de um objeto_ `Point`.

A variável blank refere-se a um objeto `Point`, que contém dois atributos. Cada [atributo](08-glossario.md#atributo) refere-se a um número de ponto flutuante.

Você pode ler o valor de um atributo usando a mesma sintaxe:

```python
>>> blank.y
4.0
>>> x = blank.x
>>> x
3.0
```

A expressão `blank.x` significa “Vá ao objeto a que blank se refere e pegue o valor de x”. No exemplo, atribuímos este valor a uma variável `x`. Não há nenhum conflito entre a variável `x` e o atributo `x`.

Você pode usar a notação de ponto como parte de qualquer expressão. Por exemplo:

```python
>>> '(%g, %g)' % (blank.x, blank.y)
'(3.0, 4.0)'
>>> distance = math.sqrt(blank.x ** 2 + blank.y ** 2)
>>> distance
5.0
```

Você pode passar uma instância como argumento da forma habitual. Por exemplo:

```python
def print_point(p):
    print('(%g, %g)' % (p.x, p.y))
```

`print_point` toma um ponto como argumento e o exibe em notação matemática. Para invocá-lo, você pode passar `blank` como argumento:

```python
>>> print_point(blank)
(3.0, 4.0)
```

Dentro da função, `p` é um alias para `blank`, então, se a função altera `p`, `blank` também muda.

Como exercício, escreva uma função chamada `distance_between_points`, que toma dois pontos como argumentos e retorna a distância entre eles.
