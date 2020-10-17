Criei um validador genérico atráves de um custom anotation para que pudesse
utilizar em diversas classes onde fosse necessário. Visto que saber se um campo era único no banco é uma necessidade recorente
nas tarefas apresentadas.
- A annotation que cumpre essa função foi chamada de ValorUnico;
- Também houve casos onde é preciso verificar se o dado se existe no banco, e se existir permite o cadastro. Nesse caso criei outra
annotation chamada Existe Valor.

Para os dois casos estou solicitando o nome da classe e o nome do campo. Essas informações serão usadas para seralizar uma query de 
consulta.