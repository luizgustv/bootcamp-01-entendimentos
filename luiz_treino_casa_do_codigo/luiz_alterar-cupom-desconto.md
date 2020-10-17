Para a alteração do Cupom:

As informações que podem ser alteradas são:

- Data de validade;
- Percentual de desconto;
- Código.

Para alterar as informações de um Cupom, criei um método PUT que solicita na URL o id do cupom,
e alteramos as informações no corpo da requisição. Através do método find(), procuramos pelo cupom a ser alterado pelo id,
e caso não seja nulo, é feito um update das informações com o método merge().
O método merge() funciona com a verificação de uma entidade JPA que está no contexto de persistência. Como buscamos um cupom do banco
sabemos que este está no contexto e dessa forma o merge irá atualizar o estado do objeto com as novas informações passadas e salva-las.