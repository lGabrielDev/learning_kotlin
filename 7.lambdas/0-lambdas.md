# Expressões lambdas

Antes de aprendermos a syntax da expressão lambda no Kotlin, vamos relembrar alguns conceitos importantes.

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

