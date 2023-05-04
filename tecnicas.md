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