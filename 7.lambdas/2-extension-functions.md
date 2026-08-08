# Extension Functions (Funções de extensão)

## O que são?

Uma maneira de adicionar funções a uma Classe, sem alterar o código dessa Classe.

Geralmente usamos quando precisamos adicionar funções a uma classe que não podemos ou não queremos modificar. Por exemplo, a classe `String` do Kotlin não pode ser alterada, mas podemos adicionar novas funções a ela através das **Extension Functions**.

--- 

## Exemplo simples

:pencil2: Imagine uma função que retorne a primeira letra de uma String

### Maneira tradicional

Passamos um parametro

```kotlin
fun main(args: Array<String>) {
    println( primeiraLetra("texto insano") );
}

fun primeiraLetra(texto: String): Char = texto[0];
```

### Usando extension function

Como estamos "criando" uma função dentro da Classe `String`, precisamos chamar essa função através de um objeto dessa Classe.

```kotlin
fun main(args: Array<String>) {
    println( "texto insano".primeiraLetraExtensionFunction() );
}

fun String.primeir
```



--- 