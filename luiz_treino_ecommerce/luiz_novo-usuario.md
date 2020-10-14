Deve - se criar um novo usuário:
Foram criadas as classes:
- Usuario com os atributos id, login (formato email), senha e instante de criação (localdatetime);
- NovoUsuarioRequest para receber os dados referente a entidade Usuario;
- e UsuarioController para permitir o recebimento de requisições.

A senha ao ser recebida deve ser encriptada com um algoritmo hash

Existem vários diponíveis, até onde pesquisei os mais "seguros" (afinal, nenhum algoritmo é impassível de ser quebrado)
são PBKDF2, BCrypt, and SCrypt.

https://medium.com/@Lunes_Pt/criptografia-como-funciona-pt-2-bd315391b2db
https://www.baeldung.com/java-password-hashing

Para essa situação, optei pelo BCrypt, que é um dos mais utilizados atualmente e é de fácil implementação.

O algoritmo BCrypt, não tem implementação nativa no Java, então é necessário baixar sua dependência.
No caso o projeto Spring Security já o possui.

Por segurança o Spring Security irá solicitar um acesso autorizado ao tentar acessar qualquer url.
Inicialmente optei por permitir acesso total, e para tal, criei a classe SecurityConfig com a annotation 
@EnableWebSecurity (dizendo que essa é uma classe de configuração de segurança web),
extendendo a classe WebSecurityConfigurerAdapter para poder reescrever o seu metodo configure da seguinte forma:
     		http.csrf().disable() //desabilitando a protecao csrf
                .authorizeRequests() //autoriza requisições
                .anyRequest().permitAll() //permite todas as requisições
                .and()
                .httpBasic(); //autenticação basica http



