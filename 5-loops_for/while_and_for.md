# Loops

## Diferença entre while() e for()

- O `while` e o `do while` são usados quando não sabemos exatamente quantas vezes o código precisará ser repetido. A repetição continua enquanto uma condição for verdadeira.

- Já o `for` é normalmente usado quando sabemos quantas vezes queremos repetir o código.

---

## `while(){}`

Verifica a condição antes de entrar no bloco de código.

```kotlin
fun main(args: Array<String>) {

    var contador = 0;

    while(contador < 5){
        println("olá $contador");
        contador++;
    }
}
```

---

## `do{} while()`

Executa o código antes de verificar a condição. Ou seja, o código é executado pelo menos uma vez, mesmo que a condição seja false.

```kotlin
fun main(args: Array<String>) {

    var codigoDeveSerExecutado: Boolean = false;

    do{
        println("olá")
    } while(codigoDeveSerExecutado);
}
```

Mesmo tendo uma condicao false, o codigo foi loopado 1 vez.

---

## `for()`


### Percorrendo uma lista qualquer

```kotlin
fun main(args: Array<String>) {

    val listaPessoas: MutableList<Person> = mutableListOf(
        Person("goku", 33),
        Person("naruto", 55),
        Person("sasuke", 66)
    );

    for(i: Person in listaPessoas){
        println(i);
    }
}
```

Igualzinho ao Java. Temos uma variable/objeto `i` que representa cada item da lista.

<br>

### Percorrendo as letras de uma String

```kotlin
fun main(args: Array<String>) {

    val palavraInsana: String = "goku insano";

    for(i: Char in palavraInsana){
        println(i);
    }
}
```

<br>

### Percorrendo um range de numeros

```kotlin
fun main(args: Array<String>) {
    
    for(i: Int in 0..25){
        println(i);
    }
}
```

📖 Funciona da mesma forma. Estamos percorrendo uma lista / estrutura de algum tipo de dado. Nesse caso, é uma lista de inteiros.