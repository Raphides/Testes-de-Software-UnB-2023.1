# Parte 1

## A Psicologia dos Testes

Já sabemos que não é possível testar todos os resultados possíveis de um processo. É necessário saber o que e quando testar, habilidade essa que requer uma certa "visão" por parte do programador.

Essa noção impacta, por exemplo, na definição de testes, já que sempre será mais fácil achar erros se você de fato estiver com a intenção de encontrá-los. Uma pessoa que faz testes "para conferir se o software funciona" provavelmente focará em erros mais simples, já que eles de fato buscam um software que funcione.

Em outras palavras, o pensamento de alguém que vai testar seu programa deve ser de fato destrutivo. Chega a ser um tanto masoquista quando é você ou sua equipe a responsável pelos testes. Não achar erros num software é uma derrota, já que nenhum software é perfeito. E não se sinta mal, isso não é diferente do que um médico faz ao tentar achar doenças e problemas num paciente.


## Princípios de teste

- Tenha bem definida a saída desejada da sua funcionalidade. Não há como achar erros sem qualquer expectativa.
- Os mais envolvidos com o produto, principalmente os desenvolvedores, devem evitar testar seu próprio software. Isso porque os envolvidos costumam se apegar pelo produto. Portanto é mais provável que eles não consigam apresentar o caráter destrutivo necessário aos testes. Sem contar que os erros podem vir da falta de conhecimento dos envolvidos, o que dificultará o teste por parte deles.
- Escreva casos com inputs válidos e invalidos. É importante entender como seu programa lida com situações que devem ser realizadas por ele, já que se não tiver mecanismos para lidar com isso, pode acabar afetando até os casos com inputs válidos.
- Não faça testes que enchem linguiça, isso não aumentará do grau de qualidade do seu software.
- Não planeje testes sem esperar encontrar erros. Isso vai de contramão ao psicológico destrutivo necessário aos testes.
- Princípio da fumaça: se uma funcionalidade apresenta muitos erros, há grandes probabilidades de terem mais. Foque nessas funcionalidades.
- Testar é uma prática extremamente criativa e intelectual. Não é fácil achar testes que cubram outros ou pensar em casos extremos e únicos. Os métodos daqui só ajudam, mas boa parte depende do quanto você consegue abstrair e imaginar.

# Parte 2 - Categorias de Teste

Testes são atividades criativas e por isso podem ocupar muito tempo ao depender da inspiração do responsável no dia. O objetivo é que testes sejam mais sistemáticos (padronizados e automáticos) sem que percam sua eficácia e criatividade envolvida. Portanto as técnicas e classficações aqui comentadas buscam mostrar os padrões e comportamentos que os responsáveis por testes normalmente seguem.

## Por acesso a informação:
Os dois tipos de teste a seguir de diferenciam pelo conhecimento que o responsável pelo teste tem sobre a funcionalidade alvo. Caso isso pareça confuso de se entender agora, pense em projetos Open Source e privados. Enquanto em projetos de Código Aberto temos acesso a todo o código de ponta a ponta, em códigos pessoais e privados, podemos acabar caindo em casos em que de fato não entendemos a lógica por trás do código. Com a diferença de acesso a informação, os testes elaborados para cada uma das situações serão orientados de forma distinta.


### Teste de Caixa Preta

Normalmente chamado de *data driven* (orientdo pelos dados), aborda a testagem de funcionalidades através de suas entradas e saídas. Ou seja, o responsável não sabe (ou só não usa) como funcion as mecânicas internas do sistema e deve testar só pela descrição e cabeçalho da função.

Como não dá para testar todas as situações e garantir que o programa funcione sempre, devemos usar casos de testes que possuem uma tendência de gerar erros (tipo bordas) e casos de testes que englobem vários outros (ou seja, que testem uma possível mecânica que provavelmente será a mesma utilizada para outros casos.)

Exemplo: função de somar

```c
int sum(int* a);
/** Sum two numbers
*/
```

