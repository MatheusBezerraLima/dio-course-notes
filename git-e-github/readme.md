# Anotações sobre Git e GitHub

## Configuração Inicial

### Definindo Nome e Email

```bash
git config --global user.name "nome"
git config --global user.email email
```

## Verificando a Branch Padrão

```bash
git config init.defaultBranch
```
## Alterando a branch para Main 
```bash
git config --global init.defaultBranch main
```

## Autenticação via Token

### 1° Passo: Clonando o Repositório

```bash
    git clone link-do-repositorio-do-github
```

### 2° Passo: Configurando Credenciais
Caso não tenha as credenciais do GitHub na máquina, insira seu email e senha do GitHub e um token de verificação. Para evitar inserir o token novamente, configure o auxiliar de credencial:

```bash
git config --global credential.helper store  # ou cache para armazenamento temporário
```

### para descobrir a localização do auxiliar: 

```bash 
git config --global --show-origin credential.helper
```