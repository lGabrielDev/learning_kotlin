# Extension Functions (Funções de extensão)

## O que são?

Uma maneira de adicionar funções a uma Classe, sem alterar o código dessa Classe.

Geralmente usamos quando queremos adicionar uma função a uma Classe que não podemos ou não queremos modificar.

Por exemplo, não podemos alterar a Classe `String` do Kotlin, mas podemos criar novas funções para ela utilizando **Extension Functions**.

---

## Exemplo 1

:pencil2: Imagine que queremos criar uma função que retorne a primeira letra de uma `String`.

### Maneira tradicional

Criamos uma função e passamos a `String` como parâmetro:

```kotlin
fun getFirstLetter(texto: String): Char {
    return texto[0]
}

fun main(args: Array<String>) {
    println(getFirstLetter("texto insano"))
}
```

### Usando Extension Function

Podemos criar essa função como uma extensão da Classe `String`:

```kotlin
fun String.getFirstLetter(): Char {
    return this[0]
}
```

Agora podemos chamar a função diretamente através de qualquer objeto `String`:

```kotlin
fun main(args: Array<String>) {
    val texto: String = "texto insano";
    println(
        texto.getFirstLetter()
    )
}
```

> :book: O `this` representa o objeto que chamou a Extension Function. Nesse exemplo, `this` representa `"texto insano"`.

---

## Exemplo 2

:pencil2: Crie uma função para somar 2 números. (Não se preocupe com generics agora)

### Maneira tradicional

```kotlin
fun somar(n1: Int, n2: Int): Int = n1 + n2;

fun main(args: Array<String>) {
    println(somar(10, 5))
}
```

### Usando Extension Function

```kotlin
fun Int.somar(n1: Int): Int = this + n1;

fun main(args: Array<String>) {

    val numeroInsano = 44;
    println(numeroInsano.somar(10));

}
```

> :book: O `this` representa o objeto que chamou a função. Nesse caso, `this` representa `numeroInsano`, que possui o valor `44`.  



---

## Exemplo 3

:pencil2: Crie uma função toString() para a class Person, utilizando extension function

```kotlin
fun main(args: Array<String>) {
    val p1 = Person("sonic", 22);
    println(p1.toStringNaMao());
}

fun Person.toStringNaMao(): String = """
    Name: ${this.name}
    Age: ${this.age}
""".trimIndent()
```



> :warning: A prioridade é sempre da função da própria Classe. Se criarmos uma Extension Function com o mesmo nome de uma função que já existe na Classe, a função da Classe será chamada.