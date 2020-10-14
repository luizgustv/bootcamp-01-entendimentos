Para a exbição de uma Lista com todos os livros:

Criei um controller chamado LivroListaController para exibir a lista de livros.
Com uma instância do entity manager criei uma query select com:
entitymanager.createQuery("select l from Livro l") e atribuindo seu resultado em uma lista com getResultList().

Observação: na declaração do comando sql caso fosse escrito: "select * from livro", não seria reconhecido, então por isso
o uso de uma letra/palavra qualquer. Outro ponto é que deve ser declarado a entidade (classe) Livro e não o nome da tabela no banco.

A resposta será exibida no formato JSON com  HTTP status 200 (requisição foi bem sucedida).


