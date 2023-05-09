
# Técnicas de Caixa Preta

## Testes Aleatórios
Testes que escolhem valores aleatórios, com base em intuição, ou que o programador julga poder ter valores diferentes ou de importante observação. Normalmente não possuem uma boa taxa de sucesso, além de baixa cobertura de código, mas podem funcionar.

## Advinhação de Erros
Outro método baseado na intuição do programador. A diferença entre esse e um teste aleatório seria que o testador aqui possui experiência e já imagina bem quais entradas e saídas de fato precisam ser observadas, mesmo sem um método específico lhe orientando.

## Particionamento Equivalente

É a estratégia pelo qual se divide todos os parâmetros de uma função em partições/classes/domínio que se assemelham em aspectos, prováveis erros e resultados numa função. Após a separação, são selecionados os representantes que cobrem as maiores quantidades de parâmetros de sua respectiva partição. Os testes são feitos com base nos representantes de cada parte, diminuindo em muito a quantidade de testes a serem realizados.

Referir-se a uma partição/classe/domínio equivalente siginifica pôr em um grupo vários casos de entradas de função que tendem a possuir o mesmo comportamento no processo.

Exemplo: numa função de soma entre dois números, podemos separar partições equivalentes de entradas inteiras positivas, inteiras negativas, inteiras positivas e negativas, infinitas, decimais, não numéricas (strings, booleanas, etc...).

### Dicas de particionamentos equivalentes:
- Todos os resultados contam, por isso normalmente há a separação de classes equivalentes de entradas **válidas** e **inválidas**.
- Se uma função possui um intervalo de valores válidos, prossiga com uma classe válida e duas inválidas. Ex: a função funciona se a entrada for um número de 1 até 10. Partição 1 (válida):  1 <=input <= 10; partição 2 (inválida): input > 10; e partição 3 (inválida): input < 1.
- Se uma função ter pedir entradas muito pré espicificadas (como constantes de Enums), faça uma partição válida para cada e mais uma partição inválida caso não seja nenhum valor especificado. É bem provável que funções assim lidem com cada valor específico de forma diferente.
- Se uma função especificar uma exigência, no mínimo faça duas classes, uma válida cumprindo-a e outra inválida descumprindo-a.

## Procedimentos:
1. **Identificar domínios de equivalência**
  - Baseia-se nas condições de entrada da sua funcionalidade.
  - Numere cada classe/domínio encontrado, negativo para inválidas e positivos para válidas
  - É de costume produzir essa tabela:

|Condições de Entrada|Classe Válida|Classe Inválida|
|-|-|-|
|(Título do parâmetro 1 de entrada)|(Intervalo de valores para parâmetros válidos)|(Intervalo de valores para parâmetros inválidos)|
|(Título do parâmetro 2 de entrada)|(Intervalo de valores para parâmetros válidos)|(Intervalo de valores para parâmetros inválidos)|
|...|...|...|


2. **Fazer testes aos domínios:**
    - Para casos de partições de entradas inválidas, faça UM ÚNICO caso de teste para CADA partição por segurança.
    - Para casos de partições de entradas válidas, faça casos de testes que cubram o máximo de partições válidas que você puder.
    - Muitas vezes é importante entender e organizar as saídas esperadas para cada partição.
    - Normalmente, uma tabela é feita:

|Contexto de Entrada|Saída esperada|Nº da partição aplicadas|
|-|-|-|
|(Valores 1 das condições de entrada da tabela anterior)|(autoexplicativo)|(classe(s) que será(ão) testada(s) nesse caso)|
|(Valores 2 das condições de entrada da tabela anterior)|(autoexplicativo)|(classe(s) que será(ão) testada(s) nesse caso)|
|... |... |... |

Bons testes de equivalência de partições cobrem todos as suas partições.

## Análise de Bordas/Valores Limites

Como seu nome já sugere, testes de análise de bordas testam as bordas das funções. Mas especificamente, um teste desse tipo foca em testar casos nos **pontos de virada** dos valores recebidos e retornados em uma função. Esses pontos de virada, ou mudanças de comportamento, podem ser considerados como as divisões entre cada partição equivalente, método explicado [anteriormente](#Particionamento-Equivalente).

Bordas, ou pontos de virada, normalmente possuem muitos defeitos por serem locais onde uma função costuma mudar seu comportamento típico. É normal fazer uma funcionalidade e esquecer de uma mudar seu comportamento em um ponto extremo. Ou até mesmo lembrar, implementando-o através de um if, mas errar na hora das comparações com < > != ==. Esse testes focam em cobrir esses erros extremamente comuns, mesmo sem ver o código.

Uma das adições importantes desse método é que ao avaliar casos de borda, essa técnica não se importa somente com as entradas de uma função, mas também com as saídas, cobrindo bem mais erros do que ao usar somente o método de [partição equivalente](#Particionamento-Equivalente).

Caso tenha dificuldade em identificar bordas, pense em exemplos extremos de entradas e saídas da sua função. Extremo é outra palavra para identificar uma borda, mas normalmente apresenta um reflexo melhor em pensar em bordas.

É sempre bom, ao encontrar pontos de virada, adicionar testes com valores em volta dos pontos. Por exemplo:
- Ao realizar uma função de somar cada número inserido em um vetor, um ponto de virada é quando o vetor não tem elementos nele, porque a tomada de decisão nessa hora muda do padrão. Logo, dois casos de teste dessa função seriam: uma lista vazia e outro caso com uma lista de só um elemento numético. 
- Ao realizar uma função que só aceita como parâmetro um número inteiro de 0 a 10, dois casos de testes seriam: uma com entrada 0 e outra com entrada -1. Outros dois seriam: 10 e 11.

Funções com condições e intervalos de entrada e saída normalmente são um bom alvo para serem testadas por testes de valor limite.

## Gráfico Causa-Efeito

Sendo normalmente usado para casos em que são precisos testes mais rigorosos que testem a maior parte das entradas e saídas possíveis. Essas situações normalmente acontecem em sistemas embarcados ou com outros sistemas de difícil correção no caso do menor dos erros.

Um gráfico de causa e efeito lista os padrões de causas responsáveis por influenciar em diferentes padrões de efeito, listando assim as especificações do seu sistema de forma simples. É um ótimo método para visualizar e listar todos os caminhos possíveis em códigos complexos. Sua implementação se assemelha bastante ao projeto de um circuito lógico, trocando as entradas e saídas respectivamente pelas causas e efeitos.

Esse gráfico causa-efeito por fim é convertido em uma espécie de tabela verdade, em que para cada linha/combinação deve ser criada um caso de teste.
