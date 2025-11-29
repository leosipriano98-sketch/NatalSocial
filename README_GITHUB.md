# Amigo Oculto com Controle de IP 🎄

Sistema de sorteio de Amigo Oculto com controle por IP, garantindo que cada pessoa só sorteia uma vez e que não haja duplicação de resultados.

## 📋 Requisitos

- Node.js 18+
- npm ou pnpm
- Banco de dados MySQL/TiDB
- Variáveis de ambiente configuradas

## 🚀 Instalação Local

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/amigo-oculto-ip.git
cd amigo-oculto-ip
```

### 2. Instalar dependências

```bash
pnpm install
```

### 3. Configurar variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:

```env
# Banco de dados
DATABASE_URL=mysql://user:password@localhost:3306/amigo_oculto

# JWT
JWT_SECRET=sua-chave-secreta-aqui

# OAuth
VITE_APP_ID=seu-app-id
OAUTH_SERVER_URL=https://api.manus.im
VITE_OAUTH_PORTAL_URL=https://portal.manus.im

# Proprietário
OWNER_NAME=Seu Nome
OWNER_OPEN_ID=seu-open-id

# APIs
BUILT_IN_FORGE_API_URL=https://api.manus.im
BUILT_IN_FORGE_API_KEY=sua-chave-api
VITE_FRONTEND_FORGE_API_KEY=sua-chave-frontend
VITE_FRONTEND_FORGE_API_URL=https://api.manus.im

# Analytics
VITE_ANALYTICS_ENDPOINT=https://analytics.manus.im
VITE_ANALYTICS_WEBSITE_ID=seu-website-id
```

### 4. Configurar banco de dados

```bash
pnpm db:push
```

### 5. Iniciar servidor de desenvolvimento

```bash
pnpm dev
```

A aplicação estará disponível em `http://localhost:3000`

## 📦 Build para Produção

```bash
pnpm build
pnpm start
```

## 🧪 Testes

```bash
pnpm test
```

## 🌐 Deploy no GitHub Pages (Frontend Estático)

**Nota:** Esta aplicação é full-stack (React + Express + MySQL). Para hospedar no GitHub Pages, você precisará apenas do frontend estático, mas perderá a funcionalidade de backend.

### Opção 1: Deploy no GitHub Pages (Sem Backend)

1. Fazer build apenas do frontend:
```bash
pnpm build
```

2. Fazer push para o GitHub:
```bash
git add .
git commit -m "Deploy no GitHub Pages"
git push origin main
```

3. Ir para Settings → Pages → Source: Deploy from a branch → Branch: main → Folder: /dist

### Opção 2: Deploy em Servidor Node.js (Recomendado)

Para manter a funcionalidade completa com backend e banco de dados, recomenda-se usar:

- **Heroku** (com add-on MySQL)
- **Railway** (com MySQL)
- **Render** (com PostgreSQL/MySQL)
- **DigitalOcean** (App Platform ou Droplet)
- **AWS** (EC2 + RDS)

## 🔒 Segurança

- Todas as validações são feitas no servidor
- Cada IP só pode sortear uma vez
- Cada pessoa só é sorteada uma vez
- Ninguém sorteia a si mesmo
- Tokens JWT para autenticação
- HTTPS obrigatório em produção

## 📱 Compatibilidade

- ✅ Android
- ✅ iOS
- ✅ Windows
- ✅ macOS
- ✅ Linux

- ✅ Chrome
- ✅ Firefox
- ✅ Safari
- ✅ Edge

## 🎯 Funcionalidades

- ✅ Sorteio aleatório justo
- ✅ Controle por IP + navegador
- ✅ Validações robustas sem duplicação
- ✅ Armazenamento em banco de dados
- ✅ Interface responsiva mobile-first
- ✅ Compatibilidade cross-browser

## 📊 Estrutura do Projeto

```
amigo-oculto-ip/
├── client/                 # Frontend React
│   ├── src/
│   │   ├── pages/         # Páginas da aplicação
│   │   ├── components/    # Componentes reutilizáveis
│   │   ├── hooks/         # Custom hooks
│   │   └── lib/           # Utilitários
│   └── index.html         # HTML principal
├── server/                 # Backend Express + tRPC
│   ├── routers.ts         # Procedimentos tRPC
│   ├── db.ts              # Funções de banco de dados
│   └── _core/             # Configurações internas
├── drizzle/               # Migrations e schema
│   └── schema.ts          # Definição de tabelas
├── shared/                # Código compartilhado
└── package.json           # Dependências
```

## 🤝 Contribuindo

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

## 📧 Contato

Para dúvidas ou sugestões, entre em contato através das Issues do GitHub.

---

**Desenvolvido com ❤️ para a Natal Social**
