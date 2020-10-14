Para a criação de um novo livro:

Inicialmente segui a mesma estrutura dos anteriores:
 - Classe Livro com @Entity e os atributos. Segundo as especificações, o cadastro só é feito se o Autor e a Categoria existir no banco,
então como o cadastro é feito só com o ID dos mesmos, fiz outra custom annotation (@ExistID) para verificar essa informação.
Em resumo, @ExistID irá verificar se o campo existe no banco e se a resposta for sim, ele valida como true e permite o cadastro.

 - A Classe NovoLivroRequest para receber os dados da requisição. Aqui, além das informações do livro, só será solicitado que se informe
o id relacionado ao autor e a categoria.Fiz um método chamado toModel do tipo Livro que recebe uma
instância do tipo EntityMananger para seja possível buscar um Autor e Categoria no banco com base no seu ID com o método 
.find(Class.clss, Object Primary Key) e devolve essa e as outras informações do Livro.

E o Controller LivroCadastroController para especificamente realizar a operação POST e salvar o livro, e retornar HTTP status 201
em caso de sucesso.

