O usuário do cartão pode realizar o bloqueio do cartão por alguma suspeita de fraude.

- informar o identificar do cartão (PK). Deve ser informado na URL

armazenar
- PK do cartao
- instante do bloqueio
- IP do cliente que fez a requisição
- User Agent do client que fez a requisição

resultado:
- armazenar o bloqueio no sistema. Cada bloqueio deve ter um ID.
- 201 com Header Location
- 400 caso ocorra alguma violação
- 404 caso o cartão não seja encontrado


/api/cartoes/pkDoCartao/bloqueios/pkDoBloqueio


User Agent: é uma cadeia de caracteres característica que permite servidores e pares de rede identificar a aplicação, 
sistema operacional, fornecedor, e/ou versão do agente de usuário requisitante.
Com o método getRemoteAddr() é possível obter o IP do client que fez a requisição.

validar bloqueio?
- id
- data
- ua
- ip?

Verificar se o bloqueio foi feito pelo usuario do cartão
- @AuthenticationPrincipal - capturar informações de um usuário logado. No caso utilizar com a classe JWT para conseguir visualizar suas
claims

usar o email como identificação unica do usuário que criou a proposta
Tratar a exceção IllegalArgumentException (422, quebra da regra de negócio?)

Usar 412 - PRECONDITION_FAILED?	

HEADER LOCATION:
http://localhost:8080/api/cartoes/a1f687ff-1e9e-40c8-af0d-e3162d4e174d/bloqueios/b3af315a-2e6c-4b37-8dd1-91d47e7eece4

