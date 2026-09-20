# Anonymous Functions

Da mesma forma que podemos criar uma Classe sem nome (**Anonymous Class**), também podemos criar uma **função sem nome (Anonymous Function)**.

Geralmente criamos uma Anonymous Function quando precisamos de uma função temporária, que será utilizada apenas naquele momento.

Um dos cenários mais comuns é **passar uma função como argumento para outra função**.

---

## Syntax

Vamos usar um exemplo onde uma funcao vai receber 2 parametros:

- uma funcao sem nome
- uma String

```kotlin

fun main(args: Array<String>) {
    
    executar(
        fun(){
            println("call back insano")
        },
        "funcao executada com sucesso"
    );
}


fun executar(funcao: () -> Unit, mensagemSucesso: String){
    funcao();
    println(mensagemSucesso);
}
```