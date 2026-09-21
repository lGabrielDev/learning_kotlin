# Anonymous Functions

Da mesma forma que podemos criar uma Classe sem nome (**Anonymous Class**), também podemos criar uma **função sem nome (Anonymous Function)**.

Estamos acostumados a criar funções com parâmetros de tipos como `String`, `Double`, `Pessoa`, `Carro`, `Int`, etc.

O legal é que, no Kotlin, uma função também pode ter **parâmetros do tipo função**.

---

## Syntax

Vamos usar um exemplo onde uma funcao vai receber 2 parametros:

- uma funcao sem nome
- uma String

```kotlin
fun executar(
    funcao: () -> Unit, //parametro do tipo funcao
    mensagemSucesso: String //parametro normal
){
    funcao();
    println(mensagemSucesso);
}
```

Quando chamamos uma função que possui um parâmetro do tipo função, preencher esse argumento com uma **Anonymous Function / funcao sem nome**.

```kotlin
fun main(args: Array<String>) {
    
    executar(
        fun(){ //funcao anonima / funcao sem nome
            println("call back insano")
        },
        
        "funcao executada com sucesso"
    );
}
```

Deixando mais simples ainda

```kotlin
fun main(args: Array<String>) {
    
    executar(
        { //funcao anonima / funcao sem nome
            println("call back insano")
        },
        
        "funcao executada com sucesso"
    );
}
```
