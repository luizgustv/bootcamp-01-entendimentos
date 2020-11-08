Deve - se criar um novo usuário:

Foram criadas as classes:
- Usuario com os atributos id, login (formato email), senha e instante de criação (localdatetime);
- NovoUsuarioRequest para receber os dados referente a entidade Usuario;
- e UsuarioController para permitir o recebimento de requisições.

A senha ao ser recebida deve ser encriptada com um algoritmo hash.

Existem vários diponíveis, até onde pesquisei os mais "seguros" (afinal, nenhum algoritmo é impassível de ser quebrado)
são PBKDF2, BCrypt, and SCrypt.

Para essa situação, optei pelo BCrypt, que é um dos mais utilizados atualmente e é de fácil implementação.

O algoritmo BCrypt, não tem implementação nativa no Java, então é necessário baixar sua dependência.
No caso o projeto Spring Security já o possui.

Por segurança o Spring Security irá solicitar um acesso autorizado ao tentar acessar qualquer url.
Inicialmente optei por permitir acesso total, e para tal, criei a classe SecurityConfig com a annotation 
@EnableWebSecurity (dizendo que essa é uma classe de configuração de segurança web),
extendendo a classe WebSecurityConfigurerAdapter para poder reescrever o seu metodo configure da seguinte forma:

```
http.csrf().disable() //desabilitando a protecao csrf
.authorizeRequests() //autoriza requisições
.anyRequest().permitAll() //permite todas as requisições
.and()
.httpBasic(); //autenticação basica http
```

Opcionalmente para que as configurações nem sejam iniciadas, podemos no arquivo main onde temos a annotation @SpringBootApplication
colocar a opção: 
```
@SpringBootApplication(exclude = {SecurityAutoConfiguration.class});
```
Dessa forma, quando a aplicação for iniciada essa classe de configuração não será executada.

Obs.: @SpringBootApplication é uma annotation que é equivalente ao uso dessa outras três em suas configurações padrão:
 - @Configuration: usado para classes que contêm métodos anotados com @Bean. Dessa forma o Spring sabe que deverá gerenciar o ciclo de 
vida do objeto gerado pelo retorno desses métodos, e dessa forma, permitir que outras classes o utilizem como depedência. 
Assim, é possível utilizar um objeto sem uma construção como:

```
Objeto obj = new Objeto();
```

E sim:

```
@Autowired
Objeto obj;
```

 - @ComponentScan: procura por Componentes Spring (@Configuration, @Controller,@Services, entre outros);
 - @EnableAutoConfiguration: permite que o Spring configure automaticamente o projeto com base nas dependências jar adicionadas. 
Por exemplo, se o projeto possui a dependência spring-starter-web, o Spring irá auto-configurar o Tomcat e o Spring MVC.
