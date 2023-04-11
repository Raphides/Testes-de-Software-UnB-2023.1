# Parte 1

## A Psicologia dos Testes

Já sabemos que não é possível testar todos os resultados possíveis de um processo. É necessário saber o que e quando testar, habilidade essa que requer uma certa "visão" por parte do programador.

Essa noção impacta, por exemplo, na definição de testes, já que sempre será mais fácil achar erros se você de fato estiver com a intenção de encontrá-los. Uma pessoa que faz testes "para conferir se o software funciona" provavelmente focará em erros mais simples, já que eles de fato buscam um software que funcione.

Em outras palavras, o pensamento de alguém que vai testar seu programa deve ser de fato destrutivo. Chega a ser um tanto masoquista quando é você ou sua equipe a responsável pelos testes. Não achar erros num software é uma derrota, já que nenhum software é perfeito. E não se sinta mal, isso não é diferente do que um médico faz ao tentar achar doenças e problemas num paciente.

## Teste de Caixa Preta

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

# Teste de Caixa Branca

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


## Princípios de teste

- Tenha bem definida a saída desejada da sua funcionalidade. Não há como achar erros sem qualquer expectativa.
- Os mais envolvidos com o produto, principalmente os desenvolvedores, devem evitar testar seu próprio software. Isso porque os envolvidos costumam se apegar pelo produto. Portanto é mais provável que eles não consigam apresentar o caráter destrutivo necessário aos testes. Sem contar que os erros podem vir da falta de conhecimento dos envolvidos, o que dificultará o teste por parte deles.
- Escreva casos com inputs válidos e invalidos. É importante entender como seu programa lida com situações que devem ser realizadas por ele, já que se não tiver mecanismos para lidar com isso, pode acabar afetando até os casos com inputs válidos.
- Não faça testes que enchem linguiça, isso não aumentará do grau de qualidade do seu software.
- Não planeje testes sem esperar encontrar erros. Isso vai de contramão ao psicológico destrutivo necessário aos testes.
- Princípio da fumaça: se uma funcionalidade apresenta muitos erros, há grandes probabilidades de terem mais. Foque nessas funcionalidades.
- Testar é uma prática extremamente criativa e intelectual. Não é fácil achar testes que cubram outros ou pensar em casos extremos e únicos. Os métodos daqui só ajudam, mas boa parte depende do quanto você consegue abstrair e imaginar.

# Parte 2

## Ferramentas de Teste
- JUnit
- AssertJ
- Selenium
- jqwik