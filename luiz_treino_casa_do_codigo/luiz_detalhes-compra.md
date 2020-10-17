Para exibir os datalhes da compra, iremos precisar do id, que é por onde cada compra é identificada.

Criei um controller chamado CompraListaController com um método GET que recebe na URL um id da compra a ser buscada. A partir desse dado
é feita uma busca no banco e caso a informação é encontrada a Compra é passada como parâmetro para a classe DetalheCompraResponse e o 
retornoda requisição será um response entity com essa classe com o HTTP Status 200.