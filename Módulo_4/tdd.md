# Test Driven Development (TDD)

O **Desenvolvimento Dirigido por Testes** é uma estratégia de produção de projetos de código veloz, que junta o desenvolvimento de *requisitos, implementação, testes* em um único processo intercalável.

Sua ideia principal centra-se em realizar testes antes de sequer implementar o código.

## Estrutura básica

O TDD é dividido em 3 etapas cíclicas:
- ![Vermelho](#Vermelho)
- ![Verde](#Verde)
- ![Refatoração](#Refatoração)

![TDD - Etapas Vermelho, Verde e Refatorar](https://github.com/Raphides/Testes-de-Software-UnB-2023.1/assets/89037051/e39a9812-3390-460c-b547-26e1c65356ac)


### Vermelho

A etapa vermelha é a primeira do ciclo TDD. Seu nome é este devido a essa respectiva cor normalmente representar *falha*. Isto porque a etapa vermelho é uma etapa centrada em falhas. Mais especificamente, nessa etapa, o testador deve:
- Dividir o sistema em unidades pequenas e individuais de funcionalidades. Escolher uma dessas unidades funcionais.
- Criar casos de teste para cobrir a funcionalidade.
- Implementar os casos de teste em versão de código, ou ao menos simular a sua execução mentalmente.
- Executar os casos de teste.
- Caso todos os testes falhem:
    - Significa que os seus testes estão no caminho **certo**.
- Caso algum teste NÃO falhe:
    - Ou há alguma funcionalidade a ser criada já existe, tornando o desenvolvimento desta funcionalidade redundante.
    - Ou a implementação de algum caso de teste possui algum defeito, gerando um **falso positivo**.

Perceba como esta etapa em si une a definição de requisitos e implementação de testes em uma única etapa simultânea.

## Verde

Associada a ideia de que a cor verde é usada para casos de sucesso, a etapa Verde consiste na criação de código suficiente para fazer os casos de teste definidos na etapa Vermelha passarem.

Se a etapa Vermelha aborda a criação de requisitos e testes, esta etapa abordará a implementação de código. Simultaneamente, o código implementado deve ser capaz de cumprir os requisitos e passar pelos testes. Tudo isso resumido a uma produção de testes curta e veloz.

Alguns cuidados:
- A etapa só estará completa quando todos os testes implementados forem bem sucedidos.
- Caso algum teste não passe, é tanto possível que o código possua algum defeito, quanto é possível que o teste implementado na etapa Vermelha não tenha sido feito de maneira correta. 

## Refatoração

A etapa de Refatoração é similar a uma **otimização e revisão**. As etapas Vermelho e Verde do TDD de fato geram o que prometeram: *requisitos, código, testes*, entretanto, o produto das duas etapas do TDD nem sempre é a melhor opção possível de teste e impĺementação. Para atingit níveis de qualidade maiores, eliminar redundâncias e linhas de código excessivas, a etapa Refatoração existe. Entretanto, caso ache que o código já foi bem implementada na Etapa Vermelha, pode-se pular a Refatoração.

Refatorar é o processo de modificar a estrutura interna do seu projeto sem alterar o conceito da funcionalidade em si. Ou seja, simplificar e otimizar o código da funcionalidades selecionada, sem mudar em nada os requisitos da mesma.

Alguns cuidados e precauções devem ser tomadadas:
- Não alterar os requisitos/testes.
- Salvar um backup da versão original do código, para caso a refatoração der errado, tenha como reverter as alterações feitas.
- A etapa só termina quando todos os testes estiverem passando com o código refatorado. É essencial executar TODOS os testes, para garantir que a refatoração não tenha quebrado nenhuma parte do produto.

---

Essas 3 etapas são repetidas para cada uma as unidades funcionais do sistema. Esta característica de abordar toda a implementação de cada funcionalidade por vez é uma ótima forma de fortalecer a ideia de que o código desenvolvido não quebra nenhuma outra parte do produto, aumentando assim a qualidade do código entregue.

Como cada funcionalidade passa por essas 3 etapas, é normal imaginar o TDD como uma abordagem extensa, monótona e pesada. Contudo, para não se tornar um trabalho longo e extenso, saiba que cada etapa é planejada para durar cerca de minutos quando realizadas por pessoas experientes com a metodologia TDD.