É impossível testar todas as somas de vetores, já que a quantidade de elementos e números inteiros tende a ser infinita. Portanto devemos testar:
- Casos que englobem outros: Se a soma de \[2, 3\] der certo, então a soma de outros dois números positivos num vetor também deve dar.
- Casos que podem dar problema (tendem a ter mecânicas diferentes): \[\] (vetor vazio).

### Teste de Caixa Branca

Normalmente conhecido como *logic driven* (orientado pela lógica), aborda testes que consideram a análise das lógicas e mecânicas internas por trás do programa. O desafio aqui é evitar não só os testes exaustivo de input e output, como também testes exaustivos nos fluxos lógicos e tomadas de decisões do seu programa. Isso porque, um programa pode ir para trilhares de rumos diferentes, mesmo sendo extremamente simples.

Exemplo:

```c
for(...){
    if(...)
    {
        ...
    }
    else ...
    {
        ...
    }
}
```

Considerando que nenhuma das condições possui um *break;* ou um *return*, caso o for tivesse um tamanho fixo de 20 loops, as permutações possíveis seriam cerca de 2^20 = 1048576. E isso porque é um programa simples.

## Por técnica:

### Testes baseados em Exemplos

Testes normalmente unitários que usam de alguns exemplos de input escolhidos a dedo pelo programador, procurando algum divergência do esperado ao chechar seus devidos outputs. Sua reprodução costuma ser extremamente simples, mas pensar em exemplos realmente relevantes é difícil

### Testes baseados em Propriedades

Testes que procuram erros em uma propriedade em específico da função. Costumam contar com a reprodução de vários testes com exemplos aleatórios feitos com a máquina, todos numa mesma situação que aborde a propriedade a ser testada.
Ficou confuso? Um bom exemplo é uma função que retorna o menor valor de um vetor de no máximo 20 inteiros!

```c
int *vetor = (int *) calloc(20, sizeof(int));

int pegar_menor(int* vetor);
```

A propriedade que queremos testar é a de que a função retorna o menor valor em 2 valores ou mais. Isso porque existe uma chance de que a função tenha mecanismos diferentes para os casos de 1 e 0 elementos, já que não há de fato o que calcular nessas duas situações. Para testar a propriedade de 2 ou mais valores, podemos colocar o valor -1 por exemplo em qualquer posição e pedir para que o programa escolha aleatoriamente no máximo 19 valores, estes todos números maiores que -1. Esses exemplos aleatórios repetidas várias vezes fazem um teste de propriedade. Muitas ferramentas de teste possuem funcionalidades específicas que geram testes de propriedade de forma simples.

## Por Estratégia

### Testes Estruturais. 

É a ideia de que devemos ter a maior parte das linhas do nosso código testadas ao menos uma vez. Essa ideia é bastante praticada hoje em dia, de modo que códigos com uma cobertura maior que 90% normalmente dão uma impressão de cuidado e polimento ao projeto, gerando confiança de investidores.

### Testes de Domínio

É uma prática que instrui o programador a dividir seus requerimentos em vários casos isolados, para assim testar cada um por vez.

