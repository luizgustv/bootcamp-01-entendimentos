Na primeira parte do fluxo de pagamento é solicitado que se obtenha certas informações do cliente mas que isso não
fará como que haja um cadastro de clientes, tendo o mesmo que a toda compra informa-las.

Foram solicitadas as seguintes informações:
email, nome, sobrenome, documento(cpf/cnpj), endereco, complemento, cidade, país, estado(caso aquele pais tenha estado), telefone e cep.

- Criei uma classe chamada Compra com os atributos acima. 
Para o Estado não utilizei a annotation @NotNull já que, diferente do Pais não é uma informação obrigatória.
Nos atributos telefone e cep, utilizei expressões regulares para garantir o formato correto do dado que será salvo no banco.
Para o cpf e o cnpj, optei por definir um atributo único chamado documento para receber uma das duas informações e criei uma custom 
annotation chamada @CpfOuCnpj para diferenciar e validar o documento recebido.

A annotation @CpfOuCnpj utiliza duas classes disponíveis na api do Hibernate Validator: CPFValidator e CNPJValidator.
Estas possuem um método chamado isValid() que recebe uma sequência de caracteres e devolve um Boolean representando se o formato,
e o digito verificador dos documentos é válido.

- NovaCompraRequest, para receber os valores correspondente a Compra.

- CompraNovaController que possui um método do tipo POST para criar uma nova compra, nesse caso não salvando por enquanto.


