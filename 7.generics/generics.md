# Generics

Uma maneira de criar funções ou classes que podem trabalhar com diferentes tipos de dados.

---

## Criando uma funcao utilizando Generics

Ao criar uma função com Generics, **colocamos o tipo genérico antes do nome da função**. Ao chamar a função, o Kotlin identifica automaticamente o tipo utilizado

```kotlin
fun main(args: Array<String>) {
    
    printarValorInformado(1);
    printarValorInformado(1.33);
    printarValorInformado(12f);
    printarValorInformado("salve");
    printarValorInformado(true);
    printarValorInformado('C');
}

fun <T> printarValorInformado(valor: T): Unit {
    println(valor);
}
```

Sem utilizar Generics, você teria que criar uma função específica para cada tipo de dado. Olha o trabalhão kkk

---

## Criando uma Classe utilizando Generics

Quando usamos Generics em uma classe, significa que um ou mais atributos da classe terão um tipo genérico. O tipo será definido quando criarmos um objeto dessa classe.

```kotlin
class Person <T> (
    val name: String = "",
    val age: Int = 1,
    val salario: T
)
```

```kotlin
fun main(args: Array<String>) {
    
    val p1: Person<Int> = Person(
        "goku",
        33,
        3
    );

    val p2: Person<String> = Person(
        "goku",
        33,
        "salario tal"
    );
}
```

---

## Relembrando as regrinhas do Generics

> :book: Ao criar uma função com Generics, colocamos o tipo genérico antes do nome da função. Ao chamar a função, o Kotlin identifica automaticamente o tipo utilizado.

> :book: Ao criar uma classe com Generics, colocamos o tipo genérico depois do nome da classe. Ao instanciar um objeto, precisamos informar o tipo que será utilizado.
