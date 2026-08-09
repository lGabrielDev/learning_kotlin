# Estrutura de dados

As mais utilizadas são essas:

- `Array`
- `List`
- `MutableList`
- `Map`
- `MutableMap`

---

## Arrays

Um Array armazena vários elementos do mesmo tipo e possui tamanho fixo.

:warning: Não pode adicionar novos itens, pois a Array tem um tamanho fixo.

```kotlin
fun main(args: Array<String>) {

    val lista: Array<String> = arrayOf("batman", "coringa", "naruto"); // ou
    val lista: Array<Int?> = arrayOf(22, null, 44); // lista com null

    lista[0] = "outro valor"

    println(lista[0])
    println(lista[1])
    println(lista[2])

}
```

---

## List

Não dá pra fazer porra nenhuma. Um List serve apenas para leitura.

- :warning: Não pode alterar o valor dos itens.
- :warning: Não pode adicionar novos itens nela.

```kotlin
val lista: List<String> = listOf("batman", "coringa", "naruto");
```

<br>

## MutableList

Como se fosse uma ArrayList do Java. Podemos fazer a porra toda.

```kotlin
fun main(args: Array<String>) {

    val lista: MutableList<String> = mutableListOf("batman", "coringa", "naruto");

    lista[0] = "outro valor"; //podemos atribuir outro valor aos itens
    lista.add("sonic"); //podemos adicionar ou remover itens
}
```

:book: Mesmo sendo `val` voce pode sim alterar os itens da lista. O que não pode ser feito é atribuir uma outra lista a essa variable.

---

## Map
Não dá pra fazer porra nenhuma. Um `Map` serve apenas para leitura.

- :warning: Não pode alterar o valor dos itens.
- :warning: Não pode adicionar novos itens nela.

```kotlin
fun main(args: Array<String>) {
    val lista: Map<Int, String> = mapOf(
        0 to "sonic",
        1 to "augusto",
        2 to "lucian"
    );
}
```

<br>

## MutableMap

Como se fosse uma HashMap do Java. Podemos fazer a porra toda.

```kotlin
fun main(args: Array<String>) {

    val lista: MutableMap<Int, String> = mutableMapOf(
        0 to "sonic",
        1 to "augusto",
        2 to "lucian"
    );

    lista[0] = "outro personagem"; //podemos alterar um item
    lista[100] = "outro personagem 2"; //podemos adicionar ou remover itens. Adicionamos like array mesmo kk
    
    lista.forEach {
        println("${it.key} ${it.value}");
    }
}
```

<br>

### Percorrendo os indices da lista

:pencil2: Crie uma lista e altere os valores dos itens que são pares.

```kotlin
fun main(args: Array<String>) {

    val lista: MutableList<String> = mutableListOf(
        "carlos",
        "rosana",
        "amanda",
        "pedro"
    );

    for(i in lista.indices){
        if(i % 2 == 0) lista[i] = "personagem PAR";
    }

    lista.forEach { println(it) }
}
```