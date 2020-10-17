Para o cadastro de cupom de desconto:

- Classe Cupom, com os atributos id, nome do cupom, percentual de desconto e data de validade.
O percentual de desconto é do tipo BigDecimal (a tranformação em um valor a ser calculado como porcentagem é feito apenas quando
o cupom é aplicado).
- NovoCupomRequest: para receber os dados da requisição e converter esse objeto em um do tipo Cupom;
- CupomController: com um método POST para receber as requisições e salvar o cupom no banco.