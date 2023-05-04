
# Técnicas de Caixa Preta

## Particionamento Equivalente

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

## Análise de Bordas/Valores Limites

Como seu nome já sugere, testes de análise de bordas testam as bordas das funções. Mas especificamente, um teste desse tipo foca em testar casos nos pontos de virada dos valores recebidos e retornados em uma função. Esses pontos de virada, ou mudanças de comportamento, podem ser considerados como as divisões entre cada partição equivalente, método explicado anteriormente.

Uma das adições importantes desse método é que ao avaliar casos de borda, essa técnica não se importa somente com as entradas de uma função, mas também com as saídas, cobrindo bem mais erros do que ao usar somente o método de [partição equivalente](#Particionamento-Equivalente)

Caso tenha dificuldade em identificar bordas, pense em exemplos extremos de entradas e saídas da sua função. Extremo é outra palavra para identificar uma borda, mas normalmente apresenta um reflexo melhor em pensar em bordas.

É sempre bom, ao encontrar pontos de virada, adicionar testes com valores em volta dos pontos. Por exemplo:
- Ao realizar uma função de somar cada número inserido em um vetor, um ponto de virada é quando o vetor não tem elementos nele, porque a tomada de decisão nessa hora muda do padrão. Logo, dois casos de teste dessa função seriam: uma lista vazia e outro caso com uma lista de só um elemento numético. 
- Ao realizar uma função que só aceita como parâmetro um número inteiro de 0 a 10, dois casos de testes seriam: uma com entrada 0 e outra com entrada -1. Outros dois seriam: 10 e 11.

Funções com condições e intervalos de entrada e saída normalmente são um bom alvo para serem testadas por testes de valor limite.

## Gráfico Causa-Efeito

Gráficos de causa e efeito
