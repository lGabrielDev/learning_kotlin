# Expressões lambdas

## Relembrando como utilizar um method de uma interface
Antes de entender o que são expressões lambda, vamos relembrar como fazemos para utilizar um method de uma interface. [Clique  aqui](../6.classes_objetos/3.interfaces_classe_abstrata/0.interfaces.md#como-usamos-um-method-de-uma-interface)

<hr>

## Functional Interface

É uma interface com apenas **1 method abstrato**. Pode ter vários methods com corpo, mas abstratos deve ter somente 1.

<hr>

## 


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

