# Documentação de Testes de API

## 1. Descrição dos Testes Manuais

Esta documentação descreve como realizar testes manuais para validar os endpoints da API utilizando as collections do Postman.

### **1. Cadastro de Usuário (POST /cadastrar)**

- **Objetivo**: Verificar se o cadastro de um novo usuário está funcionando corretamente.
  
- **Passos**:
  1. Selecione o método `POST` no Postman.
  2. Insira a URL do endpoint:  
     `http://localhost:8080/cadastrar`
  3. No corpo da requisição, selecione o tipo `JSON` e insira os dados do novo usuário:
     ```json
     {
       "nome": "Nome do Usuário",
       "email": "usuario@exemplo.com",
       "login": "usuario123",
       "senha": "senha123",
       "endereco": "Rua Exemplo, 123"
     }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se a resposta retorna o status `201 Created`.
     - Certifique-se de que o corpo da resposta contém os dados do usuário recém-criado.

### **2. Atualizar Dados do Usuário (PUT /{id})**

- **Objetivo**: Verificar se é possível atualizar os dados de um usuário existente.

- **Passos**:
  1. Selecione o método `PUT` no Postman.
  2. Insira a URL do endpoint substituindo `{id}` pelo ID do usuário que você deseja atualizar:  
     `http://localhost:8080/{id}`
  3. No corpo da requisição, selecione o tipo `JSON` e insira os novos dados do usuário:
     ```json
     {
       "nome": "Novo Nome",
       "email": "novoemail@exemplo.com",
       "login": "novousuario123",
       "endereco": "Rua Exemplo, 456"
     }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - Certifique-se de que os dados retornados correspondem aos dados atualizados.

### **3. Alterar Senha do Usuário (POST /alterar-senha/{id})**

- **Objetivo**: Verificar se é possível alterar a senha de um usuário.

- **Passos**:
  1. Selecione o método `POST` no Postman.
  2. Insira a URL do endpoint substituindo `{id}` pelo ID do usuário:  
     `http://localhost:8080/alterar-senha/{id}`
  3. No corpo da requisição, selecione o tipo `JSON` e insira a senha antiga e a nova senha:
     ```json
     {
       "senhaAntiga": "senha123",
       "novaSenha": "senhaNova123"
     }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - Certifique-se de que a senha foi alterada corretamente, se possível, validando com o login.

### **4. Validar Login do Usuário (POST /validar-login)**

- **Objetivo**: Verificar se o login de um usuário está funcionando corretamente.

- **Passos**:
  1. Selecione o método `POST` no Postman.
  2. Insira a URL do endpoint com os parâmetros `login` e `senha` na query string:
     ```
     http://localhost:8080/validar-login?login=usuario123&senha=senha123
     ```
  3. Clique em **Send**.
  4. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - A resposta deve indicar que o login foi bem-sucedido. Caso contrário, o status pode ser `401 Unauthorized`.

### **5. Deletar Usuário (DELETE /{id})**

- **Objetivo**: Verificar se é possível excluir um usuário pelo ID.

- **Passos**:
  1. Selecione o método `DELETE` no Postman.
  2. Insira a URL do endpoint substituindo `{id}` pelo ID do usuário que você deseja excluir:  
     `http://localhost:8080/{id}`
  3. Clique em **Send**.
  4. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - A resposta deve conter uma mensagem indicando que o usuário foi deletado com sucesso, como um objeto com a mensagem "Usuário deletado com sucesso".

## 2. Link para a Collection do Postman

Para testar a API, importe a collection do Postman usando o link abaixo:

[Link para a Collection do Postman]([https://github.com/usuario/repositorio/arquivo-collection.json](https://github.com/Emersoaresj/collections-PosTech/blob/main/Gerenciamento-Restaurantes.postman_collection.json))

## 3. Executando os Testes

1. **Importando a Collection no Postman**:
   - No Postman, clique em **Import** no canto superior esquerdo.
   - Selecione **Link** e cole o link da collection.
   - Clique em **Import** para adicionar a collection ao seu Postman.
   
2. **Executando as Requisições**:
   - Escolha o endpoint desejado na collection importada.
   - Clique em **Send** para enviar a requisição e validar a resposta.

## 4. Conclusão

Os testes manuais descritos acima podem ser realizados utilizando o Postman para garantir que os endpoints da API estão funcionando corretamente.
