Para cadastrar uma categoria não fiz muito difente do cadastro de autor:
 - Uma classe categoria anotada como @Entity com um id e nome e seus getters;
 - Outra classe chamada NovaCategoriaRequest para receber os dados externos. Aqui utilizei a minha anotação customizada UniqueValue
para verificar se o mesmo nome de categoria já existe no banco de dados;
 - E um Controller (Categoria Controller) com um método POST para salvar a informação no banco. Em caso de sucesso ele devolve
o status HTTP 201, que se refere a quando um novo recurso é criado.


