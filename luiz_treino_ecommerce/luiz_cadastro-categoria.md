Cadastro categoria:

Categoria:
id
nome - obrigatorio e unico
nome categoria mae - opicional e caso tenha deve estar no banco

NovaCategoriaRequest

CategoriaController

self join com @ManyToOne


Before Java 8, programmers would return null instead of Optional. There were a 
few shortcomings with this approach. One was that there wasn’t a clear way to express that null might be a special value. 
By contrast, returning an Optional is a clear statement in the API that there might not be a value in there. 
If we wanted to make sure that we won't get a null pointer exception, then we would need to do explicit null 
check for each reference, as shown below, and we all agree that’s a lot of boilerplate.


Pergunta:
Na categoria do eccomerce, a categoria pode deve ter um nome e pode ter uma categoria mae
No caso, caso a categoria mae n estiver no banco eu devo cadastra-la antes, certo? 
Ou seja cadastrar uma categoria sem categoria mae?

