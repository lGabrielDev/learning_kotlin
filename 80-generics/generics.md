# Generics

Generics é uma forma de criar Classes e funções que podem trabalhar com diferentes datatypes.

---

## Trabalhando com funcoes genericas

### Exemplo 1

Essa funcao vai printar o parametro informado

```kotlin
class FuncoesInsanas() {

    //maneira tradicional
    fun printar(value: String): Unit {
        println(value);
    }

    fun printar(value: Int): Unit {
        println(value);
    }

    fun printar(value: Character): Unit {
        println(value);
    }

    //etc...

    //usando generics
    fun <T> printar(value: T): Unit {
        println(value);
    }

}
```

> :book: Perceba que, se quiséssemos trabalhar com diferentes tipos de dados da maneira tradicional, precisaríamos criar uma função para cada tipo. Olha o trabalho...
>
> Utilizando **Generics**, podemos criar a função apenas uma vez e utilizá-la com diferentes tipos de dados.

<br>

### Exemplo 2

Essa funcao vai somar dois numeros.


```kotlin
class Calculos() {

    // forma tradicional
    fun somar(n1: Int, n2: Int): Int {
        return n1 + n2;
    }

    fun somar(n1: Double, n2: Double): Double {
        return n1 + n2;
    }

    // etc...
    
    //usando generics
    fun <T: Number> somar(n1: T, n2: T): Double {
        return n1.toDouble() + n2.toDouble();
    }
}
```

> :book: Ao criar uma função com **Generics**, informamos o tipo genérico antes do nome da função.

---

## Criando uma Classe utilizando Generics

Quando usamos Generics em uma classe, significa que um ou mais atributos da classe terão um tipo genérico. O tipo será definido quando criarmos um objeto dessa classe.

```kotlin
class Person <T> (
    val name: String,
    val age: T
)
```

:book: Ao criar uma Class com Generics, informamos o tipo genérico depois do nome da Class.

```kotlin
fun main(args: Array<String>) {

    val p1 = Person <Int> ("goku", 33);
    val p2 = Person <String> ("naruto", "cinquenta e cinco");

}
```

---

## Relembrando as regrinhas do Generics

> :book: Ao criar uma função com Generics, colocamos o tipo genérico antes do nome da função. Ao chamar a função, o Kotlin identifica automaticamente o tipo utilizado.

> :book: Ao criar uma classe com Generics, colocamos o tipo genérico depois do nome da classe. Ao instanciar um objeto, precisamos informar o tipo que será utilizado.
