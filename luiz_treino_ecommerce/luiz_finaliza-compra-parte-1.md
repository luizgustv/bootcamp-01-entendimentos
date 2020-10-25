Compra{
	produto escolhido (pedir ID)
	quantidade
	gateway de pagamento (Pagseguro ou PayPal)
}

Resultado Compra:{
	id da compra
	produto
	quantidade
	comprador
	gateway de pagamento
	status: iniciada
}

Efeitos:
- abater do estoque (se estoque = 0, não vender)
- enviar email para comprador (só envia se a compra for efetuada, ou msm se der erro mandar tb?)

uriComponentsBuilder.buildAndExpand("/times/{id}",
                        time.getId()).toUri()).build();

uriComponentsBuilder
		.path("/retorno-pagseguro/{id}")
		.buildAndExpand(compra.getId()).toString();


perguntas:
- só envia se a compra for efetuada, ou msm se der erro mandar tb?

Uso de Enum:
 - casos de elementos de tamanho finito;
 - são classes de implementam Enum;
 - podem ter atributos e métodos;
 - caso tenha um método abstrato, os elementos terão que implementa-lo


https://docs.oracle.com/javase/tutorial/java/javaOO/enum.html
https://codereview.stackexchange.com/questions/73369/rock-paper-scissors-lizard-spock-game
https://pt.stackoverflow.com/questions/43756/enumera%C3%A7%C3%B5es-podem-conter-m%C3%A9todos


Boa tarde,
------ poderia me tirar uma dúvida?
Sobre o ecommerce (finaliza-compra-parte-1) sobre a parte do retorno do redirecionanmento, 
gostaria de saber sobre o retorno do endpoint da compra. 
Como que seria o retorno? Uma string com a url do redirecionamento? Ou ResponseEntity com o objeto UriComponentsBuilder configurado?

E sobre a parte do email para o vendedor. Nesse caso independente da pessoa ter acessado o pagamento e de fato ter pago pelo produto,
a mensagem deve ser enviada?

https://learning.postman.com/docs/sending-requests/requests/
https://woliveiras.com.br/posts/url-uri-qual-diferenca/

BindingResult - objeto que armazena o resultado de uma validação

BindException - extende Exception e implementa BindResult
Dessa forma é possível criar lançar uma exceção e armazenar em uma objeto do tipo BindResult

