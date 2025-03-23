# Documentação de Testes de API

## 1. Descrição dos Testes Manuais

Esta documentação descreve como realizar testes manuais para validar os endpoints da API utilizando as collections do Postman.

# Documentação de Testes de API

## 1. Descrição dos Testes Manuais

Esta documentação descreve como realizar testes manuais para validar os endpoints da API utilizando as collections do Postman.

---

## **Usuário**

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
       "endereco": "Rua Exemplo, 123",
       "tipo": "DONO DE RESTAURANTE/CLIENTE"
     }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se a resposta retorna o status `201 Created`.
     - Certifique-se de que o corpo da resposta contém os dados do usuário recém-criado.

### **2. Atualizar Dados do Usuário (PUT /usuarios/{id})**

- **Objetivo**: Verificar se é possível atualizar os dados de um usuário existente.

- **Passos**:
  1. Selecione o método `PUT` no Postman.
  2. Insira a URL do endpoint substituindo `{id}` pelo ID do usuário que você deseja atualizar:  
     `http://localhost:8080/usuarios/{id}`
  3. No corpo da requisição, selecione o tipo `JSON` e insira os novos dados do usuário:
     ```json
     {
       "nome": "Novo Nome",
       "email": "novoemail@exemplo.com",
       "login": "novousuario123",
       "endereco": "Rua Exemplo, 456",
       "tipo": "DONO DE RESTAURANTE/CLIENTE"
     }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - Certifique-se de que os dados retornados correspondem aos dados atualizados.

### **3. Alterar Senha do Usuário (POST /usuarios/alterar-senha/{id})**

- **Objetivo**: Verificar se é possível alterar a senha de um usuário.

- **Passos**:
  1. Selecione o método `POST` no Postman.
  2. Insira a URL do endpoint substituindo `{id}` pelo ID do usuário:  
     `http://localhost:8080/usuarios/alterar-senha/{id}`
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
     - Certifique-se de que a senha foi alterada corretamente.

### **4. Validar Login do Usuário (POST /usuarios/validar-login)**

- **Objetivo**: Verificar se o login de um usuário está funcionando corretamente.

- **Passos**:
  1. Selecione o método `POST` no Postman.
  2. Insira a URL do endpoint:  
     `http://localhost:8080/usuarios/validar-login`
  3. No corpo da requisição, selecione o tipo `JSON` e insira `login` e `senha`:
     ```json
     {
       "login": "usuario123",
       "senha": "senha123"
     }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - A resposta deve indicar que o login foi bem-sucedido.

### **5. Deletar Usuário (DELETE /usuarios/{id})**

- **Objetivo**: Verificar se é possível excluir um usuário pelo ID.

- **Passos**:
  1. Selecione o método `DELETE` no Postman.
  2. Insira a URL do endpoint substituindo `{id}` pelo ID do usuário que você deseja excluir:  
     `http://localhost:8080/usuarios/{id}`
  3. Clique em **Send**.
  4. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - A resposta deve conter uma mensagem indicando que o usuário foi deletado com sucesso.

---

## **Restaurante**

### **1. Cadastro de Restaurante (POST /restaurantes)**

- **Objetivo**: Verificar se é possível cadastrar um novo restaurante.

- **Passos**:
  1. Selecione o método `POST` no Postman.
  2. Insira a URL do endpoint:  
     `http://localhost:8080/restaurantes`
  3. No corpo da requisição, insira os dados do restaurante:
     ```json
     {
      "nomeRestaurante": "Restaurante 01",
      "enderecoRestaurante": "Rua das Flores, 123, São Paulo, SP",
      "tipoCozinha": "Mexicano",
      "horarioFuncionamento": "12:00 - 22:00",
      "idDonoRestaurante": 1
      }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se o status da resposta é `201 Created`.

### **2. Atualizar Restaurante (PUT /restaurantes/{id})**

- **Objetivo**: Verificar se é possível atualizar os dados de um restaurante existente.

- **Passos**:
  1. Selecione o método `PUT` no Postman.
  2. Insira a URL do endpoint substituindo `{id}` pelo ID do restaurante:  
     `http://localhost:8080/restaurantes/{id}`
  3. No corpo da requisição, insira os novos dados do restaurante:
     ```json
     {
      "nomeRestaurante": "Restaurante Emerson",
      "enderecoRestaurante": "Rua das Flores, 123, São Paulo, SP",
      "tipoCozinha": "Brasileiro",
      "horarioFuncionamento": "12:00 - 22:00",
      "idDonoRestaurante": 1
      }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se o status da resposta é `200 OK`.

### **3. Listar Todos os Restaurantes (GET /restaurantes)**

- **Objetivo**: Obter a lista completa de restaurantes cadastrados.

- **Passos**:
  1. Selecione o método `GET` no Postman.
  2. Insira a URL do endpoint:  
     `http://localhost:8080/restaurantes`
  3. Clique em **Send**.
  4. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - A resposta deve conter um array de objetos representando os restaurantes cadastrados, incluindo informações como nome, endereço, tipo de cozinha, horário de funcionamento e ID do dono.

