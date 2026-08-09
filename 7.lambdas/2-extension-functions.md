# Extension Functions (Funções de extensão)

## O que são?

Uma maneira de adicionar funções a uma Classe, sem alterar o código dessa Classe.

Geralmente usamos quando precisamos adicionar funções a uma classe que não podemos ou não queremos modificar. Por exemplo, a classe `String` do Kotlin não pode ser alterada, mas podemos adicionar novas funções a ela através das **Extension Functions**.

--- 

## Exemplo simples 1

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

fun String.primeiraLetra(): Char = this[0];
```

---

## Exemplo simples 2

:pencil2: Crie uma funcao para somar 2 numeros.

### Maneira tradicional

Passamos um parametro

```kotlin
fun main(args: Array<String>) {
    println( somarComAlgumNumero(1, 2) );
}

fun somarComAlgumNumero(n1: Int, n2: Int): Int = n1 + n2;
```

### Usando extension function

Como a funcao foi "criada" dentro de uma Classe, chamamos ela através de um objeto da Classe.

```kotlin
fun main(args: Array<String>) {
    println( 45.somarComAlgumNumero(1) );
}

fun Int.somarComAlgumNumero(n1: Int): Int = this + n1;
```

---

## Conflito de nomes entre Extension Function e função da classe

> :book: Se uma Extension Function tiver o mesmo nome de uma função que já existe na classe, a função da própria classe terá prioridade.

:pencil2: Crie uma funcao dentro de uma Class "Person"

### Maneira tradicional

Nós mesmos que criamos a class "Person", entao podemos criar o method ali mesmo.

```kotlin
class Person (
    val name: String,
    val age: Int
) {
    fun apresentarPessoa(): Unit {
        println(
            """
            Olá, sou o ${this.name} e tenho ${this.age} anos.
            """.trimIndent()
        );
    }
}


fun main(args: Array<String>) {
    val p1: Person = Person("goku", 33);
    p1.apresentarPessoa();
}
```

### Usando extension function

```kotlin
fun main(args: Array<String>) {
    val p1: Person = Person("goku", 33);
    p1.apresentarPessoa();
}

fun Person.apresentarPessoa(): Unit {
    println(
        """
                Olá 22222222, sou o ${this.name} e tenho ${this.age} anos.
            """.trimIndent()
    );
}
```