# Enums

É uma forma de representar um conjunto fixo de valores possíveis.

A ideia é restringir os valores possíveis.

## Syntax:

```kotlin
enum class Genero(){
    //CONSTANTS
    MALE,
    FEMALE
}

fun main(args: Array<String>) {
    val generoEscolhido4: Genero = Genero.MALE;
    val generoEscolhido5: Genero = Genero.FEMALE;
}
```

<hr>
<br>

## Criando um Enum com attributes
O enum é como uma classe onde os objetos já são criados dentro dela mesma — você preenche o constructor direto na declaração de cada constante.

```kotlin
enum class TarefaOneClick(
    val descricao: String,
    val ativo: Boolean
){
    //CONSTANTES
    PIX("Transferência instantânea", true),
    DDA(descricao = "Débito Direto Autorizado", true),
    LIS("Limite de crédito", false),
    STI("Seguro transação", false),
    OPEN_FINANCE("Compartilhamento de dados financeiros", true)
}

fun main(args: Array<String>) {
    val tarefa1: TarefaOneClick = TarefaOneClick.PIX;
    val tarefa2: TarefaOneClick = TarefaOneClick.OPEN_FINANCE;
    println(tarefa2.ativo);
    println(tarefa2.descricao);
}
```

<hr>
<br>


## Criando funcoes na enum


Assim como qualquer classe, o enum também pode ter attributes e methods.

- **Methods normais** → chamados pelas constantes (instâncias)
- **Methods static** → declarados dentro de um `companion object`, chamados pela própria classe

<br>

Relacionando com uma classe comum:
- Methods normais → o objeto (instâncias) chama
- Methods static → a classe chama

<br>

### Criando uma funcao statica

Chamamos pela própria classe
```kotlin
fun main(args: Array<String>) {
    println(
        TarefaOneClick.isTarefaValid("open_finance") //chamamos direto pela Classe
    ) ;
}

enum class TarefaOneClick(
    val descricao: String,
    val ativo: Boolean,
    val nome: String
){
    //CONSTANTES
    PIX("Transferência instantânea", true, "pix"),
    DDA(descricao = "Débito Direto Autorizado", true, "dda"),
    LIS("Limite de crédito", false, "lis"),
    STI("Seguro transação", false, "sti"),
    OPEN_FINANCE("Compartilhamento de dados financeiros", true, "open_finance");


    companion object{
        //attributos staticos

        //methods staticos
        fun isTarefaValid(tarefa: String): Boolean = TarefaOneClick.values().any { it -> tarefa == it.nome }
    }
}
```

<br>
<hr>

### Criando uma funcao "normal"
Chamamos pelas constantes (instancias)

```kotlin
fun main(args: Array<String>) {
    println(
        TarefaOneClick.OPEN_FINANCE.isTarefaValid("open_fsinance") //chamamos por uma das constantes
    ) ;
}

enum class TarefaOneClick(
    val descricao: String,
    val ativo: Boolean,
    val nome: String
){
    //CONSTANTES
    PIX("Transferência instantânea", true, "pix"),
    DDA(descricao = "Débito Direto Autorizado", true, "dda"),
    LIS("Limite de crédito", false, "lis"),
    STI("Seguro transação", false, "sti"),
    OPEN_FINANCE("Compartilhamento de dados financeiros", true, "open_finance");
    
    //methods
    fun isTarefaValid(tarefa: String): Boolean = TarefaOneClick.values().any { it -> tarefa == it.nome }
}
```