### **4. Deletar Restaurante (DELETE /restaurantes/deletar/{idRestaurante})**

- **Objetivo**: Excluir um restaurante pelo ID.

- **Passos**:
  1. Selecione o método `DELETE` no Postman.
  2. Insira a URL do endpoint substituindo `{idRestaurante}` pelo ID do restaurante que você deseja excluir:  
     `http://localhost:8080/restaurantes/deletar/{idRestaurante}`
  3. Clique em **Send**.
  4. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - A resposta deve conter uma mensagem indicando que o restaurante foi deletado com sucesso, como:  
       ```json
       {
         "mensagem": "Restaurante deletado com sucesso"
       }
       ```
       
---

## **Cardápio**

### **1. Cadastro de Item do Cardápio (POST /cardapio)**

- **Objetivo**: Verificar se é possível cadastrar um novo item no cardápio.

- **Passos**:
  1. Selecione o método `POST` no Postman.
  2. Insira a URL do endpoint:  
     `http://localhost:8080/cardapio`
  3. No corpo da requisição, insira os dados do item:
     ```json
     {
      "nome": "Pizza de Calabresa",
      "descricao": "Pizza de calabresa com cebola",
      "preco": 49.90,
      "disponibilidadeConsumo": "LIVRE",
      "caminhoImagem": "caminho aleatorio"
      }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se o status da resposta é `201 Created`.

### **2. Atualizar Item do Cardápio (PUT /cardapio/{id})**

- **Objetivo**: Verificar se é possível atualizar os dados de um item existente no cardápio.

- **Passos**:
  1. Selecione o método `PUT` no Postman.
  2. Insira a URL do endpoint substituindo `{id}` pelo ID do item:  
     `http://localhost:8080/cardapio/{id}`
  3. No corpo da requisição, insira os novos dados do item:
     ```json
     {
      "nome": "Pizza de Calabresa",
      "descricao": "Pizza com calabresa, cebola e queijo mussarela",
      "preco": 45.90,
      "disponibilidadeConsumo": "LIVRE",
      "caminhoImagem": "caminho aleatorio"
      }
     ```
  4. Clique em **Send**.
  5. **Validação**:
     - Verifique se o status da resposta é `200 OK`.

### **3. Listar Todos os Cardápios (GET /cardapios)**

- **Objetivo**: Obter a lista completa de cardápios cadastrados.

- **Passos**:
  1. Selecione o método `GET` no Postman.
  2. Insira a URL do endpoint:  
     `http://localhost:8080/cardapios`
  3. Clique em **Send**.
  4. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - A resposta deve conter um array de objetos representando os cardápios cadastrados, incluindo informações como ID, descrição e ID do restaurante associado.

### **4. Deletar Cardápio (DELETE /cardapios/deletar/{idCardapio})**

- **Objetivo**: Excluir um cardápio pelo ID.

- **Passos**:
  1. Selecione o método `DELETE` no Postman.
  2. Insira a URL do endpoint substituindo `{idCardapio}` pelo ID do cardápio que você deseja excluir:  
     `http://localhost:8080/cardapios/deletar/{idCardapio}`
  3. Clique em **Send**.
  4. **Validação**:
     - Verifique se o status da resposta é `200 OK`.
     - A resposta deve conter uma mensagem indicando que o cardápio foi deletado com sucesso, como:  
       ```json
       {
         "mensagem": "Cardápio deletado com sucesso"
       }
       ```
--

## 2. Link para a Collection do Postman

Para testar a API, importe a collection do Postman usando o link abaixo:

[Link para a Collection do Postman](https://github.com/Emersoaresj/collections-PosTech/blob/main/RestauranTech.postman_collection.json)
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
