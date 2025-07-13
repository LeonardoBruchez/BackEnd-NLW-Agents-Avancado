# NLW Agents

Projeto desenvolvido durante o evento **NLW (Next Level Week)** da Rocketseat, focado em criar uma aplicação de agentes inteligentes utilizando IA.

## 🚀 Tecnologias

### Backend
- **Fastify** - Framework web rápido e eficiente
- **TypeScript** - Linguagem de programação tipada
- **Drizzle ORM** - ORM moderno para TypeScript
- **PostgreSQL** - Banco de dados relacional
- **pgvector** - Extensão para embeddings vetoriais
- **Zod** - Validação de schemas
- **Google Gemini AI** - API de inteligência artificial

### Ferramentas de Desenvolvimento
- **Biome** - Linter e formatter
- **Docker Compose** - Containerização do banco de dados
- **Drizzle Kit** - Ferramentas de migração e seed

## 📋 Pré-requisitos

- Node.js 18+
- Docker e Docker Compose
- Conta no Google AI Studio (para chave da API Gemini)

## ⚙️ Configuração

### 1. Clone o repositório
```bash
git clone <url-do-repositorio>
cd server
```

### 2. Instale as dependências
```bash
npm install
```

### 3. Configure as variáveis de ambiente
Crie um arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
GEMINI_API_KEY=sua_chave_api_aqui
```

### 4. Inicie o banco de dados
```bash
docker-compose up -d
```

### 5. Execute as migrações
```bash
npm run db:generate
npm run db:migrate
```

### 6. Execute o seed (opcional)
```bash
npm run db:seed
```

### 7. Inicie o servidor
```bash
# Desenvolvimento
npm run dev

# Produção
npm start
```

## 🏗️ Estrutura do Projeto

```
src/
├── db/
│   ├── connection.ts
│   ├── migrations/
│   ├── schema/
│   │   ├── rooms.ts
│   │   ├── questions.ts
│   │   ├── audio-chunks.ts
│   │   └── index.ts
│   └── seed.ts
├── http/
│   └── routes/
│       ├── create-room.ts
│       ├── get-rooms.ts
│       ├── create-question.ts
│       ├── get-room-questions.ts
│       └── upload-audio.ts
├── env.ts
└── server.ts
```

## 📊 Banco de Dados

O projeto utiliza PostgreSQL com a extensão pgvector para suporte a embeddings vetoriais. As principais tabelas são:

- **rooms** - Salas de conversação
- **questions** - Perguntas dos usuários
- **audio_chunks** - Chunks de áudio processados

## 🔧 Scripts Disponíveis

- `npm run dev` - Inicia o servidor em modo desenvolvimento
- `npm start` - Inicia o servidor em modo produção
- `npm run db:generate` - Gera migrações do banco
- `npm run db:migrate` - Executa migrações pendentes
- `npm run db:seed` - Popula o banco com dados iniciais

## 🔒 Segurança

⚠️ **Importante**: O arquivo `.env` está no `.gitignore`, mas certifique-se de nunca commitar suas chaves de API. Se você já fez commit acidentalmente, considere rotacionar suas chaves imediatamente.

## 📝 Licença

Este projeto foi desenvolvido durante o evento NLW da Rocketseat. 