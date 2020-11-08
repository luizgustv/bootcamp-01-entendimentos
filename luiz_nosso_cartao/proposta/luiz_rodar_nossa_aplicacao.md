//SQL
spring.datasource.platform= ${DATASOURCE}
spring.datasource.url= ${DATASOURCE_URL}
spring.datasource.username= ${DATASOURCE_USERNAME}
spring.datasource.password= ${DATASOURCE_PASSWORD}

//JPA
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
spring.jpa.properties.hibernate.jdbc.time_zone=UTC
#tempo maximo de execucao de uma query
#spring.jpa.properties.javax.persistence.query.timeout = 50

//FEIGN
host.analise.financeira =${URL_ANALISE_FINANCEIRA}
host.cartao =${URL_CARTAO}
#tempo de espera para as requisições
#feign.client.config.integracoes.read-timeout=100
#tempo maximo para conseguir realizar a conexão
#feign.client.config.integracoes.connect-timeout=100

#Tempo resposta Scheduled
periodo.proposta.cartao= 10000

#para permitir sobrescrever o projeto
spring.main.allow-bean-definition-overriding=true

Para gerar a imagem é preciso gerar um jar do projeto:
mvn clean package

*pra gerar é feito teste na aplicação e não esta reconhecendo variáveis de ambiente

FROM openjdk:11
ARG JAR_FILE=target/<seu_projeto>.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]

Criar .jar:
mvn clean package

Criar imagem:
docker image build -t zupacademy/proposta:latest .

Rodar imagem:
docker container run -d -p 8080:8080 zupacademy/proposta --name proposta
