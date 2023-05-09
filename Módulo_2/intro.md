# Testes de Caixa Preta

Testes de Caixa Preta, também chamados de **Testes de Especificações** ou **Testes Orientado a Dados**, focam em testar funcionalidades de um sistema focando em suas respectivas especificaçes e requisitos. Num código em C, isso seria feito através de testes baseados somente nos arquivos de cabeçalho (.h). Claro, não só usar os cabeçalhos é o suficiente, saber o que a função deve fazer e como ela está posicionada no raciocínio lógico do seu código é essencial. Por isso, definir bem requisitos e especificações antes de um projeto é essencial.

Exemplo de cabeçalho:

```c
int somar(int a, int b);
int subtrair(int a, int b);
```
O fato de se preocupar principalmente com as entradas e saídas é o que lhe dá o nome de Orientado a Dados.

## Características Gerais:
Entre as características gerais dos testes de caixa preta, estão:
- Mais usado.
- Pode ser realizado em níveis unitários e sistemáticos.
- No caso de testes caixa preta unitários, sua complexidade de implementação é baixa, permitindo pessoas com pouca ou nenhum formação a realização dos testes.
- Útil para identificar erros mais visíveis aos usuários finais.
- A qualidade do teste dependerá da qualidade dos requisitos. 



