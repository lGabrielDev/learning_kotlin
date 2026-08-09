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

Para praticar, vamos criar 2 cenários:

- Passando a lista como parâmetro
- Usando Extension Function (igualzinho como o Kotlin faz)

### Passando a lista como parâmetro

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


### Usando Extension Function (igualzinho como o Kotlin faz)

```kotlin
fun main(args: Array<String>) {
    val listaInsana: MutableList<Int> = mutableListOf(1,3,77,99);
    listaInsana.forEach {println(it)  } //criado pelo Kotlin
    listaInsana.forEachNaMao{ println(it) }; //igualzinho kk
}


fun MutableList<Int>.forEachNaMao(
    funcaoCallback: (Int) -> Unit
): Unit {
    for(i in this) funcaoCallback(i);
}
```


---

## filter()

O filter percorre uma lista e utiliza uma Callback para decidir quais elementos devem permanecer. Se a Callback retornar true, o elemento é adicionado em uma nova lista. Se retornar false, ele é ignorado.

No final, o filter retorna a nova lista.

### Passando a lista como parâmetro

```kotlin
fun main(args: Array<String>) {
    val listaInsana: MutableList<Int> = mutableListOf(1,3,77,99);

    val novaLista = filterNaMao(listaInsana) { n1 -> n1 >= 78};
    println(novaLista);

}


fun filterNaMao(
    listaAntiga: MutableList<Int>,
    callBackfunction: (Int) -> Boolean
): MutableList<Int> {
    val novaLista: MutableList<Int> = mutableListOf();

    for(i in listaAntiga){
        if( callBackfunction(i) ) novaLista.add(i);
    }
    return novaLista;
}
```

### Usando Extension Function (igualzinho como o Kotlin faz)

```kotlin
fun main(args: Array<String>) {
    val listaInsana: MutableList<Int> = mutableListOf(1,3,77,99);

    val novaLista = listaInsana.filter { n1 -> n1 >= 78}; // criado pelo Kotlin
    println(novaLista);

    val novaLista2 = listaInsana.filterNaMao { n1 -> n1 >= 78}; //igualzin kk
    println(novaLista2);

}


fun MutableList<Int>.filterNaMao(
    callBackfunction: (Int) -> Boolean
): MutableList<Int> {
    val novaLista: MutableList<Int> = mutableListOf();

    for(i in this){
        if( callBackfunction(i) ) novaLista.add(i);
    }
    return novaLista;
}
```

---

## map()

O map percorre uma lista e transforma cada elemento em um novo valor. No final, retorna uma nova lista com os elementos transformados.

### Passando a lista como parâmetro

```kotlin
fun main(args: Array<String>) {
    val listaInsana: MutableList<Person> = mutableListOf(
        Person("goku", 33),
        Person("naruto", 80),
        Person("sasuke", 18)
    );
    val nomes: MutableList<String> = mapNaMao(listaInsana ) { it.name };
    println(nomes);
}

fun mapNaMao(
    listaAntiga: MutableList<Person>,
    funcaoCallback: (Person) -> String
): MutableList<String> {
    val novaLista: MutableList<String> = mutableListOf()

    for(person in listaAntiga){
        val nomeDaPessoa = funcaoCallback(person);
        novaLista.add(nomeDaPessoa);
    }
    return novaLista;
}
```

### Usando Extension Function (igualzinho como o Kotlin faz)

```kotlin
fun main(args: Array<String>) {
    val listaInsana: MutableList<Person> = mutableListOf(
        Person("goku", 33),
        Person("naruto", 80),
        Person("sasuke", 18)
    );
    val nomes: Iterable<String> = listaInsana.map{ it.name };
    val nomes2: MutableList<String> = listaInsana.mapNaMao{ it.name }; // igualzin kk

    println(nomes);
}

fun MutableList<Person>.mapNaMao(
    funcaoCallback: (Person) -> String
): MutableList<String> {
    val novaLista: MutableList<String> = mutableListOf()

    for(person in this){
        val nomeDaPessoa = funcaoCallback(person);
        novaLista.add(nomeDaPessoa);
    }
    return novaLista;
}
```

---

## Usando Extension Function com Generics (EXATAMENTE igualzinho como o Kotlin faz)

Vamos usar apenas o método `map()` como exemplo.

Recapitulando, o `map()`, assim como outras funções (filter(), forEach(), etc.), percorre uma estrutura de dados e realiza alguma operação em cada elemento.

No caso do `map()`, ele transforma cada elemento em um novo valor e retorna uma nova lista com esses valores.

Precisamos ter em mente duas coisas:

- O `map()` pode ser usado com listas de qualquer tipo, como `List<Int>`, `List<String>`, `List<Person>`, etc.
- O `map()` pode retornar uma lista de um tipo diferente do tipo original.

Como o `map()` pode receber uma lista de um tipo e retornar uma nova lista com outro tipo, precisamos usar Generics para deixar a função flexível.

```kotlin
fun main(args: Array<String>) {
    val listaInsana: MutableList<Person> = mutableListOf(
        Person("goku", 33),
        Person("naruto", 80),
        Person("sasuke", 18)
    );
    val novaLista1: Iterable<String> = listaInsana.mapNaMao { it.name }; //generics eh bom demais
    val novaLista2: Iterable<Int> = listaInsana.mapNaMao { it.age }; //generics eh bom demais
    println(novaLista1);
    println(novaLista2);
}

fun <T, R> Iterable<T>.mapNaMao(
    funcaoCallback: (T) -> R
): Iterable<R> {
    val novaLista: MutableList<R> = mutableListOf()

    for(person in this) novaLista.add( funcaoCallback(person) );

    return novaLista;
}
```

## Relembrando as regrinhas do Generics

> :book: Ao criar uma função com Generics, colocamos o tipo genérico antes do nome da função. Ao chamar a função, o Kotlin identifica automaticamente o tipo utilizado.

> :book: Ao criar uma classe com Generics, colocamos o tipo genérico depois do nome da classe. Ao instanciar um objeto, precisamos informar o tipo que será utilizado.
