# Casos de Teste

Como não é possível testar todas as possibilidades num programa real, nosso objetivo no estudo de casos de teste tem como meta achar qual subconjunto dos testes possíveis cobre a maior quantidade de erros num contexto específico. Portanto, neste capítulo, serão abordados métodos de Caixa Preta e Caixa Branca que, quando aplicados juntos, geram subconjuntos de testes com altas coberturas.

Como foi dito, é interessante usar as técnicas de Caixa Branca e Caixa Preta simultaneamente numa mesma *test case*. Recomenda-se começar elaborando os testes com técnicas de Caixa Preta e por fim ir implementando funções adicionais com métodos de teste de Caixa Branca 


## Técnicas de Caixa Branca

### Cobertura de Expressões

- Definição: testes que cobrem todas as linhas de código.
- Como fazer: fazer um teste em que todas as linhas do programa são de fato executadas.
- Eficácia: baixa
- Pontos Cegos: Condicionais sem else, funções com parâmetros de longo escopo, etc.
- Tamanho: pequeno
- Dificuldade: baixa

### Cobertura de Decisões / Ramo

- Definição: testes que cobrem todas as possíveis decisões em um programa.
- Como fazer: elaborar testes que executem ao menos uma vez estruturas condicionais em suas possibilidades verdadeiras e falsas.
- Eficácia:
    - Sozinha: baixa
    - Com Cobertura de Expressões como requisito: baixa/média.
- Pontos Cegos: programas sem decisão, condições que possuem métodos com vários parâmetros de entrada, condições que dependem do resultado de outras condições, condições com múltiplos requisitos.
- Tamanho: pequeno
- Dificuldade: baixa


### Cobertura Condicional

- Definição: testes que cobrem todas as possíveis expressões lógicas (requisitos) de uma decisão. Importante principalmente para condições e laços com conectivos lógicos (&& e ||)
- Como fazer: escreva testes que cubram os valores verdadeiros e falsos de cada componente de expressão lógica incluso numa condição.
- Eficácia:
    - Sozinha: baixa
    - Com coberturas de decisão e de expressão: média
- Pontos Cegos (dos 3 juntos): condições com expressões lógicas que ignoram parte da expressão lógica, normalmente causados por conectivos *and*(&&) e *or*(||).
- Tamanho: médio/grande
- Dificuldade: média

### Cobertura de Múltiplas Condicionais

- Definição: testes que cobrem todas as combinações de decisões possíveis e os possíveis valores de cada componente de expressão lógica na condição.
- Eficácia: alta
- Pontos Cegos: 
- Tamanho: pequeno/médio
- Dificuldade: média/alta


## Técnicas de Caixa Preta

## Particionamento Equivalentes

É a estratégia pelo qual se divide todos os parâmetros de uma função em partições/classes que se assemelham em aspectos, prováveis erros e resultados numa função. Após a separação, são selecionados os representantes que cobrem as maiores quantidades de parâmetros de sua respectiva partição. Os testes são feitos com base nos representantes de cada parte, diminuindo em muito a quantidade de testes a serem realizados.

Referir-se a uma partição/classe equivalente siginifica por em um grupo vários casos de entradas de função que tendem a possuir o mesmo comportamento no processo.

Exemplo: numa função de soma entre dois números, podemos separar partições equivalentes de entradas inteiras positivas, inteiras negativas, inteiras positivas e negativas, infinitas, decimais, não numéricas (strings, booleanas, etc...).

### Dicas de particionamentos equivalentes:
- Todos os resultados contam, por isso normalmente há a separação de classes equivalentes de entradas **válidas** e **inválidas**.
- Se uma função possui um intervalo de valores válidos, prossiga com uma classe válida e duas inválidas. Ex: a função funciona se a entrada for um número de 1 até 10. Partição 1 (válida):  1 <=input <= 10; partição 2 (inválida): input > 10; e partição 3 (inválida): input < 1.
- Se uma função ter pedir entradas muito pré espicificadas (como constantes de Enums), faça uma partição válida para cada e mais uma partição inválida caso não seja nenhum valor especificado. É bem provável que funções assim lidem com cada valor específico de forma diferente.
- Se uma função especificar uma exigência, no mínimo faça duas classes, uma válida cumprindo-a e outra inválida descumprindo-a.
- Para casos de partições de entradas inválidas, faça UM ÚNICO caso de teste para CADA partição por segurança.
- Para casos de partições de entradas válidas, faça casos de testes que cubram o máximo de partições válidas que você puder.

Bons testes de equivalência de partições cobrem todos as suas partições.

## Análise de Bordas

Como seu nome já sugere, testes de análise de bordas testam as bordas das funções. Mas especificamente, um teste desse tipo foca em testar casos nos pontos de virada de uma função. Esses pontos de virada, ou mudanças de comportamento, podem ser considerados como as divisões entre cada partição equivalente, com a difereneça de que essa técnica não se importa somente com as entradas, mas também com as saídas.

Por exemplo: ao realizar uma função de somar cada número inserido em um vetor, um ponto de virada é quando o vetor tem somente um elemento, o que faria com que um vetor não somasse nada, só retornasse o primeiro elemento. Outro seria quando o vetor não possui elemento algum. Ao colocar elementos além da capacidade de processamento do dispositivo, o que aconteceria.

Caso tenha dificuldade em identificar bordas, pense em exemplos extremos de entradas e saídas da sua função. Extremo é outra palavra para identificar uma borda, mas normalmente apresenta um reflexo melhor em pensar em bordas.

## 

## 
