# Expressões lambdas

## Relembrando como utilizar um method de uma interface
Antes de entender o que são expressões lambda, vamos relembrar como fazemos para utilizar um method de uma interface.

[Clique  aqui](../6.classes_objetos/3.interfaces_classe_abstrata/0.interfaces.md#como-usamos-um-method-de-uma-interface)

<hr>

## Functional Interface

É uma interface com apenas **1 method abstrato**. Pode ter vários methods com corpo, mas abstratos deve ter somente 1.



A syntax é

```kotlin
fun interface MethodsInsanos{
    //apenas 1 method abstrato
    fun boasVindas(funcionario: String): Unit;
    //outros methods com corpo....
}
```

> :book: Para indicar que é uma interface funcional, usamos a palavrinha reservada `fun`


<hr>

### Syntax

```kotlin

```

:book: Percebe que eh como se tivéssemos criando uma interface funcional. Na esquerda setamos a declaração, com o datatype dos parametros e o datatype do retorno.

Na direita temos a implementacao / corpo desse method.

