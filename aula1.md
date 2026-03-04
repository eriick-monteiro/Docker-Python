# O que é o Docker?
O Docker é um programa que gerencia um ecossistema para isolar aplicações. Ele permite que você execute suas aplicações em ambientes separados do seu sistema operacional principal, chamados de contêineres.
Os contêineres são ambientes isolados que possuem suas próprias configurações e são orientados a tarefas, existindo apenas para rodar a aplicação. Se a aplicação parar, o contêiner entra em estado de parada, mas não "morre".
O principal objetivo do Docker é fornecer uma infraestrutura que permite configurar um ambiente específico para a aplicação, que não dependa da máquina hospedeira. Isso significa que as configurações do seu sistema operacional (como Python ou banco de dados) não afetam a aplicação dentro do contêiner.

---

# Benefícios do Docker
### Isolamento
As aplicações rodam em ambientes isolados, evitando conflitos de dependências.

### Portabilidade
Um ambiente configurado com Docker pode ser facilmente replicado em qualquer máquina que tenha Docker instalado.

### Orquestração
Com ferramentas como o Docker Compose, é possível levantar todo um ecossistema de aplicações de forma simples, sem precisar configurar a máquina hospedeira para cada aplicação.

Foco na aplicação: Diferente de máquinas virtuais, que focam no sistema operacional completo, o Docker é otimizado para atender as necessidades específicas das aplicações. Ele abstrai a complexidade do sistema operacional para a aplicação.
As imagens são arquivos que descrevem como cada contêiner será configurado. O Docker usa essas imagens para criar os contêineres e garantir que as configurações desejadas sejam aplicadas.

---

# Como Docker se difere da VM?
O vídeo explica que o Docker e as Máquinas Virtuais (VMs) são usados para isolar aplicações, mas se diferenciam em sua abordagem e propósito principal:

### Máquinas Virtuais (VMs)

Levantam um sistema operacional completo. Têm como propósito principal o sistema operacional em si, incluindo elementos visuais, diretórios e drivers de som, que muitas vezes são desnecessários para a aplicação.
Embora existam versões mínimas de VMs, o propósito delas ainda é o sistema operacional. A máquina virtual tem uma certa "resistência" para atender à aplicação, pois seu foco é o SO.

### Docker (Contêineres):

O propósito principal é a aplicação. Existe para atender às especificações necessárias das aplicações de forma mais direta. Todo o sistema operacional que roda dentro de um contêiner existe justamente para atender à aplicação. Permite abstrair toda a complexidade que o sistema operacional traz para a gente.

---

# Comandos Utilizados no Vídeo

```bash
docker ps
```

Este comando lista os contêineres que estão em execução. Ele exibe informações como os nomes dos contêineres, as portas de comunicação e suas identidades.

```bash
docker exec -it bash
```

Este comando permite executar um comando dentro de um contêiner já em execução e interagir com ele. No vídeo, o comando bash é usado para entrar no terminal do contêiner, permitindo a execução de comandos como `ls`.
