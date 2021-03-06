## 18.2 - Atributos de classe

Para exibir objetos Card de uma forma que as pessoas possam ler com facilidade, precisamos de um mapeamento dos códigos de número inteiro aos naipes e valores correspondentes. Uma forma natural de fazer isso é com listas de strings. Atribuímos essas listas a atributos de classe:

```python
# dentro da classe Card:

    suit_names = ['Clubs', 'Diamonds', 'Hearts', 'Spades']
    rank_names = [None, 'Ace', '2', '3', '4', '5', '6', '7',
                  '8', '9', '10', 'Jack', 'Queen', 'King']

    def __str__(self):
        return '%s of %s' % (Card.rank_names[self.rank],
                             Card.suit_names[self.suit])
```

Variáveis como `suit_names` e `rank_names`, que são definidas dentro de uma classe, mas fora de qualquer método, chamam-se atributos de classe porque são associadas com o objeto de classe Card.

Este termo as distingue de variáveis como `suit` e `rank`, chamadas de atributos de instância porque são associados com determinada instância.

Ambos os tipos de atributo são acessados usando a notação de ponto. Por exemplo, em `__str__`, `self` é um objeto `Card`, e `self.rank` é o seu valor. De forma semelhante, Card é um objeto de classe, e `Card.rank_names` é uma lista de strings associadas à essa classe.

Cada carta tem seu próprio suit e rank, mas há só uma cópia de suit_names e rank_names.

Juntando tudo, a expressão `Card.rank_names[self.rank]` significa “use o rank (valor) do atributo do objeto self como um índice na lista rank_names da classe Card e selecione a string adequada”.

O primeiro elemento de rank_names é None, porque não há nenhuma carta com valor zero. Incluindo None para ocupar uma variável, conseguimos fazer um belo mapeamento onde o índice 2 é associado à string '2', e assim por diante. Para evitar ter que usar esse truque, poderíamos usar um dicionário em vez de uma lista.

Com os métodos que temos por enquanto, podemos criar e exibir cartas:

```python
>>> card1 = Card(2, 11)
>>> print(card1)
Jack of Hearts
```

A Figura 18.1 é um diagrama do objeto de classe Card e uma instância de Card. Card é um objeto de classe; seu tipo é type. card1 é uma instância de Card, então seu tipo é Card. Para economizar espaço, não incluí o conteúdo de suit_names e rank_names.

![Figura 18.1 – Diagrama de objetos: classe Card e card1, uma instância de Card](/fig/tnkp_1801.png).
<br>_Figura 18.1 – Diagrama de objetos: classe_ `Card` _e_ `card1`, _uma instância de_ `Card`.
