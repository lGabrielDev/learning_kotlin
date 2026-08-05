# Expressões lambdas

Uma **Expressão Lambda** é uma forma mais simples de escrever uma **Anonymous Function (função anônima)**.

No Kotlin, normalmente utilizamos Lambdas quando precisamos passar uma função como argumento para outra função (Callback Function).

> :book: No dia a dia do Kotlin, é muito mais comum encontrar Lambdas do que Anonymous Functions escritas com a sintaxe tradicional (`fun`).

<hr>


## Syntax

Foque em como funciona os parametros de uma expressao lambda (funcao anonima).

Para deixar mais facil, vamos criar uma variavel e armazenar uma funcao. Logo, eh uma variable do tipo funcao.


```kotlin
fun main(args: Array<String>) {

    //funcao anonima (lambda) sem parametros
    val funcaoAnonima1: () -> Unit = { println("salve") }

    //funcao anonima (lambda) com apenas 1 parametro
    val funcaoAnonima2: (String) -> String = {
        name -> name.uppercase(); //no lambda não precisamos usar a keyword 'return'. O último valor da Lambda é retornado automaticamente
    }

    //funcao anonima (lambda) com apenas 1 parametro - it
    val funcaoAnonima3: (String) -> String = {it.uppercase()};

    //lambda com varios parametros
    val funcaoAnonima4: (Int, Int) -> Int = {n1, n2 -> n1 + n2}
    
}
```

> Quando a expressão Lambda recebe apenas **1 parâmetro**, podemos omitir o nome desse parâmetro. Nesse caso, o Kotlin cria automaticamente uma variável chamada `it`.
