# Testes e Validação de Segurança

Existem diversas categoriais de ferramentas que permitem testes de segurança em um software. Normalmente programas mais maduros usam ferramentas de várias categorias, a fim de cobrir os pontos fracos uma da outra. Entre essas categorias, podemos citar:

## Categorias de Testes Automatizados:

### Análise Estática / Static Analysis Security Testing (SAST):

A partir da análise da lógica do projeto, o SAST procura por vulnerabilidades em pontos mais sucetíveis a erros a partir de padrões que comumente são explorados no código. Sua implementação pode ser simples ou complexa, sendo normalmente integrada ao script de *build* do projeto ou no próprio ambiente de desenvolvimento.

Desvantagens:
- Dependência no conhecimento do desenvolvedor de testes sobre possíveis pontos vulneráveis.
- Não aborda pontos de vulnerabilidade pensando também na **lógica de negócio**.
- Depende da disponibilidade de ferramentas SAST boas para as linguagens, modelos e frameworks utilizados.
- Pode apontar vulnerabilidades para invasão com dados que um invasor não consegue adquirir (falso positivo).

### Análise Dinâmica / Dynamic Analysis Security Testing (DAST):
Gera uma série de ataques simulados dentro do aplicativo funcionando como um todo.


Desvantagens:
- Dificilmente testa ataques no *setup* e nas configurações iniciais.
- 

### Fuzzing:

### Análise de Composição:

### Escaneamento de Vulnerabilidade de Rede:

### Verificação de Configurações:

### Mitigação dos Erros em diferentes Plataformas:

## Categorias de Testes Manuais:

### Verificação de Funcionalidades de Segurança

### Teste de Penetração / Pentest
