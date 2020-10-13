Seguindo as tarefas, uma delas se refere a livros. Deve-se criar um novo livro, exibir uma lista dos livros, e um em específico.

Inicialmente segui a mesma estrutura dos anteriores:
Classe Livro com @Entity e os atributos. Segundo as especificações, o cadastro só é feito se o Autor e a Categoria existir no banco,
então como o cadastro é feito só com o ID dos mesmos, fiz outra custom annotation (@ExistID) para verificar essa informação;

A Classe NovoLivroRequest para receber os dados da requisição. Fiz um método chamado toModel do tipo Livro que recebe uma
instância do tipo EntityMananger para seja possível buscar um Autor e Categoria no banco com base no seu ID com o método 
.find(Class.clss, Object Primary Key) e devolve as informações do Livro.

E o Controller LivroController
