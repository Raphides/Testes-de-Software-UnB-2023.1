# Introdução à Testes de Software

# O que são testes?
Testes são uma série de práticas feitas por usuários e desenvolvedores de uma aplicação ou produto a fim de **encontrar defeitos** em qualquer parte do processo de produção.

Diferente da área de qualidade, que visa em garantir que a sua equipe siga as práticas mais adequadas do processo de desenvolvimento de software, a área de testes foca em criar ferramentas que possam, de forma eficiente, encontrar defeitos em softwares. A prática de testes ocorrem durante todo o ciclo de desenvolvimento de software.

A comunidade de software costuma utilizar duas abordagens diferentes na produção de testes:

|Abordagem|Foco|Quando começa|Para projetos de tamanho|
|-|-|-|-|
|Tradicional|Documentação|Após realizar o design dos testes|Grande
|Ágil|Execução|Desde o planejamento do produto|Pequenos

Corrigir defeitos pode se tornar caro, portanto testes são usados para agrupar informações estatísticas importantes a tomadores de decisões dentro de empresas. Assim, a empresa pode decidir se corrige ou não a malfuncionalidade. Esta em si é a principal diferença entre **testes** e ***debugging***, processo este que foca em achar e remover a causa da falha no sistema. Testes ficam registrados e servem como forma de garantir quais as características que o software deve apresentar, ou seja, para os testes nao acharem falha alguma. Essa concepção de testes caracterizando um produto é o de onde vem a ***Test Driven Development*** (TDD) que em breve será abordada.

## Por que é importante realizar testes?

Softwares estão presentes no nosso dia a dia em diversos produtos. Falhas em seus sistemas podem deixar o serviço/produto inoperável, o que no caso de tecnologias de banco, hospitais, voos e vários outros serviços, geram consequências desastrosas. Alguns problemas que podem se decorrer de falhas de software são:
- Perda da confiabilidade do público nas empresas desenvolvedoras e afiliadas.
- Menor número de venda e aumento das devoluções.
- Vazamento de dados sensíveis, como número do cartão de crédito.
- Dano a pessoas, alguns até fatais.

Casos mais graves, como a perda do módulo "Mars Polar Lander" ou as mortes resultantes das falhas no Therac-25, geraram um prejuízo enorme de vidas e dinheiro. Elas mostram a necessidade de entregar softwares de qualidade.

## Por que estudar testes?
Testes normalmente ocupam de 50% a 75% do tempo de desenvolvimento, isso porque o proceso de testes de software costuma ser um dos processos mais difíceis comparado a outros testes. Isso se dá principalmente devido a grande quantidade de variáveis a serem considerados

Desde o início, já procuramos erros no nosso software, ou seja, testes sempre são feitos, entretanto estudar testes é importante para que os programadores e projetistas façam testes de forma mais **sistemática e efetiva**. Isso garante um **aumento de qualidade** do desenvolvimento do produto.

Equipes ágeis adotam os testes em todas fases de desenvolvimento.

Para realizar testes efetivos, é preciso:
- Saber quando e o que testar, se testarmos tudo, perdemos muito dinheiro e se não testarmos nada, o produto pode ter mal funcionamento.
- Lembrar que mesmo de forma sistemática, não há receita de bolo para escolher qual tipo de teste e como fazer. Cada produto necessita diferentes testes.

## Princípios e Paradoxos de Testes

- Caso todos os testes não encontrem nenhum defeito, não é garantia que o seu software não terá defeitos. Testes não cobrem toda as milhares de possibilidades de defeitos.
- Testar tudo é quase sempre inviável, tentar gera testes lentos. Procure casos de teste que cubram outros casos.
- Teste o mais cedo possível, consertar defeitos no início do projeto costuma ser mais barato.
- Tente achar padrões de onde os bugs do seu software estão concentrados.
- A quantidade, foco e qualidade dos testes dependem do contexto.
- Corrigir erros nem sempre vai fazer o seu software decolar nas vendas.

 
