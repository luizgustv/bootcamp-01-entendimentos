Biometria

Um cartão pode ter uma ou mais biometrias

entrada
- identificador do cartão (seria o a PK ou o número do cartão obtido pelo sitema externo?)
- fingerprint da biometria (imagem já vem em base64)

resultado
- cadastro biometria
- data da criacao da biometria deve ser armazenada

Biometria:
- numero do cartao - String, obrigatorio
- foto do dedo - em BASE64, verificar se a digital é uma BASE64 válida (ver o seus caracteres, 
não necessariamente o que pode ser gerado)

nome do endpoint:
/api/cartoes/numeroDoCartao/biometrias

 //decoderFingerPrint = decoder.decode(arrayFingerPrint);
                        /*ByteArrayInputStream byteArrayInputStream =
                                new ByteArrayInputStream(decoderFingerPrint);
                        image = ImageIO.read(byteArrayInputStream);
                        byteArrayInputStream.close();
                        File file = new File("C:\\Users\\luiz.viana\\Downloads\\image.png");
                        ImageIO.write(image, "png", file);*/


Formato do envio em file? Em base64
Retornar 400 quando a biometria não enviada ou está inválida?
Verficar se a base enviada está correta (se possui os caracteres corretos). Não verifica necessariamente se a informação forma a
imagem correta.

- Utilizei uma custon annotation para validar o Base64. Capturar uma IllegalArgument Exception pelo RestController Advice não estava
funcionado. Solução temporária.

Como vou saber se a imagem saiu correta?

- preciso q cada biometria tenha seu location (com id dele separado) ou posso apresentar para cada cartao a lista de biometrias?
Tratar erro de base64
