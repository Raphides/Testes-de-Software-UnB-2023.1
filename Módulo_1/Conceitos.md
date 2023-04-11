# Conceitos de Teste

- Testes: série de práticas com o intuito de encontrar defeitos num produto.

- Artefatos de Software: documentos e códigos gerados durante a produção de um software.

## Causas de defeitos em software
- Erro: ação humana que causa um defeito.
- Defeito: representação do erro humano no produto
- Falha: consequências de um defeito na execução ou integração do produto. Podem ser causados tanto por defeitos gerados por erros internos (humanos), quanto por problemas externos (malfuncionalidade no hardware ou em outros software, tempestades, interferências de sinal, sobreaquecimento) 

Exemplo: o programador esquece do ; na liguagem C (erro do programador, defeito no progrma). Na execução do programa, esse erro do programador lança uma Exceção ao compilador. Por fim, o programa encerra a sua execução devido ao erro.(falha)

# Verificação vs Validação (V&V)
Veja a norma ISO/IEC 12207.

- **Verificação**: checa se uma unidade ou funcionalidade está de fato funcionando como esperado e de acordo com os requisitos de projeto.
    - É mais técnico.
    - Artefatos também podem ser verificados, avaliando se esses requisitos de fato podem ser alcançados.
- **Validação**: checa se as ideias, unidades e funcionalidades atendem às necessidades e preferências dos usuários e compradores, se está adequada a eles.
    - Normalmente é realizada durante as conversas com o cliente e as revisões das sprints/ciclos.

## Abordagens de V&V
- Estáticas:
    - Revisão
    - Walktrhout
- Dinâmicas:
    - Testes de Software

## Abordagens de erros por V&V
- Estático:
    - Engano/*mistake*: ação humana que produz um estado incorreto.
    - Defeito (fault/bug): alguma inconsistência nos dados/programa. Um conceito de V&V estático
- Dinâmico:
    - Erro: execução inconsistente de um caso do software.
    - Falha: falha geral na execução do software/programa.

