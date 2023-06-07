# Técnicas de Caixa Branca

## Cobertura de Comandos (*Statement Coverage*)

- **Definição**: testes que cobrem todas as expressões (statements) do programa.

- **Como fazer**: fazer um teste em que todas AS LINHAS do programa são de fato executadas.

- **Eficácia**: baixa

- **Pontos Cegos**:
    - Condicionais sem else, já que nunca testamos caso o if não seja acionado.
    - Funções com parâmetros de longo escopo
    - ...

- **Tamanho**: pequeno

- **Dificuldade de Realização**: baixa

## Cobertura de Decisões / Ramo (*Branch Coverage*)

- **Definição**: testes que cobrem toda a árvore de decisões de um programa.

- **Como fazer**: elaborar testes que executem ao menos uma vez estruturas condicionais em suas possibilidades verdadeiras e falsas.

|Decisão|Condição|Condição verdadeira|Condição falsa|
|-|-|-|-|
|ID|o que acontece|O que precisa acontecer para a condição ser verdadeira|O que precisa acontecer para a condição ser falsa|

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

- **Como fazer**: escreva testes que cubram os valores verdadeiros e falsos de cada componente de expressão lógica incluso numa expressão condicional. Cada 

- **Eficácia**: média.

- **Pontos Cegos**:
    - Condições com expressões lógicas que ignoram parte das condições, normalmente causados pelos próprios conectivos *and*(&&) e *or*(||). Exemplo: em um ` if (exp1 and exp2)`, caso *exp1* for falso, não importa o valor de *exp2*, o resultado da condição sempre será falso. Não adianta testar *exp1* e *exp2* separadamente, quando *exp2* sequer fará diferença na expressão final. Esse detalhe passa sem ser visto nesse tipo de teste.
    - Alguns casos podem cobrir todas as condições, mas não todas as decisões.

- **Tamanho**: médio/grande

- **Dificuldade de Realização**: baixa

## Cobertura de Decisão/Condição (*Decision/Condition Coverage*)

## Cobertura de Múltiplas Condicionais

- **Definição**: testes que cobrem TODAS as combinações de decisões possíveis, incluindo os possíveis valores de cada componente de expressão lógica na condição e até mesmo valores inválidos para a árvore de decisão. Essa técnica cobre consequentemente as demais.

- **Eficácia**: alta

- **Pontos Cegos**: nenhum

- **Tamanho**: pequeno/médio

- **Dificuldade de Realização**: média/alta, pela necessidade de entender bem a lógica por trás do código. Em códigos grandes, pode se tornar algo impraticável de ser realizado.


Normalmente as técnicas aqui descritas são usadas em conjunto em casos de testes.
