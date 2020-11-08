<h2>Cadastro categoria:</h2>

No cadastro de categoria, como dito, uma categoria pode não ter nenhuma relação mas se tiver, esta deve estar no banco.

Para atingir o objetivo, realizei o seguinte:

- CategoriaController: para receber a requisição POST;
- NovaCategoriaRequest: objeto que recebe os dados da requisição;
- Categoria: será a entidade. Como e os dados de NovaCategoriaRequest serão convertidos em um objeto do tipo Categoria. Para isso em NovaCategoriaRequest possui um método que recebe um objeto do tipo EntityManager para buscar uma categoria com base no id. Uma categoria pode ter um nome e sua "mãe" (o atributo foi chamado de categoriaMae), sendo esta um dado opicional. Como ela pode ser nula, utilizo o Optional para verificar isso, e caso exista realizo uma busca no banco e preencho a categoria com o dado encontrado e retorno o objeto.
Para representar essa relação na tabela, o atributo categoriaMae é do tipo Categoria, anotado com @ManyToOne. Essa forma quando a tabela for gerada, heverá como coluna o seu id, nome e categoriaMae.
Dessa forma, ao buscar uma categoria, será possível ver as outras que estão relacionadas.

