## 2.5 - Ordem das operações

Quando uma [expressão](09-glossario.md#expressão) contém mais de um operador, a ordem da avaliação depende da [ordem das operações](09-glossario.md#ordem-das-operações). Para operadores matemáticos, o Python segue a convenção matemática. O acrônimo PEMDAS pode ser útil para lembrar das regras:

* Os Parênteses têm a precedência mais alta e podem ser usados para forçar a avaliação de uma expressão na ordem que você quiser. Como as expressões em parênteses são avaliadas primeiro, `2 * (3-1)` é 4, e `(1+1)**(5-2)` é 8. Também é possível usar parênteses para facilitar a leitura de uma expressão, como no caso de `(minute * 100) / 60`, mesmo se o resultado não for alterado.

* A Exponenciação tem a próxima precedência mais alta, então `1 + 2**3` é 9, não 27, e `2 * 3**2` é 18, não 36.

* A Multiplicação e a Divisão têm precedência mais alta que a Adição e a Subtração. Assim, `2 * 3 - 1` é 5, não 4, e `6 + 4 / 2` é 8, não 5.

* Os operadores com a mesma precedência são avaliados da esquerda para a direita (exceto na exponenciação). Assim, na expressão `degrees / 2 * pi`, a divisão acontece primeiro e o resultado é multiplicado por `pi`. Para dividir por 2π, você pode usar parênteses ou escrever `degrees / 2 / pi`.

Eu não fico sempre tentando lembrar da precedência de operadores. Se a expressão não estiver clara à primeira vista, uso parênteses para fazer isso.
