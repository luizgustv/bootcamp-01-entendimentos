Afim de apresentar que ocorreu um erro ao usuário de uma forma mais clara, realizei o seguinte procedimento:

O erro a ser tratado se referente a por exemplo, quando alguma informação não foi preenchida, ou digitada na quantidade e 
formato inválido, que atráves das annotations do BeanValidation que colocamos sobre os atributos queremos detectar.
Quando uma informação recebida na requisição marcada com @Valid é inválida, é lançada a excessão MethodArgumentNotValidException
que possui as informações sobre o que ocorreu.

Dito isso para capturar esse erro e personalizado, foi feito o seguinte:
- Uma classe chamada ErrorResponse com os atributos:
mensagem, código, status, nome do objeto e uma lista de erros do tipo ErrorObject que tem os atributos mensagem, campo e parâmetro.
- A classe CapturaExceptionHandler que extende uma outra denominada ResponseEntityExceptionHandler (classe que oferece métodos
para de forma centralizada tratar excessões, devolvendo como resposta um ResponseEntity). Sobrescrevi um método chamado 
handleMethodArgumentNotValid que recebe objeto do tipo MethodArgumentNotValidException como parâmetro. Como dito ele devolve um
ResponseEntiity, agora com um objeto ErroResponse com as informações que quero exibir.
