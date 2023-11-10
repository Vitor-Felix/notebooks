# Cp 1 - Kotlin: o que é e por quê

De que se trata o Kotlin?
* É uma nova linguagem de programação voltada para a plataforma Java.
* Linguagem concisa, segura, pragmática, com enfoque na interoperabilidade com Java.
* Funciona com as bibliotecas/frameworks Java e executa apresentando o mesmo nível de desempenho que Java.

#### Uma amostra de Kotlin:
```kotlin
data class Person( // declaração de uma classe de dados
  val name: String,
  val age: Int? = null // tipo nullable e valor default
)

fun main(args: Array<String>){ // função de nível superior
    val people = listOf(
        Person("Alice"),
        Person("Bob", age=29) // argumento nomeado
    )
    val oldest = people.maxBy{ it.age?: 0} // lambda expression e Elvis operator
    println("The oldest is: $oldest") // template de string
}
//The oldest is: Person(name=Bob, age=29)
```
#### Principais características de Kotlin

##### Plataformas visadas: lados do servidor, Android, qualquer lugar em que Java seja executado

Um dos focos do Kotlin é a de prover uma alternativa mais concisa, produtiva e segura a Java.

##### Tipagem estática

Kotlin é uma linguagem **estaticamente tipada**, ou seja, o tipo de toda expressão no programa é conhecido e avaliado em tempo de compilação. Linguagens onde os tipos são inferidos em tempo de execução são denominadas *dinamicamente tipadas*.

Por outro lado, *Kotlin não exige que você especifique o tipo de toda variável explicitamente* em seu código-fonte. Em muitos casos, o tipo de uma variável pode ser determinado automaticamente a partir do contexto permitindo omitir a sua declaração. A capacidade do compilador de determinar tipos com base no contexto é chamada de **inferência de tipos**.

Outras vantagens da tipagem estática:
* *Desempenho* nas chamadas de método, pois não há a necessidade de descobrir os tipos em tempo de execução.
* *Confiabilidade*, pois disponibilizar a verificação em tempo de compilação, reduz as chances de falhas em tempo de execução.
* *Manutenibilidade*, pois é mais fácil de lidar com códigos desconhecidos, quando já temos os tipos de objetos explícitos.
* *Suporte de ferramentas* como IDEs que podem oferecer recursos como realizar refatorações, preenchimentos automáticos e etc, com mais precisão e confiabilidade.

Em Koltin há muitos tipos conhecidos no Java que funcionam de maneira semelhante, porém também existem novidades com os tipos **nullable**, que permitem a detecção de possíveis *NullPointerExceptions* em tempo de compilação e o suporte para **tipos de função**. Ambas serão exploradas mais a fundo ao decorrer do livro.

##### Programação funcional e orientada a objetos

Principais conceitos da programação funcional:

* *Funções de primeira classe* - Trabalhamos com funções como valores. Podemos armazená-las em variáveis, passá-las como parâmetros ou devolvê-las a partir de outras funções. 
* *Imutabilidade* - Trabalhamos com objetos imutáveis, que garantem que seu estado não pode ser alterado após a sua criação. 
* *Funções puras (sem efeitos colaterais)* - Usamos funções puras, que devolvem o mesmo resultado, dadas as mesmas entradas, e não modificam o estado de outros objetos nem interagem com o mundo externo.

###### Vantagens do estilo funcional: **Concisão**

Um código funcional pode ser mais elegante e sucinto que um código imperativo, por trabalhar com funções como valores, proporcionando uma maior capacidade de abstração, tornando a duplicação de código mais "evitável".
