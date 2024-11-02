### O que é um Registry?

Um **registry** (registro) é um serviço que armazena imagens de contêineres Docker. Ele funciona como um repositório onde você pode:

- **Armazenar Imagens**: Guardar várias imagens Docker em um só lugar.
- **Compartilhar Imagens**: Permitir que outras pessoas ou equipes baixem as imagens.
- **Versionar Imagens**: Manter diferentes versões da mesma imagem, facilitando o gerenciamento.

### Exemplo de Caso de Uso

#### Situação: Desenvolvimento de uma Aplicação Web

Imagine que uma equipe está desenvolvendo uma aplicação que possui um front-end (interface do usuário) e um back-end (servidor). Cada parte da aplicação é criada como uma imagem Docker.

1. **Desenvolvimento Local**: Os desenvolvedores criam e testam suas imagens em suas máquinas.
   
2. **Uso do Registry**: A equipe usa um registry, como o Docker Hub, para armazenar suas imagens.

3. **Fazendo Upload**: Um desenvolvedor cria uma imagem para o back-end e a envia para o registry:
   ```bash
   docker push meu-backend:1.0
   
4. **Baixando Imagens**

Outro desenvolvedor, que trabalha no front-end, baixa a imagem do back-end do registry:

```bash
docker pull meu-backend:1.0
```

5. **Implantação**
Quando a equipe está pronta para lançar a aplicação, as imagens são puxadas do registry para o ambiente de produção.


## Vantagens do Uso de um Registry
Consistência: Todos usam as mesmas versões das imagens.
Automação: Facilita a integração em processos de automação de build e implantação.
