# Expressões lambdas

Antes de aprendermos a syntax da expressão lambda no Kotlin, vamos relembrar alguns conceitos importantes.

<hr>

## Lambda

Lambda serve para conseguirmos utilizar methods de uma interface funcional de uma maneira mais simples, sem precisar criar uma classe para isso.

Não precisa escrever esse código novamente, apenas relembre como o fluxo de utilizar um method de uma interface funciona. [Clique  aqui](../6.classes_objetos/3.interfaces_classe_abstrata/0.interfaces.md#como-usamos-um-method-de-uma-interface)

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

