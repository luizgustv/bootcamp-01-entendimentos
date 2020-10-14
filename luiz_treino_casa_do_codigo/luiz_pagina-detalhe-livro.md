Para a exbição de um livro específico e suas informações:
No caso é solicitado que apenas alguma informações sejam exbidas, de acordo com o que é apresentado no site Casa do código:
titulo, resumo, sumário, preço, número de páginas, isbn, nome do autor e descrição sobre o autor.

Para tal foi feito o seguinte:

- Uma classe chamada DetalheLivroResponse, atribuindo as informações citadas do livro e com um atributo do tipo DetalheAutorResponse, esta 
que é uma classe que possui as informações citadas do autor (nome do autor e descrição sobre o autor).
A necessidade por criar essa duas classe se dá por não ser necessário exibir todas os dados que a entidade Livro possui e 
para não permitir que a mesma exiba dados diretamente (através do seus gets que serão necessário para que o Jackson os exiba em formato
JSON), seguindo o princípio de proteger a todo custo as "Bordas" da aplicação;

- utilizei o LivroListaController com outro método GET que nesse caso, através de um id do livro será exibida suas informações. 
Para insesir essa informação, optei por recebe-la diretamente na URL e para fazer isso é necessário que o endereço da requisição 
tenha a seguinte estrutura:
localhost:8080/{"nome do campo a receber o dado"}, e a annotation @PathVariable("nome do campo") a esquerda do campo que receberá 
a informação.
Em seguida realizei uma busca no banco de acordo com a entidade e o id do livro com o método .find(Class.class, Obejct Primary Key).
Esse método pode devolver um resultado nulo então nesse caso restou apenas verificar o nulo e retorna HTTP status 404 e caso exista
exibir o dado.



