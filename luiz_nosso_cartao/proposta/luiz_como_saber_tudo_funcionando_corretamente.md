métrica

qual métrica exportar?

Métricas de infraestrutura, como por exemplo: CPU, memória, rede, etc.
Métricas de negócio, como por exemplo: Quantidade de usuário, compras, vendas, conversão, etc

RED
(Request) Rate: nº de solicitações que o serviço está atendendo
(Request) Errors: nº de solicitações com falha por segundo
(Request) Duration: distribuições da quantidade de tempo que cada solicitação leva

USE
Utilization: A média de tempo que o recurso está sendo utilizado.
Saturation: O grau em que o recurso tem trabalho extra que não pode atender.
Error: Quantidade de falhas no recurso.


Micrometer - biblioteca de métricas de aplicativos
Prometheus - sistema de monitoramento

NAME é o nome da métrica, como por exemplo: proposta_criadas_total
LABEL é utilizado para diferenciar as características da métrica:
proposta_criadas_total{aplicacao="serviço de proposta", ambiente="desenvolvimento"}

Métrica tipo Counter - conta quantas vezes um método foi chamado
Métrica tipo Timer - medir latência de curta duração e frequência de eventos



Chamar uma classe que realiza métricas seria um aumento de complexidade?



