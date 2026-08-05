# Anonymous Functions

Da mesma forma que podemos criar uma Classe sem nome (Anonymous Class), também podemos criar uma **função sem nome** (Anonymous Function).

Geralmente criamos uma Anonymous Function quando precisamos de uma função temporária, que será utilizada apenas naquele momento. Um dos cenários mais comuns é **passar uma função como parâmetro para outra função**.
<hr>

## Syntax
Vamos usar um exemplo onde, existe uma funcao e um dos parametros dela é uma funcao anonima.

```kotlin

fun funcaoPrincipal(
    name: String,               //parametro comum
    funcaoCallback: () -> Unit  //parametro do tipo function
): Unit {
    funcaoCallback();
}
```


```kotlin
fun main(args: Array<String>) {

    // Maneira antiga
    funcaoPrincipal(
        "goku",
        fun () {
            println("salve 1")
            //...
        }
    )
    
    // Usando lambda
    funcaoPrincipal("goku"){
        println("salve 1")
        //...
    }
    
}
```

> :book: Se o último parâmetro de uma função for do tipo função, o argumento desse parametro pode ser informado fora dos parênteses `()` .