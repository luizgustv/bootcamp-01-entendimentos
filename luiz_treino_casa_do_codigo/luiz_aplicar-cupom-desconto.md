Agora a próxima tarefa se trata de tendo um cupom, aplica-lo na compra. Ter um cupom e aplicar seu desconto é algo opcional, então
na estrutura haverá um total referente a compra e um total com o desconto aplicado, juntamente com o nome do cupom usado.
Para isso:

- Criei um validador interno para o controller CompraNovaController, chamado de CupomValidoValidator para verificar se o cupom existe no
banco e se está dentro da validade. Para que a cada requisição recebida pelo controller, o validador verifique o cupom, deve-se criar um
método void (com a annotation @InitBinder) no mesmo que receba um objeto do tipo WebDataBinder e usar seu método addValidator para 
adicionar o CupomValidoValidator.

- Classe que recebemos os dados da requisição (NovaCompraController), agora possui um atributo do tipo String chamado codigoCupom. Este 
é utilizado para procurar o nome do cupom que foi recebido na requisição no banco de dados. A procura foi feita criando uma interface 
extendendo outra interface chamada CRUDRepository (esta possui métodos prontos que realizam comandos DML "por de baixo dos panos"). 
É possível também criar métodos que realizam comandos de acordo com os campos disponíveis. No caso, fiz um método chamado getByCodigo() 
do tipo Cupom que recebe uma String que será o código do cupom.

Caso o cupom exista, devemos realizar o total da compra com desconto. Isso é feito com o método aplicarCupom() da classe Compra, que recebe 
um objeto do tipo Cupom. A função dele é iniciar um objeto do Tipo CupomAplicado (Feito para proteger a Entidade Cupom) e realizar o 
cáuculo do total com o desconto.

