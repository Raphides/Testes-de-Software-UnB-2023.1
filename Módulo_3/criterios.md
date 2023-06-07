# Critérios

### Critério de McCabe
É um critério que utiliza-se da análise da complexidade cinclomática de um GFC para determinar:
- Número de casos de teste para cobrir todos os caminhos.
- Nível de dificuldade dos casos de teste.
- Confiabilidade dos casos de teste
- Quantidade de caminhos base.

Um caminho base seria uma rota do início ao fim do código livre de loops e independente. Para adquirir os caminhos base, vá em seu GFC e escolha um caminho livre de loops, ele será seu 1º caminho base. Depois, altere o resultado da primeira decisão, tentando deixar o resto do caminho inalterado - esta é o seu 2º caminho base. Para o 3°, retorne a primeira decisão ao normal (caso seja possível para seguir à próxima decisão) e altere o rumo tomado na segunda decisão. Repita o processo do 3º caso base até que não haja outras decisões que você não tenha mudado alguma vez. O seu número de caminhos base deve ser idntico a $Caminho-base = arestas - nós + 2$. Agora crie um caso de teste para cada caminho-base. Isso já é o suficiente para garantir uma cobertura de decisões e comandos, duas técnicas abordadas mais em outro capítulo.
