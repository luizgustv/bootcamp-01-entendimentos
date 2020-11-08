Determinadas funções do ecommerce só devem possíveis ser realizadas quando há um usuário logado e autenticado, que são todas menos a criação de novo usuário e a visualização dos produtos.

Para fazer isso:

- SecurityConfiguration: classe que extende WebSecurityConfigurerAdapter. Com isso podemos reescrever alguns métodos, entre eles:
  - configure(HttpSecurity http): aqui utilizo o objeto http para invocar métodos que realizam diversas configurações, entre elas quais requisições serão atendidas, de quais tipos (GET, POST, por exemplo), como serão atendidas (autenticação ou não), filtros de autenticação (criei a classe JwtAutheticationFilter para isso), entre outras configurações;
 ```
 http
                .authorizeRequests()
                    .antMatchers(HttpMethod.GET, "/produtos/{id:[0-9]+}").permitAll()
                    .antMatchers(HttpMethod.POST, "/usuarios").permitAll()
                    .antMatchers("/api/auth/**").permitAll()
                    .anyRequest().authenticated()
                .and()
                    .cors()
                .and()
                    .csrf().disable()
                .sessionManagement()
                    .sessionCreationPolicy(SessionCreationPolicy.STATELESS)
                .and()
                    .addFilterBefore(new JwtAutheticationFilter(tokenManager, userService),
                            UsernamePasswordAuthenticationFilter.class)
                .exceptionHandling()
                    .authenticationEntryPoint(new JwtAuthenticationEntryPoint());
 ```
 
 - JwtAutheticationFilter: classe extende OncePerRequestFilter, onde rescrevo o método doFilterInternal. A ideia é que quando um usuário for acessar um recurso, este deve estar cadastrado e autenticado. Para essa última parte foi utilizado o padrão Token JWT.

Token JWT: é um padrão de mercado que define como transmitir objetos JSON de forma compacta e segura entre diferentes aplicações.
Essecialmente é formado por três sessões: Header, Paylaod e Signature. No final será formato um token com esses elementos separados
por um ponto (ex: token).

https://www.treinaweb.com.br/blog/implementando-autenticacao-baseada-em-jwt-em-uma-api-restful-jax-rs/
https://swagger.io/docs/specification/authentication/bearer-authentication/

Para a autenticação, criei a controller UserAuthenticationController que com o usuário e senha, gera o token.
