Para o cadastro do Autor fiz o seguinte:

- Criei uma classe Autor (marcada com a annotation @Entity, para que a mesma possa ser persistida e através do Hibernate esta e 
os seus atributos sejam transformados em tabela e colunas, respectivamente, no banco) com os atributos de id (com chave primária), 
nome, email, descrição e instante da criação;

- Outra classe chamada NovoAutorRequest sendo que esta, utilizei para receber os valores da requisição
e naõ expor a entidade Autor a receber os dados diretamente. Fiz um método chamado toModel do tipo Autor para retornar um objeto 
do mesmo tipo com os valores recebidos pelo NovoAutorRequest;

- A classe AutorController com a annotation @RestController (combinação de @ResponseBody - indica que o retorno 
do método deve ser associado ao corpo da resposta e 
@Controller - indica que a classe é uma Controller e pode receber requisições) com um método que recebe requisições do tipo POST. 
Para isso, utilizei da annotation @PostMapping.

Como é necessário cadastrar em banco, para salvar fiz uso do Entity Manager para poder gerenciar o contexto da persistência
(preservação do estado dos dados) e salvar o que foi recebido no banco.

Importante reseltar que como utilizei diretamente o Entity Manager é necessário colocar a annotation 
@PersistenceContext (irá associar-lo com o contexto de persistência), que armazena as entidades que estão sendo gerenciadas pelo mesmo. 
Assim como a annotation @Transactional, no método post para indicar que irá haver uma transação de dados.



