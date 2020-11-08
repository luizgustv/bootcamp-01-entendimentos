620.840.350-23
01.358.316/0001-12
399.259.580-32
334.610.420-64

/api/cartoes/{id} -> busca pelo numero do cartao gerado
cartao id -> 38a311e1-04d9-4b69-b58b-e203926ed86f
idProposta -> 7c5e637c-2495-45f3-b411-ca40327395be

cartao{
id,
emitidoEm,
titular,
bloqueios,
avisos,
carteiras,
parcelas,
limite,
renegociacao,
vencimento{id, dia, dataDeCriacao}
idProposta
}

Esse são os dados gerados recebidos. Mas só é pedido para capturar o numero do cartão e atrelar na proposta

busca da proposta:
- status elegivel
- sem id do idCartao null
opçoes:
fk de cartao em proposta e fk de proposta em cartao

fk de prosposta em cartao, join com tabela proposta (dessa forma não preciso ter uma fk cartao em proposta)

"procurar em proposta onde o id = proposta_id (presente em cartão) onde o 
status avaliacao proposta = ELEGIVEL e o id (chave primaria do cartao) é nulo (que significa proposta que n tiveram um cartao criado)"

https://www.postgresqltutorial.com/postgresql-left-join/



