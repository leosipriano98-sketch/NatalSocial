# 🚀 Guia de Deploy - Amigo Oculto

Este guia fornece instruções detalhadas para hospedar a aplicação Amigo Oculto em diferentes plataformas.

## 📌 Importante

A aplicação é **full-stack** (React + Express + MySQL). Você precisa de:
- Um servidor Node.js
- Um banco de dados MySQL/TiDB
- Variáveis de ambiente configuradas

## 🌐 Opções de Deploy

### 1️⃣ Railway (Recomendado - Mais Fácil)

Railway oferece suporte completo para Node.js + MySQL com deploy automático do GitHub.

#### Passo 1: Criar conta no Railway
1. Acesse [railway.app](https://railway.app)
2. Clique em "Start a New Project"
3. Selecione "Deploy from GitHub repo"

#### Passo 2: Conectar GitHub
1. Autorize Railway a acessar seu GitHub
2. Selecione o repositório `amigo-oculto-ip`

#### Passo 3: Adicionar banco de dados
1. No dashboard do Railway, clique em "Add Service"
2. Selecione "MySQL"
3. Railway criará automaticamente a variável `DATABASE_URL`

#### Passo 4: Configurar variáveis de ambiente
1. Clique em "Variables" no seu projeto
2. Adicione as seguintes variáveis:

```
JWT_SECRET=gere-uma-chave-secreta-aleatoria
VITE_APP_ID=seu-app-id
OAUTH_SERVER_URL=https://api.manus.im
VITE_OAUTH_PORTAL_URL=https://portal.manus.im
OWNER_NAME=Seu Nome
OWNER_OPEN_ID=seu-open-id
BUILT_IN_FORGE_API_URL=https://api.manus.im
BUILT_IN_FORGE_API_KEY=sua-chave-api
VITE_FRONTEND_FORGE_API_KEY=sua-chave-frontend
VITE_FRONTEND_FORGE_API_URL=https://api.manus.im
VITE_ANALYTICS_ENDPOINT=https://analytics.manus.im
VITE_ANALYTICS_WEBSITE_ID=seu-website-id
```

#### Passo 5: Deploy
1. Clique em "Deploy"
2. Railway fará o build e deploy automaticamente
3. Sua aplicação estará disponível em `https://seu-projeto.railway.app`

---

### 2️⃣ Render

Render é outra excelente opção com suporte a Node.js e PostgreSQL/MySQL.

#### Passo 1: Criar conta no Render
1. Acesse [render.com](https://render.com)
2. Clique em "Get Started"
3. Selecione "New Web Service"

#### Passo 2: Conectar GitHub
1. Autorize Render a acessar seu GitHub
2. Selecione o repositório `amigo-oculto-ip`

#### Passo 3: Configurar serviço
1. **Name**: `amigo-oculto`
2. **Environment**: `Node`
3. **Build Command**: `pnpm install && pnpm build`
4. **Start Command**: `pnpm start`
5. **Plan**: Selecione o plano desejado

#### Passo 4: Adicionar banco de dados MySQL
1. Clique em "Create Database"
2. Selecione "MySQL"
3. Configure as credenciais
4. Copie a `DATABASE_URL`

#### Passo 5: Adicionar variáveis de ambiente
1. Na página do serviço, clique em "Environment"
2. Adicione todas as variáveis listadas acima

#### Passo 6: Deploy
1. Clique em "Create Web Service"
2. Render fará o deploy automaticamente

---

### 3️⃣ Heroku (Descontinuado - Não Recomendado)

Heroku descontinuou o plano gratuito. Use Railway ou Render em vez disso.

---

### 4️⃣ DigitalOcean App Platform

DigitalOcean oferece uma solução gerenciada com bom custo-benefício.

#### Passo 1: Criar conta no DigitalOcean
1. Acesse [digitalocean.com](https://digitalocean.com)
2. Clique em "Sign Up"

#### Passo 2: Criar App
1. Clique em "Apps" no menu
2. Clique em "Create Apps"
3. Selecione "GitHub"
4. Autorize e selecione o repositório

#### Passo 3: Configurar
1. **Source**: GitHub repository
2. **Branch**: `main`
3. **Build Command**: `pnpm install && pnpm build`
4. **Run Command**: `pnpm start`

#### Passo 4: Adicionar banco de dados
1. Clique em "Add Component"
2. Selecione "MySQL Database"
3. Configure as credenciais

#### Passo 5: Variáveis de ambiente
1. Clique em "Settings"
2. Adicione todas as variáveis necessárias

#### Passo 6: Deploy
1. Clique em "Create App"
2. DigitalOcean fará o deploy

---

### 5️⃣ AWS (Mais Complexo)

Para usuários avançados que desejam máximo controle.

#### Opção A: Elastic Beanstalk
1. Acesse AWS Console
2. Vá para Elastic Beanstalk
3. Clique em "Create Application"
4. Selecione "Node.js" como plataforma
5. Upload do código ou conecte GitHub
6. Configure RDS para MySQL
7. Adicione variáveis de ambiente
8. Deploy

#### Opção B: EC2 + RDS
1. Crie uma instância EC2 (Ubuntu 22.04)
2. Crie um banco de dados RDS MySQL
3. SSH na instância
4. Clone o repositório
5. Instale Node.js e pnpm
6. Configure variáveis de ambiente
7. Execute `pnpm install && pnpm build && pnpm start`
8. Configure um reverse proxy (Nginx)
9. Configure SSL (Let's Encrypt)

---

## 🔐 Segurança em Produção

### Checklist de Segurança

- [ ] Todas as variáveis de ambiente estão configuradas
- [ ] `JWT_SECRET` é uma string aleatória forte (mínimo 32 caracteres)
- [ ] HTTPS está ativado (todas as plataformas acima suportam)
- [ ] Banco de dados está em rede privada (não exposto à internet)
- [ ] Backups automáticos do banco de dados estão configurados
- [ ] Logs estão sendo monitorados
- [ ] Rate limiting está ativado (se aplicável)

### Gerar JWT_SECRET Seguro

```bash
# No seu terminal local
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

---

## 🔄 Atualizações e Manutenção

### Deploy de Atualizações

1. Faça as mudanças localmente
2. Commit e push para `main`:
```bash
git add .
git commit -m "Descrição das mudanças"
git push origin main
```

3. A plataforma de deploy (Railway, Render, etc.) fará o deploy automaticamente

### Monitorar Logs

**Railway:**
```bash
railway logs
```

**Render:**
- Acesse o dashboard e clique em "Logs"

**DigitalOcean:**
- Acesse o dashboard e clique em "Logs"

---

## 🐛 Troubleshooting

### Erro: "Database connection failed"
- Verifique se `DATABASE_URL` está correto
- Verifique se o banco de dados está rodando
- Verifique se as credenciais estão corretas

### Erro: "Cannot find module"
- Execute `pnpm install`
- Verifique se todas as dependências estão em `package.json`

### Erro: "Port already in use"
- A aplicação tenta usar porta 3000
- Verifique se nenhum outro serviço está usando essa porta

### Aplicação lenta
- Verifique os logs para erros
- Verifique a conexão com o banco de dados
- Considere aumentar os recursos (CPU/RAM)

---

## 📊 Monitoramento

### Recomendações

1. **Logs**: Configure alertas para erros críticos
2. **Performance**: Monitore tempo de resposta das APIs
3. **Banco de dados**: Monitore uso de espaço e conexões
4. **Uptime**: Use um serviço como UptimeRobot

### Ferramentas Recomendadas

- [UptimeRobot](https://uptimerobot.com) - Monitoramento de uptime
- [Sentry](https://sentry.io) - Rastreamento de erros
- [DataDog](https://datadoghq.com) - Monitoramento completo
- [New Relic](https://newrelic.com) - APM

---

## 💡 Dicas

1. **Sempre teste localmente antes de fazer push**
   ```bash
   pnpm dev
   pnpm test
   ```

2. **Use branches para features novas**
   ```bash
   git checkout -b feature/nova-funcionalidade
   ```

3. **Mantenha logs detalhados**
   ```bash
   pnpm build > build.log 2>&1
   ```

4. **Faça backups regulares do banco de dados**

5. **Monitore custos** (especialmente em AWS)

---

## 📞 Suporte

Se encontrar problemas:

1. Verifique os logs da aplicação
2. Consulte a documentação da plataforma
3. Abra uma issue no GitHub
4. Entre em contato com o suporte da plataforma

---

**Boa sorte com seu deploy! 🎉**
