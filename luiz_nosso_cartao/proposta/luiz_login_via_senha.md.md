Keycloak - permite login unico para suas aplicacoes
Criar um Realm - irá permitir por colocar permissões de acesso

Username: Luiz
email: luiz@email.com
password: luiz@email.com

https://www.digitalocean.com/community/tutorials/uma-introducao-ao-oauth-2-pt

dependencias necessárias:
spring-boot-starter-oauth2-resource-server
spring-security-oauth2-jose

OAuth2
proprietário do recurso - usuário que permite uma aplicação usar sua conta
cliente - é a aplicação que quer acessar a conta do usuário
servidor do recurso - hospeda as contas de usuário protegidas
servidor de autorização - verifica a identidade do usuário e emite token de acesso a aplicação

- não estou conseguindo utilizar os parâmetros ("SCOPE_propostas:read") 
o read/write, está dando 403 forbidden
Resp: é uma configuração de sintaxe para as requisições configuradas (não é obrigatório)

Em Authorization: Bearer (schema de autenticação HTTP, identifica os recursos protegidos por um OAuth2) + token

grant_type : client_credentials
client_id : minha-aplicacao
client_secret : 029f9635-84ad-4e6a-a659-83c4f5874317

com usuario e senha:
client_id
client_secret
grant_type: password
username
password

criar token com um so scope. Ao gerar um token ele assume todos relacionados ao seu realm