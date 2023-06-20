# Dublês de Testes (Mock)

São componentes instalados no lugar de componentes reais do seu código durante os testes do sistema/funcionalidade. Com o objetivo de isolar uma funcionalidade de outras que também necessitam ser testadas, um dublê costuma ser mais simples do o componente real. Na prática, um Mock pode ser construído manualmente pelo testador ou usado pronto através de código disponibilizado para construção de Mocks por frameworks de teste.

## Tipos de Teste

### Dummy Object

O Objeto Bobo é o mais simples entre eles, já que ele normalmente é usado só para fazer com que uma funcionalidade de fato seja executado. Mais especificamente, criamos um Dummy normalmente quando uma funcionalidade exige um objeto ou valor como parâmetro. O Dummy nunca precisa ser especificamente utilizado no teste, ele só precisa existir na funcionalidade.

### Stub Object

Um Objeto Injetivo não deve só existir na funcionalidade como o Dummy, mas também deve retornar/injetar algum comportamento ou consequência no código. Um ótimo exemplo é um objeto que sempre lança exceções para testar como uma funcionalidade lida com elas.

### Test Spy

Um Espião de Testes nada mais é do que um Stub Object, que registra de forma transparente as interações com o sistema, como chamadas, caracerística e/ou mudanças feitas. Para este registro, um Test Spy pode lidar com chamadas feitas a ele pelo próprio sistema, normalmente através da sobrecarga dos métodos numa classe Espiã que herda a classe com os métodos a serem testados. Os registros do Test Spy deve ser disponibilizado para consulta.


### Mock Object
O Objeto Mock é bastante similar ao Test Spy, mas ao invés de disponibilizar os registros, o Mock Object já irá coletar os registros e compará-los com os resultados esperados, normalmente através de *assertions*. Como os métodos testados costumam ser sobrescritos no Test Spy, é normal que um Mock Object irá lançar a exceção no nome do próprio método testado ao executar a ferramenta de testes. Mock Objects são divididos em **Strict** (Restrito) e **Lenient** (Maleável), aquela aceitando somente as chamadas a comportamentos numa determinada ordem e este aceitando em quaisquer ordem.


### Fake Object
É um objeto construído de forma mais fidedigna ao que o objeto deveria ser, sem ênfase em registrar os comportamentos, entradas e saídas. Um Fake Object costuma ser feito quanto o objeto real ainda não existe ou seu código ainda está parcialmente feito. 
