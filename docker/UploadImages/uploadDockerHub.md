# BOOTCAMP DEAL - Realizando o Upload de Imagens para o Docker Hub

## Processo de Upload de Imagens para o Docker Hub

### 1. **Login no Docker Hub**

- **Comando Executado:**
    ```bash
    docker login
    ```
- **Descrição:**
    - O comando solicita o **username** e a **senha** para autenticar o usuário no Docker Hub. É possível usar uma senha ou um Personal Access Token (PAT).
    - **Exemplo de entrada:**
        - Username: `seu username do docker hub`
        - Password: `sua senha do docker hub`
    - **Resultado:**
        - Login Succeeded (Login bem-sucedido).

---

### 2. **Construção da Imagem Docker**

- **Comando Executado:**
    ```bash
    docker build . -t username-docker/nome-da-imagem
    ```
- **Descrição:**
    - Este comando cria uma imagem Docker a partir de um Dockerfile no diretório atual, atribuindo-lhe a tag `username-docker/nome-da-imagem`.
    - O processo de build é detalhado com etapas como:
        - Carregamento do Dockerfile.
        - Cópia de arquivos e configuração do ambiente de execução.
        - Execução de comandos, como a compilação da aplicação Go.
    - **Resultado:**
        - A imagem é criada com sucesso e está listada como `username-docker/nome-da-imagem` com o ID da imagem gerado.

---

### 3. **Listagem de Imagens Docker**

- **Comando Executado:**
    ```bash
    docker images
    ```
- **Descrição:**
    - Este comando lista todas as imagens Docker disponíveis localmente.
    - **Resultado:**
        - Exibe a nova imagem `username-docker/nome-da-imagem` com a tag `1.0`, além de outras imagens previamente existentes.

---

### 4. **Upload da Imagem para o Docker Hub**

- **Comando Executado:**
    ```bash
    docker push username-docker/nome-da-imagem
    ```
- **Descrição:**
    - O comando envia a imagem `username-docker/nome-da-imagem` para o Docker Hub.
    - O upload é feito em várias partes, com referências a camadas (layers) da imagem.
    - **Resultado:**
        - As camadas da imagem são enviadas com sucesso, e o digest final da imagem é exibido.
