A fim de verificar se o email de um autor prestes a ser cadastrado é válido, fiz uso de uma custom annotation,
onde a configurei para capturar o campo digitado e realizar uma busca no banco para saber se o dado já existe no mesmo.

Para validar uma informação é utilzado uma especificação Java chamada Jakarta Bean Validation (exemplos de annotations: @NotNull, 
@NotBlank, @Email...). 

Seguindo tal especificação tive que criar uma criei uma interface de nome UniqueValue (essa interface deve ser escrita com @interface) 
e definir os atributos message (mensagem que irá aparecer ao usuário final em caso de erro), groups e payload. 

Na interface definir as annotations:
@Documented
@Constraint(validatedBy = {UniqueValueValidator.class}) - qual classe irá ser chamada para validar o dado
@Target({FIELD}) - a validação será feita no campo de dado a ser inserido
@Retention(RUNTIME) - a validação ocorrerá em tempo de execução

Defini dois atributos do tipo String nomeDoCampo e um do tipo Classe nomeDaClasse;

Como dito a classe que efetivamente fará a validação será a UniqueValueValidator. Esta deve implementar a interface ConstraintValidator
e utlizar seus métodos que são initialize (que recebe um objeto do tipo UniqueValue, e pode inicializar atributos) e isValid (que recebe
o dado a validar um contexto que retorna, e um bolean para indicar se a operação é válida ou não). Nesse ultimo metodo é feita uma busca
no banco pelo campo email e armazenada em um objeto do tipo Query. Aí com a combinação dos métodos query.getResultList().isEmpty 
é devolvido um boolean.



