# Expressões Lambda

Uma **Expressão Lambda** é uma forma mais simples de escrever uma **Anonymous Function (função anônima)**.

No Kotlin, é muito comum utilizarmos Lambdas quando precisamos passar uma função como argumento para outra função (**Callback Function**).

> :book: No dia a dia do Kotlin, é muito mais comum encontrar Lambdas do que Anonymous Functions escritas utilizando `fun()`.

---

## Syntax

Vamos utilizar uma função que recebe uma Callback:

```kotlin
fun executar(
    funcaoCallback: () -> Unit
) {
    funcaoCallback()
}
```

Utilizando uma Anonymous Function:

```kotlin
executar(
    fun() {
        println("salve")
    }
)
```

Utilizando uma Lambda:

```kotlin
executar(
    {
        println("salve")
    }
)
```

Ou, como o parâmetro do tipo função é o último parâmetro:

```kotlin
executar {
    println("salve")
}
```

> :book: A Lambda permite escrever uma função anônima de forma muito mais simples, utilizando `{ }`.

---

## Lambda recebendo parâmetro

```kotlin
fun executar(
    funcaoCallback: (String) -> Unit
) {
    funcaoCallback("goku")
}
```

Podemos acessar o parâmetro dentro da Lambda:

```kotlin
executar { name ->
    println(name)
}
```

---

## Utilizando `it`

Quando a Lambda recebe apenas **1 parâmetro**, podemos omitir o nome desse parâmetro.

Nesse caso, o Kotlin disponibiliza automaticamente o `it`:

```kotlin
executar {
    println(it)
}
```

Ou seja, esses dois exemplos fazem a mesma coisa:

```kotlin
executar { name ->
    println(name)
}

executar {
    println(it)
}
```

> :book: Quando a Lambda possui apenas **1 parâmetro**, podemos utilizar `it` para representar esse parâmetro.

--- 

## Syntax em diferentes cenários

| Cenário | Tipo da função | Lambda |
|---|---|---|
| Sem parâmetro e sem retorno | `() -> Unit` | `{ println("salve") }` |
| 1 parâmetro e sem retorno | `(String) -> Unit` | `{ name -> println(name) }` |
| 1 parâmetro usando `it` | `(String) -> Unit` | `{ println(it) }` |
| 2 parâmetros e sem retorno | `(Int, Int) -> Unit` | `{ n1, n2 -> println(n1 + n2) }` |
| 1 parâmetro e com retorno | `(String) -> String` | `{ name -> name.uppercase() }` |
| 2 parâmetros e com retorno | `(Int, Int) -> Int` | `{ n1, n2 -> n1 + n2 }` |


:book: Se uma funcao tem um parametro do 'tipo funcao', sei que vou precisar passar como argumento uma funcao anonima `{}`.

- Posso passar essa funcao anonima da maneira tradicional `fun(){}`
- Posso passar essa funcao anonima utilizando lambda.