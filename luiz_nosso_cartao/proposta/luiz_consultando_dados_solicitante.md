{
	documento
	nome
	idProposta
}

consultar serviço externo
se retornar COM_RESTRICAO atualizar proposta com NAO_ELEGIVEL (cpf começa com digito 3)
se retornar SEM_RESTRICAO atualizar proposta com ELEGIVEL (cpf começa qualquer outro numero)

usar OpenFeign para consulta o serviço

controlar tempo de resposata:
feign.client.config.nomeFeignClienteDefinidoNoBean.read-timeout=100
feign.client.config.nomeFeignClienteDefinidoNoBean.connect-timeout=100
spring.jpa.properties.javax.persistence.query.timeout = 50

configuração das aplicações em variáveris de ambiente
ex: cartoes.host=${CARTOES_URL}


PropostaController
crio a prosposta
acessar o servico esterno(proposta) -> resultado
atualiza proposta(resultado)

AvaliarProposta
implementa integracao
acessa o servico
colocar resultado em uma proposta

RespostaStatusAvaliacao
COM_RESTRICAO SEM_RESTRICAO 

StatusAvaliacaoProposta
ELEGIVEL NAO_ELEGIVEL
normaliza com o servico externo

Integracoes OpenFeign
url, nome

CPF para testar com restrição:
352.888.620-01
399.259.580-32
334.610.420-64

Pode ocorrer problema com um fluxo onde uma transação está aberta e várias operações de banco estão ocorrendo. É recomendado
abir/fechar transação a cada operação feita.

Criar classe para transações com o banco de dados.
Generalizar com Objects? pode ocorrer um ClassCastException?
Usar generics?

TransacionTemplate do Spring:
para cada transação deveria ser usado seu metodo execute(), onde passaria uma função como argumento (que seria o entity manager)
o que aumentaria em 1 os pontos de complexidade.

Com uma classe que realiza as operações, essas operações se tornam transversais a aplicação (passíveis de reutilização).







