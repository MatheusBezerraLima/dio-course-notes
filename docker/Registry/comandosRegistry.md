# BOOTCAMP DEAL - Gerenciamento de Imagens Docker

## Processo de Gerenciamento de Imagens Docker

### 1. **Executar o Registro do Docker**

- **Comando Executado:**
    ```bash
    docker run -d -p 5000:5000 --restart=always --name registry registry:2
    ```
- **Descrição:**
    - Executa um container Docker para o registro de imagens Docker.
- **Opções:**
    - `-d`: Executa o container em segundo plano (modo detach).
    - `-p 5000:5000`: Mapeia a porta 5000 do host para a porta 5000 do container.
    - `--restart=always`: Reinicia automaticamente o container se ele parar.
    - `--name registry`: Nomeia o container como "registry".
    - `registry:2`: Especifica a imagem a ser usada, neste caso, a versão 2 do registro Docker.

---

### 2. **Listar Imagens Docker**

- **Comando Executado:**
    ```bash
    docker images
    ```
- **Descrição:**
    - Lista todas as imagens disponíveis no sistema local.
- **Saída:**
    - Exibe informações como repositório, tag, ID da imagem, data de criação e tamanho.

---

### 3. **Taggear uma Imagem**

- **Comando Executado:**
    ```bash
    docker image tag 500bbb9986eb localhost:5000/my-go-app:1.0
    ```
- **Descrição:**
    - Cria uma nova tag para a imagem existente, permitindo que ela seja referenciada por outro nome.
- **Uso:**
    - O ID da imagem (neste caso, `500bbb9986eb`) é associado à nova tag `localhost:5000/my-go-app:1.0`.

---

### 4. **Empurrar (Push) uma Imagem para o Registro**

- **Comando Executado:**
    ```bash
    docker push localhost:5000/my-go-app:1.0
    ```
- **Descrição:**
    - Envia a imagem tagueada para o registro Docker que está sendo executado localmente.
- **Saída:**
    - Exibe o status de cada camada da imagem sendo enviada e o digest da imagem após o push.

---

### 5. **Remover uma Imagem**

- **Comando Executado:**
    ```bash
    docker rmi -f 500bbb9986eb
    ```
- **Descrição:**
    - Remove uma ou mais imagens do sistema local.
- **Opções:**
    - `-f`: Força a remoção, mesmo que a imagem esteja em uso por containers.

---

### 6. **Verificar o Registro com cURL**

- **Comando Executado:**
    ```bash
    curl localhost:5000
    ```
- **Descrição:**
    - Tenta acessar a interface do registro local, mas não é o comando ideal para verificar o status do registro.
- **Uso correto:**
    - Para verificar os repositórios disponíveis, utilize:
    ```bash
    curl http://localhost:5000/v2/_catalog
    ```

---

### Resposta de confirmação

- **Comando Executado:**
    ```jsx
    PS C:\Users\mathe> curl http://localhost:5000/v2/_catalog
    ```
- **Saída:**
    ```jsx
    StatusCode        : 200
    StatusDescription : OK
    Content           : {"repositories":["my-go-app"]}
    ```
    ```jsx
    RawContent        : HTTP/1.1 200 OK
    Docker-Distribution-Api-Version: registry/2.0
    X-Content-Type-Options: nosniff
    Content-Length: 31
    Content-Type: application/json; charset=utf-8
    Date: Sat, 02 Nov 2024 00:18:34 GMT...
    Forms             : {}
    Headers           : {[Docker-Distribution-Api-Version, registry/2.0],
    [X-Content-Type-Options, nosniff], [Content-Length,
    31], [Content-Type, application/json;
    charset=utf-8]...}
    Images            : {}
    InputFields       : {}
    Links             : {}
    ParsedHtml        : mshtml.HTMLDocumentClass
    RawContentLength  : 31
    ```

- **Observação:**
    - A linha `Content : {"repositories":["my-go-app"]}` indica que a imagem foi armazenada no servidor local.

---

### Resumo

Esses comandos são fundamentais para gerenciar imagens e containers no Docker, especialmente quando se trata de trabalhar com um registro local. Eles permitem que você armazene, organize e distribua suas imagens de forma eficaz.
