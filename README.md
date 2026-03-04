# Docker Python
## 🛠️ Tecnologias Utilizadas

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-2.x-000000?logo=flask&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-ORM-D71F00?logo=sqlalchemy&logoColor=white)
![Pre-commit](https://img.shields.io/badge/Pre--commit-Hooks-FAB040?logo=pre-commit&logoColor=white)
![Virtualenv](https://img.shields.io/badge/Env-Virtualenv-4B8BBE?logo=python&logoColor=white)


## 📦 Pré-requisitos

Antes de iniciar, certifique-se de ter instalado:

- Docker
- Python 3.9+
- pip
- virtualenv (ou venv)
- Git (opcional)

## ▶️ Como Executar o Projeto
### 1️⃣ Clonar o repositório

```bash
git clone https://github.com/eriick-monteiro/Docker-Python.git
cd Docker-Python
```

### 2️⃣ Instalando as dependências
#### 🐧 Linux / 🍎 macOS
```bash
$ . install.sh
```

#### 🪟 Windows (PowerShell)

```bash
.\install.ps1
```

#### 🪟 Windows (CMD)
```bash
install.bat
```


---

### 💡 Observação importante

No Linux/macOS, se der erro de permissão, pode ser necessário rodar antes:

```bash
chmod +x install.sh
```

---

### 3️⃣ Criando uma imagem
```bash
$ docker build --tag docker-python .
```

### 4️⃣ Subindo o container à partir da imagem criada
```bash
$ docker run -p 5000:5000 docker-python
```

Acesse no navegador:
```
http://127.0.0.1:5000/
```

### 📁 Estrutura do Projeto
```bash
📦 Docker-Python/
├── 🚫 .dockerignore
├── 🙈 .gitignore
├── 🔧 .pre-commit-config.yaml
├── 🐍 app.py
├── 📝 aula1.md
├── 🐳 Dockerfile
├── ⚙️ install.sh
├── 📦 requirements.txt
└── 📘 README.md
```
