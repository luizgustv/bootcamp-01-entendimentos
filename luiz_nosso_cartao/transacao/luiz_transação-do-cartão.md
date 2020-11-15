
http://localhost:16686/search jaeger	

Kafka

 - tópico: stream de evento, informações de uma transação;
 - partição: um tópico pode ser constituído por uma ou mais pertições. Isso permite a redundância e escabilidade, 
pois cada partição pode estar em um broker (máquina) diferente;
 - produtor: envia os eventos para o tópico determinado;
 - consumidor: processar os eventos de um determinado tópico.

um evento possui:
nome do topico
corpo do evento (geralmente em JSON)
chave (opcional)

retry: confirmação de recuperação das mensagens

Failed to construct kafka consumer
StringSerializer is not an instance of Deserializer