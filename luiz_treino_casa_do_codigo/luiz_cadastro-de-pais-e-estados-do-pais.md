Para o cadastro de país e estados:

Seguindo o que foi pedido, cada país tem um nome e cada estado, quando cadastrado, tem um nome e pertence a um país.

- Criei a classe País com id e nome (verificando se já existe um país com o mesmo nome com minha annotation @UniqueValue) 
e sobre sobrescrevi os métodos equals e hash code para que fosse usado o nome do país como parâmetro de comparação 
(isso será usado e explicado melhor nas futuras tarefas);
- NovoPaisRequest para receber as informações e passa-las para a entidade Pais;
- PaisController para cadastrar um novo País no banco.

Para o cadastro de estados:
- Criei a classe Estado com id, nome (com @UniqueValue) e um objeto do tipo Pais com a annotation @ManyToOne + @NotNull. 
Com isso estamos criando um relacionamento de 1-1, onde um Pais PODE ter um Estado, e um Estado DEVE TER um Pais. Como consequência 
do mapeamento objeto relacional, no banco será criada um FK (Foreign Key) de Pais. Também foi criado um método chamado 
pertenceAoPais(Pais pais) que retorna um bolean para comparar se um pais é igual a outro e dessa forma verificar se o Estado pertence
a um determinado Pais.
- NovoEstadoRequest para receber as informações e passa-las para a entidade Estado;
- EstadoController para cadastrar um novo Estado no banco.