Proposta:

documento (CPF ou CNPJ) - obrigatório e válido
email - obrigatório e válido
nome - obrigatório
endereço - obrigatório
salario bruto - obrigatório (positivo)

identificacao gerada pelo sistema
201 - header location
400 - quando houver violacao das restrições

-- cpf / cnpj nao esta validando certo (o cpf permite propositalmente se for com número igual)
-- ver oq tem q ser unico no banco (documento e email) - não é solicitado entao dexa por enquanto

-caso a nova proposta tenha o mesmo documento da outra é necessário emitir um http status 422 (UNPROCESSABLE_ENTITY)
UNPROCESSABLE_ENTITY

-feito classe documentoExiste que busca no banco pelo documento
- é anotado como @Component para ser possível instancia-lo pelo construtor
- o retorno caso exista é um response entity com stauts 422. (Como seria o front a apresentar o resultado, optei por so lançar o status
ao invés da exceção). Possivelmente colocar um logger na operação.

video dock - 16:08

-- testes
utilizar o Mockito
- oq testar:
formato do documento
documento é válido (cpf ou cnpj)
se o documento ja existe no banco
salvar o documento

ver sobre mockito


