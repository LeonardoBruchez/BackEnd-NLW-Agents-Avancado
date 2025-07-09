# NLW Agents

Projeto desenvolvido durante o evento **NLW (Next Level Week)** da Rocketseat, focado em criar uma aplicação de agentes inteligentes.

## 🚀 Tecnologias

- **Node.js** - Runtime JavaScript
- **TypeScript** - Linguagem de programação
- **Fastify** - Framework web rápido
- **Drizzle ORM** - ORM para PostgreSQL
- **PostgreSQL** - Banco de dados (com pgvector)
- **Zod** - Validação de schemas
- **Docker** - Containerização

## 📋 Pré-requisitos

- Node.js 18+
- Docker e Docker Compose
- Git

## ⚙️ Configuração

1. **Clone o repositório**
```bash
git clone <url-do-repositorio>
cd server
```

2. **Instale as dependências**
```bash
npm install
```

3. **Configure as variáveis de ambiente**
Crie um arquivo `.env` na raiz do projeto:
```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

4. **Inicie o banco de dados**
```bash
docker-compose up -d
```

5. **Execute as migrações**
```bash
npx drizzle-kit push
```

6. **Popule o banco com dados iniciais**
```bash
npm run db:seed
```

## 🏃‍♂️ Executando o projeto

**Desenvolvimento:**
```bash
npm run dev
```

**Produção:**
```bash
npm start
```

O servidor estará disponível em `http://localhost:3333`

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── connection.ts
│   ├── migrations/
│   ├── schema/
│   └── seed.ts
├── http/
│   └── routes/
├── env.ts
└── server.ts
```

## 🛠️ Scripts Disponíveis

- `npm run dev` - Executa em modo desenvolvimento com hot reload
- `npm start` - Executa em modo produção
- `npm run db:seed` - Popula o banco com dados iniciais

## 🔧 Padrões Utilizados

- **TypeScript** para tipagem estática
- **Zod** para validação de schemas
- **Drizzle ORM** para operações de banco
- **Fastify** com plugins para CORS e validação
- **Docker** para containerização do banco
- **Biome** para formatação de código 