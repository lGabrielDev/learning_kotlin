# Recriando funcoes do kotlin

Agora que já temos uma base sobre funções, podemos recriar algumas das funções mais utilizadas do Kotlin.

Quando trabalhamos com estruturas de dados, como listas e arrays, podemos utilizar diversas funções já prontas do Kotlin, como:

- `forEach`
- `filter`
- `map`
- `sort`
- etc.

Vamos criar na mão essas funções para entender como elas funcionam por baixo dos panos.

<hr>

## forEach()

O forEach percorre todos os elementos da lista e executa a Callback para cada elemento. Essa funcao não retorna nada.


```kotlin
fun <T> Iterable<T>.forEachNaMao( callback: (T) -> Unit ): Unit {
    for(i in this) callback(i);
}


fun main(args: Array<String>) {
    val lista1: MutableList<Int> = mutableListOf(80, 2, 7, 9,13, 400);
    lista1.forEachNaMao { println(it) };
}
```

---

## filter()

O filter percorre uma lista e utiliza uma Callback para decidir quais elementos devem permanecer. Se a Callback retornar true, o elemento é adicionado em uma nova lista. Se retornar false, ele é ignorado.

No final, o filter retorna a nova lista.


```kotlin
fun <T> Iterable<T>.filterNaMao(callback: (T) -> Boolean ): MutableList<T> {
    val novaLista: MutableList<T> = mutableListOf();

    for(i in this){
        if(callback(i)) novaLista.add(i);
    }
    return novaLista;
}


fun main(args: Array<String>) {
    val lista1: MutableList<Int> = mutableListOf(80, 2, 7, 9,13, 400);

    println(
        lista1.filterNaMao { it %2 == 0 }
    )
}

```


## map()

O map percorre uma lista e transforma cada elemento em um novo valor. No final, retorna uma nova lista com os elementos transformados.

```kotlin
fun <T, R> Iterable<T>.mapNaMao(callback: (T) ->  R): Iterable<R> {
    val novaLista: MutableList<R> = mutableListOf();
    
    for(i in this){ novaLista.add(callback(i)) }
    return novaLista;
}

fun main(args: Array<String>) {
    val lista1: MutableList<Int> = mutableListOf(80, 2, 7, 9,13, 400);

    println(
        lista1.mapNaMao { it * 2 }
    );

}
```

## Relembrando as regrinhas do Generics

> :book: Ao criar uma função com Generics, colocamos o tipo genérico antes do nome da função. Ao chamar a função, o Kotlin identifica automaticamente o tipo utilizado.

> :book: Ao criar uma classe com attributes Generics, colocamos o tipo genérico depois do nome da classe. Ao instanciar um objeto, precisamos informar o tipo que será utilizado.
