# Recriando funcoes do kotlin
Quando estamos trabalhando com estruturas de dados (listas, arrays, etc.), podemos utilizar diversas funções já prontas do Kotlin, como:

- `[forEach]`
- `filter`
- `map`
- `sortedBy`
- etc.

Agora que já entendemos **Anonymous Functions**, **Callback Functions**, **Expressões Lambda** e **Extension Functions** , vamos criar na mão essas funções para entender como elas funcionam por baixo dos panos.

<hr>

## ForEach

```kotlin

fun main(args: Array<String>) {
    forEach( listOf(1,3,4,22) ) { println(it) }
}

fun forEach(
    lista: List<Int>,
    funcaoCallback: (Int) -> Unit
){
    for(i in lista){
        funcaoCallback(i);
    }
}
```

> :book: O `forEach` apenas percorre todos os elementos da lista. O que será feito com cada elemento é definido pela Callback (Lambda) passada como argumento.

<br>

### Deixando IGUAL, usando a `extension function`

```kotlin
fun main(args: Array<String>) {
    listOf(1,3,4,22).forEachNaMao{ println(it) }; // criado por mim
    listOf(1,3,4,22).forEach{ println(it) };      // Criado pelo kotlin... mesma coisa kk
}


fun List<Int>.forEachNaMao (
    funcaoCallback: (Int) -> Unit
){
    for(i in this){
        funcaoCallback(i);
    }
}
```

<hr>

## filter 

```kotlin
fun main(args: Array<String>) {

    val listaNovaInsana = filter(
        mutableListOf(1,33,44,80,3000,5000,25000),
    ) {it > 2000}

}

fun filter(
    listaAntiga: List<Int>,
    funcaoCallback: (Int) -> Boolean
): MutableList<Int> {
    val listaNova: MutableList<Int> = mutableListOf();

    for(i in listaAntiga){
        if(funcaoCallback(i)) listaNova.add(i)
    }

    return listaNova;
}
```

> :book: O `filter` percorre uma lista e utiliza uma Callback para decidir quais elementos devem permanecer.
>
> Caso a Callback retorne `true`, o elemento é adicionado na nova lista. Caso retorne `false`, ele é ignorado.

<hr>

## map