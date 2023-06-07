# Técnicas de Caixa Branca

## Cobertura de Comandos (*Statement Coverage*)

- **Definição**: testes que cobrem todas as expressões (statements) do programa.

- **Como fazer**: fazer um teste em que todas AS LINHAS do programa são de fato executadas.

- **Eficácia**: baixa

- **Pontos Cegos**:
    - Condicionais sem else, já que nunca testamos caso o if não seja acionado.
    - Funções com parâmetros de longo escopo
    - Códigos com vários ramos/decições, já que durante a execução, nem todas as linhas serão utilizadas.
    - Códigos com loops.
    - Códigos com parâmetros de entrada a serem manipulados/tratados/utilizados.

- **Tamanho**: pequeno

- **Dificuldade de Realização**: baixa

## Cobertura de Decisões / Ramo (*Branch Coverage*)

- **Definição**: testes que cobrem toda a árvore de decisões de um programa.

- **Como fazer**: elaborar testes que executem ao menos uma vez estruturas condicionais em suas possibilidades verdadeiras e falsas.

|Linha da Decisão|Caso verdadeiro|Caso falso|
|-|-|-|
|Número da Linha|O que precisa acontecer para a decisão ser verdadeira|O que precisa acontecer para a decisão ser falsa|

- **Eficácia**: baixa.

- **Pontos Cegos**:
    - Programas sem decisão, impedindo o que testar.
    - Condições que chamam funções de grande escopo ou com muitos argumentos de entrada, já que é difícil prever se a função realmente chegará a resultar verdadeiro e falso.
    - Condições que dependem do resultado de outras condições, gerando um crescimento exponencial de teste ( $f(x) = 2^x$ )
    - Condições com múltiplos operadores lógicos e requisitos anteriores, já que esse teste só testa a expresão condicional inteira, não cada parte dela.

- **Tamanho**: pequeno

- **Dificuldade de Realização**: baixa


## Cobertura Condicional (*Condition Coverage*)

- **Definição**: testes que cobrem todas as possíveis expressões lógicas (requisitos) de uma decisão. Importante principalmente para condições e laços com conectivos lógicos AND e OR.

- **Como fazer**: mapeie casos testes que cubram os valores verdadeiros e falsos de cada componente de expressão lógica incluso numa expressão condicional. Para isso, use a seguinte tabela de auxílio.


|Linha da Decisão|Condição|Condição verdadeira|Condição falsa|
|-|-|-|-|
|Número da linha|A condição analisada|O que precisa acontecer para a condição ser verdadeira|O que precisa acontecer para a condição ser falsa|


- **Eficácia**: média.

- **Pontos Cegos**:
    - Condições com expressões lógicas que ignoram parte das condições, normalmente causados pelos próprios conectivos *and*(&&) e *or*(||). Exemplo: em um ` if (exp1 and exp2)`, caso *exp1* for falso, não importa o valor de *exp2*, o resultado da condição sempre será falso. Não adianta testar *exp1* e *exp2* separadamente, quando *exp2* sequer fará diferença na expressão final. Esse detalhe passa sem ser visto nesse tipo de teste.
    - Alguns casos podem cobrir todas as condições, mas não todas as decisões.

- **Tamanho**: médio

- **Dificuldade de Realização**: baixa


## Cobertura de Decisão/Condição (*Decision/Condition Coverage*)

- **Definição**: uma mistura das coberturas de decisão e condição. Logo, é um teste que cobre todos os resultados de cada decisão e condição ao menos uma vez.

- **Como fazer**: mapeie casos testes que no total, executem ao menos uma vez todos os valores de saída de cada decisão e condição. Utilize a tabela da [Cobertura de Condições](#Cobertura-Condicional) para mapear.

- **Eficácia**: média/alta

- **Pontos Cegos**:
    - Condições seguidas por *and* e *or* podem mascarar as condições subsequentes. Sem o devido cuidado, os testadores podem não perceber isso e acabar ciando testes de decisão/condição que cumprem a definição, mas não testem de fato o funcionamento de cada condição em uma decisão de múltiplas-condições.

- **Tamanho**: médio/alto

- **Dificuldade de Realização**: média/alta, pela necessidade de entender bem a lógica por trás do código.

## Cobertura de Múltiplas Condicionais

- **Definição**: testes que cobrem TODAS as combinações de decisões possíveis, incluindo os possíveis valores de cada componente de expressão lógica na condição e até mesmo valores inválidos para a árvore de decisão. Essa técnica cobre consequentemente as demais.

- **Como fazer**: mapeie casos testes que cubram todos os possíveis caminhos de saída nas decisões e condições. Utilize a tabela da [Cobertura de Condições](#Cobertura-Condicional) para mapear.

- **Eficácia**: alta

- **Pontos Cegos**: nenhum

- **Tamanho**: alto.

- **Dificuldade de Realização**: média/alta, pela necessidade de entender bem a lógica por trás do código. Em códigos grandes, pode se tornar algo impraticável de ser realizado.


Normalmente as técnicas aqui descritas são usadas em conjunto em casos de testes.
