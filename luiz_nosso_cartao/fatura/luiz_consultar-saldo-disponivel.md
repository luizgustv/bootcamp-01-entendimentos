Buscar o limite disponível para utilização do cartão.

 - Gerar o cartão (criar uma nova proposta que o cartão será gerado);
 - Pesquisar o cartão no sistema legado;
 - pegar o valor limite.

Spring 2.4
Load Balancer Feign Client - ao realizar a operação de consulta a uma API externa.
Não sei exatamente o problema mas após utilizar uma versão anterios não tive mais o problema

luiz@email.com
num cartao: 9428-7865-7221-4384

gustavo@email.com
num cartâo: 3675-8664-1999-3314]


é preciso saber o valor total da fatura e o limite do cartão
apresentar saldo disponível

O limite varia?
precisa salvar no banco?

fatura consolidada? no caso ao realizar a consultar só apresento o resultado naquele momento, sem necessariamente salva-lo,
juntamente com o limite e o saldo disponível. Apresentar as últimas dez consultas.

Query utilizada:
select f from Fatura f join fetch f.transacoes t where f.cartao.numeroCartao =:numero 
and mes =:mes and ano =:ano 
order by t.efetivadaEm desc



