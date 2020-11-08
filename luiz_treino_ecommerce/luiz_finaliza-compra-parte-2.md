https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/302

{
	id da compra
	id do gateway de pagamento (um id gerado pelo gateway relacionado a transacao que foi realizada)
	status: paypal: 1 ou 0 / pagseguro: sucesso ou erro
	data instante do processamento
}


erro ou sucesso

transacao
id
compra (fk)
data
idtransacaogateway
status


em caso de SUCESSO:
 - controller nota fiscal (endpoint e tudo):
	{
		id da compra
		id do usuario que fez a compra
	}

 - ranking de vendedores:
fazer um controller
{
	id da compra
	id do vendedor
}


email para comprador informando sucesso no pagamento com infos da compra


em caso de ERRO:
email informando que o pagamento falhou com o link para que a pessoa tente novamente (link de pagamento imagino)


RESULTADO:
- Status 200, retornando o status do pagamento
- Em caso de erro, status 400 com JSON com os erros


Perguntas:

Se trata do desafio do ecommerce (finaliza-compra-parte2):

Sobre a especificação: Uma compra não pode ter mais de duas transações concluídas com sucesso associada a ela. Não entendi esse ponto.  
Não deveria ser uma só? A compra é feita, a pessoa paga, recebe o status de sucesso, operação registrada. Não poderia a partir da mesma compra realizar outra transação.

Sobre identificar as transações, uma comparação através do método equals seria válido? Ou seria melhor procurar por outras soluções?
E sobre usar o método equals: as transações vindas do pagseguro/palpal o que as diferencia individualmente? O id da transação mesmo?

uma explicação de como a interface funciona para encontrar que a implementou e quando foi utilizada
