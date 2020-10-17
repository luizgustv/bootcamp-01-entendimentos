Agora foi solicitado que além dos dados do cliente a compra deve conter o carrinho de compras.
Dessa forma as informações disponíveis ao carrinho são:

{
	Dados do cliente,
	total,
	itens:
	[
	  {
		idlivro,
		quantidade
	  }
	]
}

Para construir o pedido, a seguinte estrutura foi feita:

- A classe Pedido, com os atributos id, total e uma lista do tipo ItemPedido. Este possui o método calcularTotalPedido() que 
calcula o total da compra com base nos item do carrinho;
- Esses itens são atribuidos no ItemPedido que é uma classe que possui os atributos: Objeto do tipo Livro, quantidade, preço do livro.
Possui o sobrescrito os métodos equals e hashCode com base no Objeto Livro e valorTotal(), 
que calcula o preço do item (valor x quantidade);

Para representar isso no banco de dados:
- Em Compra, adicionei um atributo do tipo Pedido com a annotation @OneToOne(cascade = CascadeType.PERSIT).
Com isso estou definindo que o relacionamento de Compra e Pedido é de 1-1 (Uma Compra deve ter um Pedido, e um Pedido deve ter 
associado uma Compra), e com CascadeType.PERSIST, estou definindo que o atributo também será persistido quando compra também for. 
Isso no mapeamento, irá gerar uma Foreign Key com o id do Pedido.

- Em Pedido, o tipo lista do tipo ItemPedido será Set. Esta é uma Collection que não permite que sejam adicionados item iguais (por isso
o equals e hashcode sobrescritos), assim não é preciso criar algum tipo de validação para este caso. Cada item do tipo ItemPedido deve ter 
um id associado ao Pedido para que consigamos busca-lo. Para isso, utilizei a annotation @ElementCollection no atributo. No banco, 
isso irá criar uma outra tabela (se não definido o nome, este será o nome da entidade + nome da coleção), 
com o id da tabela Pedido como Foreign Key.


















