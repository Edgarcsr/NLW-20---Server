# NLW Agents - Server

<p align="center">
<img src="https://img.shields.io/badge/Projeto-NLW%20Agents%20Server-green?style=for-the-badge&logo=node.js&logoColor=white" />
<img src="https://img.shields.io/badge/Evento-Rocketseat-blueviolet?style=for-the-badge&logo=rocket&logoColor=white" />
</p>

Backend da aplicação **NLW Agents** desenvolvido durante um evento da **Rocketseat**. O projeto utiliza Node.js com TypeScript, Fastify como framework web e PostgreSQL com extensão pgvector como banco de dados.

## 🧩 Tecnologias Utilizadas

### Backend

- **Node.js** - Runtime JavaScript
- **TypeScript** - Tipagem estática para JavaScript
- **Fastify** - Framework web rápido e eficiente
- **Zod** - Validação de schemas TypeScript-first

### Banco de Dados

- **PostgreSQL** - Banco de dados relacional
- **pgvector** - Extensão para armazenamento de embeddings/vetores
- **Drizzle ORM** - ORM TypeScript-first para SQL
- **Drizzle Kit** - CLI para migrações do banco

### DevOps & Ferramentas

- **Docker** - Containerização do banco de dados
- **Biome** - Linter e formatter para JavaScript/TypeScript

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── connection.ts     # Configuração da conexão com o banco
│   ├── seed.ts          # Scripts de seed do banco
│   ├── migrations/      # Migrações do banco de dados
│   └── schema/          # Schemas do Drizzle ORM
├── http/
│   └── routes/          # Rotas da API
├── env.ts              # Validação de variáveis de ambiente
└── server.ts           # Configuração do servidor Fastify
```

## 🚀 Setup e Configuração

### Pré-requisitos

- Node.js (versão 18 ou superior)
- Docker e Docker Compose
- PostgreSQL (caso não use Docker)

### 1. Instalação das Dependências

```bash
npm install
```

### 2. Configuração do Banco de Dados

#### Usando Docker (Recomendado)

```bash
# Subir o container PostgreSQL com pgvector
docker-compose up -d
```

#### Configuração Manual

Se preferir usar PostgreSQL local, certifique-se de instalar a extensão `pgvector`.

### 3. Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

### 4. Executar Migrações

```bash
# Gerar migrações (se necessário)
npx drizzle-kit generate

# Aplicar migrações
npx drizzle-kit migrate
```

### 5. Seed do Banco (Opcional)

```bash
npm run db:seed
```

### 6. Executar o Servidor

#### Desenvolvimento

```bash
npm run dev
```

#### Produção

```bash
npm start
```

O servidor estará disponível em `http://localhost:3333`

## 📋 Scripts Disponíveis

- `npm run dev` - Executa o servidor em modo desenvolvimento com watch
- `npm start` - Executa o servidor em modo produção
- `npm run db:seed` - Executa o seed do banco de dados

## 🔗 Endpoints

### Health Check

```
GET /health
```

### Rooms

```
GET /rooms
```

---

Desenvolvido durante o evento **NLW Agents** da [Rocketseat](https://rocketseat.com.br) 🚀
