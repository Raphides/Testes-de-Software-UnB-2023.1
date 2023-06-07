# Testes de Caixa Branca

São testes que focam em encontrar erros na lógica do programa. Aqui entram testes nas árvores de decisões e condições do programa, checagem de laços e recursões, compreensão da pilha de chamada de funções, etc.

É **obrigatório** o acesso ao código fonte da funcionalidade/integração/sistema para poder analisar sua lógica por traś. 

## Características
- Não exige um profundo conhecimento da linguagem de programação escolhida, só de lógica de programação em si.
- Complexidade crescente à quantidade de decisões, expressões e funções existentes na linha lógica do programa.
- Mais usada em teste de baixo escopo.
- Normalmente é acompanhada com uma tabela ou diagrama de decisão.


## Decisões vs Condições
Entender a diferença entre ambas as nomenclaturasna área de testes é essencial para entender testes caixa-branca e as suas técnicas. Muitas vezes, ambos os termos são considerados sinônimos, mas no contexto de testes:
  - **Decisões** são o conjunto de expressões dentro de um termo condicional. Elas normalmente contam com várias expressões lógicas dentro de si, mas no final, uma decisão deve convergir a True ou False (com exceção do Switch).
```c
if (a == b && b == c) // Decisão 1 é "a == b && b == c"
  //se a decisão 1 for True
else:
  // se a decisão 1 for False
```
  - **Condições** são as expressões lógicas dentro de uma decisão. Elas também convirgem a True ou False.
```c
if (a == b && b == c) // Condição 1 é "a == b"; Condição 2 é "b == c"
  //se a condiçaõ 1 e 2 forem verdadeiras.
else:
  // caso a condição 1 e/ou 2 forem falsas.
```


## Gráfico de Fluxo de Controle

![image](https://github.com/Raphides/Testes-de-Software-UnB-2023.1/assets/89037051/057dd078-cfee-4957-8744-38616d4ac437)

O Gráfico de Fluxo de Controle é uma forma de mapear o seu código, focando principalmente nos diferentes condições, decisões, mudanças e caminhos que o programa vai tomar. Esse tipo de gráfico é muito usado como auxílio na produção de testes de caixa-branca, visto que representa os possíveis diferentes comportamentos do seu programa de forma simples. Normalmente são representados em gráficos assim:
- Tomada de decisões - Através de losângos com bifurcações.
- Expressões Lógicas (condição) - Através de losângos com bifurcações.
- Laços/Loops - Através de condições/decisões que criam ciclos no fluxo.
- Ação relevante - Atravpes de um retângulo.
