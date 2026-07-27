# Expressões lambdas

Antes de aprendermos a syntax da expressão lambda no Kotlin, vamos relembrar alguns conceitos importantes.

<hr>
<br>

## Interfaces
Interfaces são contratos que as classes devem seguir. Possuem methods sem corpo (obrigatórios de implementar) e methods com corpo (opcionais de sobrescrever).

Um exemplo prático: seu chefe pede para você criar uma função / method. Ele sabe exatamente o que a função deve receber e retornar, mas não sabe como você vai implementar. Ele cria a interface com a declaração do method — o contrato. Você cria uma classe, implementa a interface e define o corpo do method.

<br>

Na prática faríamos:


1. Criamos a interface e definimos o comportamento das funcoes abstratas.
    ```kotlin
    fun interface MethodsInsanos { //fun significa que eh uma 'interface funcional'. Uma interface com apenas 1 method abstrato / method sem corpo
        fun printComum(name: String): Unit;
    }
    ```

<br>

2. Criamos uma Classe para implementar a interface e sobreescrever o method. Para aí sim definir o corpo desse method.
    ```kotlin
    class Person(val name: String, val age: Int): MethodsInsanos {
        override fun printComum(name: String) {
            println("deu certo!");
        }
    }
    ```
<br>

3. Instanciamos a Classe e utilizamos o method.
    ```kotlin
    fun main(args: Array<String>) {
        val p1: Person = Person("camila", 2);
        p1.printComum("daora"); //chamamos o method da interface
    }
    ```
   
<hr>
<br>

### Usando lambda ficaria assim:

```kotlin
//utilizando lambda
val lambdaInsano = MethodsInsanos { nome1, nome2 -> println("Salve $nome1 e $nome2")}
lambdaInsano.printComum("goku1", "goku2");
```

:book: Nao precisa se afobar. Isso eh soh para entendimento. No dia a dia vamos usar as expressoes lambda de uma outra abordagem.

<hr>
<br>


## Lambda

Lambda serve para conseguirmos utilizar methods de uma interface funcional de uma maneira mais rápida e simples, sem precisar criar uma classe para isso, como vimos acima.


### Syntax

```kotlin
val methodAbstratoInsano: (String) -> Unit = {a -> println(a)};



val methodAbstratoInsano2: (String, String, Int) -> Unit = {a1, a2, a3 ->
    println(a1)
    println(a2)
    println(a3)
};
```

:book: Percebe que eh como se tivéssemos criando uma interface funcional. Na esquerda setamos a declaração, com o datatype dos parametros e o datatype do retorno.

Na direita temos a implementacao / corpo desse method.

