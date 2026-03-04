## 🐳 1️⃣ Primeiro comando

```bash
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=root -d mysql.latest
```
### O que ele faz:

- `docker run` → cria e inicia um novo container.
- `--name some-mysql` → define o nome do container como some-mysql.
- `-e MYSQL_ROOT_PASSWORD=root` → define uma variável de ambiente dentro do container:
    - Está configurando a senha do usuário root do MySQL como `root`.
- `-d` → roda o container em modo detached (em segundo plano).
- `mysql.latest` → imagem usada para criar o container.

👉 Resumindo:

Cria um container MySQL simples, com senha definida para root, rodando em background.

---

## 🐳 2️⃣ Segundo comando (versão mais completa)

```bash
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=root -p 3306:3306 -v mysqlVolume:/var/lib/mysql -d mysql:latest
```

Essa versão é mais usada em projetos reais.

### O que muda aqui:


- `-p 3306:3306`
    - Faz o mapeamento de portas.
    - Porta **3306 do seu computador** → Porta **3306 do container**.
    - Isso permite conectar no banco pelo `localhost:3306`.
- `-v mysqlVolume:/var/lib/mysql`
    - Cria e usa um volume Docker chamado `mysqlVolume`.
    - Esse volume armazena os dados do banco em `/var/lib/mysql` (onde o MySQL guarda os arquivos).
    - 🔥 Isso evita perder os dados se o container for removido.
- `-e MYSQL_ROOT_PASSWORD=root`
    - Define a senha do root como `root`.

👉 Resumindo:
Esse comando cria um MySQL persistente (com volume) e acessível externamente pela porta 3306.

---

## 🗄 3️⃣ Conectando e executando o schema

```bash
cd init/
```

```bash
docker exec -i CONTAINER_ID mysql -u root -proot <./schema.sql
```

### O que isso faz:

- `cd init/`
    - Entra na pasta onde está o arquivo `schema.sql`.
- `docker exec -i CONTAINER_ID`
    - Executa um comando dentro de um container já rodando.
    - `-i` mantém o modo interativo (permite enviar entrada).
- `mysql -u root -proot`
    - Executa o cliente MySQL dentro do container.
    - -`u root` → usuário root.
    - -`proot` → senha root.
- `<./schema.sql`
    - Redireciona o conteúdo do arquivo `schema.sql` para o MySQL.
    - Ou seja: executa todos os comandos SQL do arquivo no banco.

👉 Em outras palavras:

Ele está importando a estrutura do banco (tabelas, índices, etc.) para dentro do MySQL que está rodando no container.

## 📦 Fluxo completo do que está acontecendo

1. Você sobe um container MySQL.
2. Ele cria o banco com senha definida.
3. Você executa um arquivo SQL dentro dele.
4. O banco fica pronto para a aplicação usar.

