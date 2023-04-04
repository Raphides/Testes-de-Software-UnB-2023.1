# Resumo do capítulo 1 - Fundamentals of Software Testing (Bénard)

## Por que é importante realizar testes?

Softwares estão presentes no nosso dia a dia em diversos produtos. Falhas em seus sistemas podem deixar o serviço/produto inoperável, o que no caso de tecnologias de banco, hospitais, voos e vários outros serviços, geram consequências desastrosas. Alguns problemas que podem se decorrer de falhas de software são:
- Perda da confiabilidade do público nas empresas desenvolvedoras e afiliadas.
- Menor número de venda e aumento das devoluções.
- Vazamento de dados sensíveis, como número do cartão de crédito.
- Dano a pessoas, alguns até fatais.

Casos mais graves, como a perda do módulo "Mars Polar Lander" ou as mortes resultantes das falhas no Therac-25, geraram um prejuízo enorme de vidas e dinheiro. Elas mostram a necessidade de entregar softwares de qualidade.

## Causas de defeitos em software

Primeiro precisamos entender a diferença entre:
- Erro: ação humana que causa um defeito.
- Defeito: representação do erro humano no produto
- Falha: consequências de um defeito na execução ou integração do produto. Podem ser causados tanto por defeitos gerados por erros internos (humanos), quanto por problemas externos (malfuncionalidade no hardware ou em outros software, tempestades, interferências de sinal, sobreaquecimento) 

Exemplo: o programador esquece do ; na liguagem C (erro do programador, defeito no progrma). Na execução do programa, esse erro do programador lança uma Exceção ao compilador. Por fim, o programa encerra a sua execução devido ao erro.(falha)

## O que são Testes

Diferente da área de qualidade, que visa em garantir que a sua equipe siga as práticas mais adequadas do processo de desenvolvimento de software, a área de testes foca em criar ferramentas que possam, de forma eficiente, encontrar defeitos em softwares. A prática de testes ocorrem durante todo o ciclo de desenvolvimento de software.

A comunidade de software costuma utilizar duas abordagens diferentes na produção de testes:

|Abordagem|Foco|Quando começa|Para projetos de tamanho|
|-|-|-|-|
|Tradicional|Documentação|Após realizar o design dos testes|Grande
|Ágil|Execução|Desde o planejamento do produto|Pequenos

Corrigir defeitos pode se tornar caro, portanto testes são usados para agrupar informações estatísticas importantes a tomadores de decisões dentro de empresas. Assim, a empresa pode decidir se corrige ou não a malfuncionalidade. Esta em si é a principal diferença entre **testes** e ***debugging***, processo este que foca em achar e remover a causa da falha no sistema. Testes ficam registrados e servem como forma de garantir quais as características que o software deve apresentar, ou seja, para os testes nao acharem falha alguma. Essa concepção de testes caracterizando um produto é o de onde vem a ***Test Driven Development*** (TDD) que em breve será abordada.

## Princípios e Paradoxos de Testes

- Caso todos os testes não encontrem nenhum defeito, não é garantia que o seu software não terá defeitos. Testes não cobrem toda as milhares de possibilidades de defeitos.
- Testar tudo é quase sempre inviável, tentar gera testes lentos. Procure casos de teste que cubram outros casos.
- Teste o mais cedo possível, consertar defeitos no início do projeto costuma ser mais barato.
- Tente achar padrões de onde os bugs do seu software estão concentrados.
- A quantidade, foco e qualidade dos testes dependem do contexto.
- Corrigir erros nem sempre vai fazer o seu software decolar nas vendas.


