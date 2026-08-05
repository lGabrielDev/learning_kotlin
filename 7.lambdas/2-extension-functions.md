# Extension Functions (Funções de extensão)

Escrever o que é.....

## Exemplo simples

```kotlin
fun transformarUpper1(name: String): String {
    return name.uppercase();
}

fun String.transformarUpper2(): String {
    return this.uppercase();
}
```

```kotlin
fun main(args: Array<String>) {
    val teste = "vegeta";
    
    println(transformarUpper1("goku"))
    
    println("naruto".transformarUpper2());
    println(teste.transformarUpper2());
}
```


> :book: Voce não está criando uma nova funcao para dentro da class String. Voce só está criando uma funcao e passando um parametro de uma forma diferente.
> 
> É como se tivesse criando um parametro 0, antes dos outros parametros tradicionais.

<hr>

## Entendendo melhor com vários parametros

```kotlin
fun String.funcaoTal(
    numero: Int,
    ativo: Boolean
)

como se fosse:

fun funcaoTal(
    texto: String, // receiver (como se fosse o primeiro parâmetro)
    numero: Int,
    ativo: Boolean
)
```