avisar sistema legado para bloquear o cartão

- Identificador do cartão é obrigatório.
essa identificação seria a do sistema legado, que no caso é o nosso numero do cartão.

Cartao status:
BLOQUEADO;
ATIVO

tentativa de bloqueio:

- registrar tentativa - ok
- consultar api externa
- ver status http, caso 200 mudar estado do cartao
- caso outro não alterar 

@RequestParam: para query parameters (ex: localhost/api/cartoes?id=01)
@PathVariables: para dados passados na URI como: localhost/api/cartoes/01, comumente ocorre em serviços REST

sistemaResponsavel - o que seria essa informação? - uma informação simples que classifica a aplicação
