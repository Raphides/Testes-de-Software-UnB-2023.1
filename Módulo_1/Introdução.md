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


## A Psicologia dos Testes

Já sabemos que não é possível testar todos os resultados possíveis de um processo. É necessário saber o que e quando testar, habilidade essa que requer uma certa "visão" por parte do programador.

Essa noção impacta, por exemplo, na definição de testes, já que sempre será mais fácil achar erros se você de fato estiver com a intenção de encontrá-los. Uma pessoa que faz testes "para conferir se o software funciona" provavelmente focará em erros mais simples, já que eles de fato buscam um software que funcione.

Em outras palavras, o pensamento de alguém que vai testar seu programa deve ser de fato destrutivo. Chega a ser um tanto masoquista quando é você ou sua equipe a responsável pelos testes. Não achar erros num software é uma derrota, já que nenhum software é perfeito. E não se sinta mal, isso não é diferente do que um médico faz ao tentar achar doenças e problemas num paciente.


## Princípios e Paradoxos de Testes

1. Caso todos os testes não encontrem nenhum defeito, **não há garantia que o seu software não terá defeitos**. Testes não cobrem toda as milhares de possibilidades de defeitos.

2. **Testar tudo é quase sempre inviável**, tentar gera testes lentos. **Procure casos de teste que cubram outros casos** e **saiba quando parar**.

3. **Teste o mais cedo possível**, consertar defeitos no início do projeto costuma ser mais barato.

4. A quantidade, foco e qualidade dos testes dependem do contexto.

5. Corrigir erros nem sempre vai fazer o seu software decolar nas vendas.

6. **Paradoxo do Inseticida**: veja testes anteriores do projeto antes de fazer os seus. Muitos projetos sofrem em ter vários testes para um único caso, principalmente após a manutenção do software ou vinda de novos desenvolvedores.

7. **Tenha bem definida a saída** desejada da sua funcionalidade. Não há como achar erros sem saber o que esperar

8. Os mais envolvidos com o produto, principalmente os desenvolvedores, devem evitar testar seu próprio software. Isso porque os envolvidos costumam se apegar pelo produto. Portanto é mais provável que eles não consigam apresentar o caráter destrutivo necessário aos testes. Sem contar que os erros podem vir da falta de conhecimento dos envolvidos, o que dificultará o teste por parte deles.

9. **Escreva casos com inputs válidos e invalidos**. É importante entender como seu programa lida com situações que devem ser realizadas por ele, já que se não tiver mecanismos para lidar com isso, pode acabar afetando até os casos com inputs válidos.

10. Não faça testes que enchem linguiça, isso não aumentará do grau de qualidade do seu software.

11. **Não planeje testes sem esperar encontrar erros**. Isso vai de contramão ao psicológico destrutivo necessário aos testes.

12. **Princípio da fumaça**: se uma funcionalidade apresenta muitos erros, há grandes probabilidades de terem mais. Foque nessas funcionalidades.

13. **Testar é uma prática extremamente criativa** e intelectual. Não é fácil achar testes que cubram outros ou pensar em casos extremos e únicos. Os métodos daqui só ajudam, mas boa parte depende do quanto você consegue abstrair e imaginar.
 
