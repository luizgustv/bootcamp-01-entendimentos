Realizar a inclusão do nosso cartão na carteira digital Paypal.

id do cartão na URL

email - obrigatório
carteira: Paypal

feing
numero do cartao
email - obrigatório
carteira: Paypal

devolver
resultado: ASSOCIADA
id: numero do cartao

resultado - guardar
id da carteira
email
nome carteira
cartao

O mesmo cartão não pode ser associado na mesma carteira digital.
Ao consultar o sistema legado com o mesmo email é retornado um erro 500. Possivelmente ele ve se o email já foi associado;
Nesse caso ignorar o erro e salvar no banco se for de outra carteira mesmo assim?
ver a lista de carteiras dos cartões e ver se já foi associado a determinada carteira. Se for não adiantar, caso não, realizar
a consulta no servidor legado e caso não tenham havido uma exceção, adicionar a nova carteira.






