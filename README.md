# 🚀 Sistema de Gestão de Usuários

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Docker](https://img.shields.io/badge/docker-ready-blue)
![Java](https://img.shields.io/badge/Java-17-orange)
![React](https://img.shields.io/badge/React-18-blue)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-blue)

> **Status do Projeto: 🏗️ Estrutura Inicial**  
> Projeto em fase de implementação. Estrutura de containers disponível, código em desenvolvimento.

## 📋 Sobre o Projeto

Sistema web full stack para **gestão, autenticação e controle de acesso de usuários**, desenvolvido com arquitetura de microsserviços containerizados.

### 🎯 Propósito
- Gerenciar cadastros de usuários
- Controlar autenticação e autorização por perfis
- Fornecer interface administrativa e de usuário comum
- Garantir rastreabilidade de ações administrativas

## 🛠️ Stack Tecnológica

| Camada | Tecnologia | Versão |
|--------|------------|--------|
| **Backend** | Java Spring Boot | 3.x |
| **Frontend** | React | 18.x |
| **Database** | PostgreSQL | 15.x |
| **Container** | Docker | 24.x |
| **Orquestração** | Docker Compose | 2.x |

## 📁 Estrutura do Projeto

```
projeto-docker-java-react/
├── backend/               # API REST em Java Spring Boot
│   ├── src/              # Código fonte
│   └── Dockerfile        # Container do backend
├── frontend/             # Interface React
│   ├── src/             # Componentes e páginas
│   └── Dockerfile       # Container do frontend
├── database/            # Scripts e configurações do banco
│   └── init.sql        # Schema inicial (em breve)
├── docker-compose.yml   # Orquestração dos containers
└── README.md           # Documentação principal
```

## ⚙️ Regras de Negócio Implementadas

### ✅ Concluídas
- Nenhuma (projeto em estruturação)

### 🚧 Em Desenvolvimento
- `RN01` – Cadastro de usuário
- `RN02` – Email como identificador único
- `RN03` – Validação de credenciais
- `RN04` – Perfis Administrador e Usuário

### 📌 Planejadas
- `RN05` – Restrição por perfil
- `RN06` – Controle de sessão
- `RN07` – Logout
- `RN08` – Integridade de dados
- `RN09` – Auditoria de ações

## 🚀 Como Executar

### Pré-requisitos
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- Git

### Passo a passo

1. **Clone o repositório**
   ```bash
   git clone https://github.com/gameturk13/projeto-docker-java-react.git
   cd projeto-docker-java-react
   ```

2. **Configure as variáveis de ambiente**
   ```bash
   cp .env.example .env
   # Edite o arquivo .env com suas configurações
   ```

3. **Execute com Docker Compose**
   ```bash
   docker-compose up -d
   ```

4. **Acesse a aplicação**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8080
   - Banco de dados: localhost:5432

5. **Parar os containers**
   ```bash
   docker-compose down
   ```

## 🔌 Endpoints da API (Previstos)

| Método | Rota | Descrição | Acesso |
|--------|------|-----------|---------|
| POST | `/api/auth/login` | Autenticação | Público |
| POST | `/api/auth/register` | Cadastro | Público |
| GET | `/api/usuarios` | Listar usuários | Admin |
| GET | `/api/usuarios/{id}` | Buscar usuário | Admin/Proprietário |
| PUT | `/api/usuarios/{id}` | Atualizar | Admin/Proprietário |
| DELETE | `/api/usuarios/{id}` | Remover | Admin |

## 🗄️ Modelo de Dados (Previsto)

```sql
-- Estrutura inicial do banco (em breve)
CREATE TABLE usuarios (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    senha VARCHAR(255) NOT NULL,
    perfil VARCHAR(20) DEFAULT 'USUARIO',
    created_at TIMESTAMP DEFAULT NOW()
);
```

## 🔐 Segurança

- ✅ Autenticação via JWT (planejado)
- ✅ Senhas hasheadas com BCrypt (planejado)
- ✅ Rotas protegidas por perfil (planejado)
- ✅ Volumes Docker para persistência (implementado)

## 📊 Roadmap

### Fase 1 - Fundação (Fev/Mar 2026)
- [x] Estrutura de containers
- [x] Docker compose configurado
- [ ] README finalizado
- [ ] Primeiro endpoint funcional

### Fase 2 - Backend (Mar 2026)
- [ ] CRUD de usuários
- [ ] Autenticação JWT
- [ ] Perfis de acesso
- [ ] Testes unitários

### Fase 3 - Frontend (Abr 2026)
- [ ] Tela de login
- [ ] Cadastro de usuários
- [ ] Painel administrativo
- [ ] Consumo da API

### Fase 4 - Entrega (Mai 2026)
- [ ] Documentação completa
- [ ] Auditoria de ações
- [ ] Deploy em produção

## 🤝 Contribuição

Este é um projeto de estudo e portfólio. Sugestões são bem-vindas!

1. Faça um fork
2. Crie uma branch (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT.

---

**Desenvolvido por [gameturk13](https://github.com/gameturk13)**  
📧 Contato: *[seu-email]*  
🐙 GitHub: [https://github.com/gameturk13/projeto-docker-java-react](https://github.com/gameturk13/projeto-docker-java-react)

---

⭐ **Se este projeto te ajudou, considere dar uma estrela!**
