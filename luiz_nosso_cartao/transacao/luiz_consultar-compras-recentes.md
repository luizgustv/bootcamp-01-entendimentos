ultimas compras do cartao - a api de transação gerar uma possível compra de forma aleatória

- escutar os eventos enviados para o tópico transações
- salvar no banco

- infoTransacaoCartao: entity
- e estabelecimento e cartao (classes)? : anotar com embadable para juntar suas colunas com a infoTransacaoCartao

- buscar a informação para cada identificação do cartão

Criação de classes:

model:
infoTransacaoCartao
estabelecimento
cartao

request:
infoTransacaoCartao
estabelecimento
cartao

response:
infoTransacaoCartao
estabelecimento
cartao

service
consultar as transações no banco
e fazer uma lista com o resultado para exibir

select i form InfoTransacaoCartao i where i.cartao.id =:value

