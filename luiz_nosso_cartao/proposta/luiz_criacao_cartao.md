620.840.350-23
01.358.316/0001-12
399.259.580-32
334.610.420-64

/api/cartoes/{id} -> busca pelo numero do cartao gerado
cartao id -> 38a311e1-04d9-4b69-b58b-e203926ed86f
idProposta -> 7c5e637c-2495-45f3-b411-ca40327395be

@EnableScheduling

/api/cartoes?idProposta=... -> busca pelo numero da proposta (chamado de idProposta)

Boa tarde Luran, será que poderia me ajudar com outra questão?
No caso, gostaria de entender o processo da proposta com o cartão (a tarefa 025.criacao_cartao.md):
- eu crio a prosposta;
- para gerar o cartão no legado, eu devo digitar as informações das prospostas e criar (sem ser na minha aplicação, 
usando o navegador ou o POSTMAN, por exemplo pela URL http://localhost:8888/api/cartoes). 
Para simular que não tem um tempo certo que isso ocorreria.
- ai feito isso, eu criaria um método para verificar se o cartao foi criado e geraria um cartao com as 
infos do legado pela minha aplicacao


a cada 10 verficar as propostas, caso existam elegíveis, gerar um cartao

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
Esse são os dados gerados recebidos 