Aquele problema do vetor na sessão dos [Testes de Propriedade](#testes-baseados-em-propriedades) por exemploo foi separado em vários casos:
1. Vetor vazio, deve retornar null.
2. Vetor com 1 elemento, deve retornar o elemento.
3. Vetor com 2 ou mais elementos, deve retornar o menor.

E ainda tem muitos outros casos:

4. Vetor com números menores repetidos deve retornar só uma instância do número.
5. Vetor somente com um único número, repetido durante todo o vetor, deve gerar um null.

### Testes de Fronteiras

É uma prática de teste que instrui o programador a testar casos extremos do seu código, perto do que a ação não é feita para lidar.

Um exemplo é novamente o teste do menor número na sessão [Testes por Propriedades](#testes-baseados-em-propriedades)

### Testes Inteligentes
São testes que se adaptam às mudanças de código no projeto. Geralmente conta com geradores de testes de casos simples e evita que o programador tenha que sempre refazer e adicionar testes ao adicionar uma nova funcionalidade.

## Por escopo:

### Teste Unitário

É a testagem de uma funcionalidade isoladamente, ignorando todas as outras. Como é só uma unidade do seu código, costuma ser um teste curto e de rápida execução, mas que representa pouco a realidade ao não testar as interações entre as diferentes funcionalidades. Normalmente testes unitários chamam a função alvo e adicionam inputs para então compará-los com os respectivos outputs esperados.

É importante ressaltar que a "unidade" é um conceito mais abstrato e pessoal, dando a possibilidade do programador considerar uma unidade como uma função/método/classe ou várias.

### Teste de Integração

Quando uma unidade é dependente de outra, um teste unitário muitas vezes não consegue cobrir direito a relação e integração entre elas, mas os testes de integração conseguem!

Testes de integração normalmente são usados quando uma unidade interna depende de outra externa e ambas devem ser testadas. Bons exemplos são conexões a bases de dados ou testes de operações web. Na primeira situação, não dá para testar uma função que conecta a base dados sem testar se as operações SQL à base funcionam corretamente. Logo o programador checará os resultados das operações à base separadamente do resto da função, depois a função sem o SQL e por fim a função com o SQL.

Testes de Integração costumam ser mais complexos e demorados, por isso algumas pessoas preferem realizar testes unitários separados com a integração em mente no input e output. 


### Teste Sistemático

Sendo definitivamente o teste mais complexo e lento de ser executado, o teste sistemático também é o mais confiável entre as opçpões. Esse teste tem como alvo o sistema como um todo, verificando se todas as integrações e funcionam de acordo.

Testes Sistemáticos testam a aplicação em si, dando uma maior confiabilidade ao produto final e permitindo críticas e abordagens extremamente mais realistas. Por outro lado, também são testes pouco maleáveis com mais chances de não testar direito a aplicação por pequenas variações em fatores externos. Um bom exemplo é testar uma aplicação web num dia em que a conexão está lenta. O teste pode gerar resultados errôneos por um erro que não vem da aplicação e que não é possível do desenvolvedor fazer nada a respeito.

## Por tamanho:

Separar testes por tamanho é uma prática popularizada pelos engenheiros da Google, normalmente adotada como alternativa à classificação por escopo. São 3 tipos de teste classificados por tamanho:

### Testes Pequenos

Testes executados numa única thread e chamada de execução.

### Testes Médios

Testes que utilizam diversas threads e chamadas de execução.

### Testes Grandes

Testes que podem usar vários computadores simultaneamente em sua execução.

# Parte 3 - Conceitos

- Requisitos de Software: quais ações, funcionalidades e especificações o seu software deve ter. É a fase inicial na produção de um software profissional e normalmente conta com vários artefatos de software que descrevem e organizam as requisições de forma mais simples. Os requisitos de software são o que gera o output esperado para muitas funções e não é incomum que revisões e adições sejam feitas nos requisitos, principalmente durante os processos de teste.

- Testes Automatizados: testes que podem ser realizados sem quaisquer dificuldades ou configuração quando você bem entender. Exemplo: quando um membro da equipe propõe uma adição de código num projeto. Normalmente testes automatizados são implementados através de frameworks/ferramentas de testes.

- Ferramentas de Teste: existem diversas ferramentas/suites/frameworks de teste, todas com suas especificações próprias e configurações que devem ser estudadas antes de seu uso. Entretanto, mesmo com tantas ferramentas de teste, todas se resumem ao seguinte comportamento: inserir casos de teste, executar a ferramenta e esperar um relatório completo indicando se os testes passaram ou não. Exemplos de suites de teste: *JUnit, AssertJ, Selenium, jqwik e pytest*.

- Cobertura de Código: linhas do código que são checadas por alguma teste. Uma alta cobertura de código não garante um programa bem polido, mas normalmente é visto com bons olhos.

- Testes duplicados: testes que abordam a mesma função e caso já analisado por outro código. Normalmente códigos duplicados são removidos, mas alguns os deixam para facilitar a compreensão dos novatos ao verem os códigos de teste.

