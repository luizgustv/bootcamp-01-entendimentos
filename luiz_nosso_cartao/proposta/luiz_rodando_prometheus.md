
Tracer tracer;
      Span activeSpan = tracer.activeSpan();
        activeSpan.setTag("user.email", "luiz.gustavo@zup.com.br");
        activeSpan.setBaggageItem("user.email", "luiz.gustavo@zup.com.br");
        activeSpan.log("Meu log");


localhost:9090 - não estou conseguindo visualizar as métricas da minha aplicação.
