# Conceitos de Teste

## Conceitos gerais

- **Testes**: série de práticas com o intuito de encontrar defeitos num produto.

- **Caso de teste**: situação contextualizada com entradas e saídas bem definidas. A expressão "*derivar casos de teste*" referencia o ato de criar casos de teste diversos e com uma boa cobertura do seu código.

- **Ferramentas de Teste**: existem diversas ferramentas/suites/frameworks de teste, todas com suas especificações próprias e configurações que devem ser estudadas antes de seu uso. Entretanto, mesmo com tantas ferramentas de teste, todas se resumem ao seguinte comportamento: inserir casos de teste, executar a ferramenta e esperar um relatório completo indicando se os testes passaram ou não. Exemplos de suites de teste: *JUnit, AssertJ, Selenium, jqwik e pytest*.



- **Testes Automatizados**: testes que podem ser realizados sem quaisquer dificuldades ou configuração quando você bem entender. Exemplo: quando um membro da equipe propõe uma adição de código num projeto. Normalmente testes automatizados são implementados através de frameworks/ferramentas de testes.

- **Cobertura de Código**: linhas do código que são checadas por alguma teste. Uma alta cobertura de código não garante um programa bem polido, mas normalmente é visto com bons olhos.

- **Testes duplicados**: testes que abordam a mesma função e caso já analisado por outro código. Normalmente códigos duplicados são removidos, mas alguns os deixam para facilitar a compreensão dos novatos ao verem os códigos de teste.

## Causas de defeitos em software
- **Erro**: ação humana que causa um defeito.

- **Defeito**: representação do erro humano no produto

- **Falha**: consequências de um defeito na execução ou integração do produto. Podem ser causados tanto por defeitos gerados por erros internos (humanos), quanto por problemas externos (malfuncionalidade no hardware ou em outros software, tempestades, interferências de sinal, sobreaquecimento) 

Exemplo: o programador esquece do ; na liguagem C (erro do programador, defeito no progrma). Na execução do programa, esse erro do programador lança uma Exceção ao compilador. Por fim, o programa encerra a sua execução devido ao erro.(falha)

## Verificação vs Validação (V&V)
Veja a norma ISO/IEC 12207.

- **Verificação**: checa se uma unidade ou funcionalidade está de fato funcionando como esperado e de acordo com os requisitos de projeto.
    - É mais técnico.
    - Artefatos também podem ser verificados, avaliando se esses requisitos de fato podem ser alcançados.
- **Validação**: checa se as ideias, unidades e funcionalidades atendem às necessidades e preferências dos usuários e compradores, se está adequada a eles.
    - Normalmente é realizada durante as conversas com o cliente e as revisões das sprints/ciclos.

### Abordagens de V&V
- Estáticas:
    - Revisão
    - Walkthrout
- Dinâmicas:
    - Testes de Software

### Abordagens de erros por V&V
- Estático:
    - **Engano/*mistake***: ação humana que produz um estado incorreto.
    - **Defeito** (fault/bug): alguma inconsistência nos dados/programa. Um conceito de V&V estático
- Dinâmico:
    - **Erro**: execução inconsistente de um caso do software.
    - **Falha**: falha geral na execução do software/programa.

## Outros

- **Artefatos de Software**: documentos e códigos gerados durante a produção de um software, normalmente derivado do processo de Requisição de Software.

- **Requisição de Software**: quais ações, funcionalidades e especificações o seu software deve ter. É a fase inicial na produção de um software profissional e normalmente conta com vários artefatos de software que descrevem e organizam as requisições de forma mais simples. Os requisitos de software são o que gera o output esperado para muitas funções e não é incomum que revisões e adições sejam feitas nos requisitos, principalmente durante os processos de teste.
