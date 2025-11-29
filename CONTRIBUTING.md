# 🤝 Contribuindo para Amigo Oculto

Obrigado por considerar contribuir para o projeto Amigo Oculto! Este documento fornece diretrizes e instruções para contribuir.

## 📋 Código de Conduta

Este projeto adota um Código de Conduta para garantir um ambiente acolhedor para todos. Esperamos que todos os contribuidores sigam estas diretrizes:

- Seja respeitoso com outros contribuidores
- Aceite críticas construtivas
- Foque no que é melhor para a comunidade
- Mostre empatia com outros membros da comunidade

## 🐛 Reportando Bugs

### Antes de Reportar

- Verifique se o bug já foi reportado nas Issues
- Tente reproduzir o bug em um ambiente limpo
- Colete informações sobre seu ambiente (OS, navegador, versão do Node.js)

### Como Reportar

1. Vá para a aba "Issues"
2. Clique em "New Issue"
3. Use o template de bug report
4. Forneça:
   - Descrição clara do bug
   - Passos para reproduzir
   - Comportamento esperado
   - Comportamento atual
   - Screenshots (se aplicável)
   - Seu ambiente (OS, navegador, versão)

## 💡 Sugerindo Melhorias

1. Use a aba "Issues" e clique em "New Issue"
2. Selecione o template de feature request
3. Descreva claramente:
   - O problema que a feature resolve
   - A solução proposta
   - Alternativas consideradas
   - Contexto adicional

## 🔧 Processo de Desenvolvimento

### 1. Fork o Repositório

```bash
# Clique em "Fork" no GitHub
```

### 2. Clone seu Fork

```bash
git clone https://github.com/seu-usuario/amigo-oculto-ip.git
cd amigo-oculto-ip
```

### 3. Adicione o Repositório Original como Remote

```bash
git remote add upstream https://github.com/usuario-original/amigo-oculto-ip.git
```

### 4. Crie uma Branch para sua Feature

```bash
git checkout -b feature/sua-feature-aqui
# ou para bugfix
git checkout -b bugfix/seu-bug-aqui
```

### 5. Faça suas Mudanças

```bash
# Instale dependências
pnpm install

# Inicie o servidor de desenvolvimento
pnpm dev

# Execute os testes
pnpm test
```

### 6. Commit suas Mudanças

```bash
git add .
git commit -m "Descrição clara das mudanças"
```

**Convenção de Commit:**
- `feat:` para novas features
- `fix:` para bug fixes
- `docs:` para documentação
- `style:` para mudanças de estilo (sem lógica)
- `refactor:` para refatoração de código
- `test:` para testes
- `chore:` para tarefas de manutenção

Exemplo:
```bash
git commit -m "feat: adicionar validação de email"
git commit -m "fix: corrigir erro de sorteio duplicado"
```

### 7. Push para seu Fork

```bash
git push origin feature/sua-feature-aqui
```

### 8. Abra um Pull Request

1. Vá para o repositório original
2. Clique em "Pull Requests"
3. Clique em "New Pull Request"
4. Selecione sua branch
5. Preencha o template de PR
6. Clique em "Create Pull Request"

## 📝 Diretrizes de Código

### Estilo de Código

- Use TypeScript para type safety
- Siga as convenções de nomenclatura:
  - `camelCase` para variáveis e funções
  - `PascalCase` para componentes React
  - `UPPER_SNAKE_CASE` para constantes
- Máximo 100 caracteres por linha
- Use 2 espaços para indentação

### Exemplo de Código Bem Formatado

```typescript
// ✅ Bom
const getUserData = async (userId: string): Promise<User> => {
  const user = await db.query('SELECT * FROM users WHERE id = ?', [userId]);
  return user;
};

// ❌ Ruim
const get_user_data = async (userId: string) => {
  let user = await db.query('SELECT * FROM users WHERE id = ?', [userId])
  return user
}
```

### Testes

- Escreva testes para novas features
- Mantenha cobertura de testes acima de 80%
- Use Vitest para testes unitários

```bash
# Executar testes
pnpm test

# Executar testes com cobertura
pnpm test:coverage

# Executar testes em modo watch
pnpm test:watch
```

### Documentação

- Atualize o README se adicionar features
- Documente funções complexas com comentários
- Use JSDoc para funções públicas

```typescript
/**
 * Calcula o sorteio aleatório
 * @param participants - Array de participantes
 * @returns Nome do participante sorteado
 */
const drawRandomParticipant = (participants: string[]): string => {
  // ...
};
```

## 🔍 Checklist antes de Submeter PR

- [ ] Código segue as diretrizes de estilo
- [ ] Testes foram adicionados/atualizados
- [ ] Todos os testes passam (`pnpm test`)
- [ ] Documentação foi atualizada
- [ ] Sem console.log ou código de debug
- [ ] Commits têm mensagens claras
- [ ] Branch está atualizada com `main`

## 📦 Dependências

Antes de adicionar uma nova dependência:

1. Verifique se já existe uma solução no projeto
2. Considere o tamanho do pacote
3. Verifique a manutenção e popularidade
4. Discuta em uma Issue antes de adicionar

Para adicionar uma dependência:

```bash
pnpm add nome-do-pacote
# ou para dev dependency
pnpm add -D nome-do-pacote
```

## 🚀 Processo de Review

Seu PR será revisado por um mantenedor. Eles podem:

- Solicitar mudanças
- Fazer perguntas
- Sugerir melhorias
- Aprovar e fazer merge

**Dicas para aprovação rápida:**
- PR pequenos e focados são mais fáceis de revisar
- Descrição clara do que foi mudado
- Testes inclusos
- Sem conflitos com `main`

## 📚 Recursos Úteis

- [Documentação do Node.js](https://nodejs.org/docs/)
- [Documentação do React](https://react.dev)
- [Documentação do TypeScript](https://www.typescriptlang.org/docs/)
- [Documentação do tRPC](https://trpc.io/docs)
- [Documentação do Prisma](https://www.prisma.io/docs/)

## 🎯 Áreas onde Ajuda é Bem-vinda

- 🐛 Correção de bugs
- 📝 Melhorias na documentação
- 🎨 Melhorias na UI/UX
- 🧪 Testes adicionais
- 🌐 Suporte a novos idiomas
- ⚡ Otimizações de performance
- 🔒 Melhorias de segurança

## 💬 Dúvidas?

- Abra uma Issue com a tag `question`
- Participe das discussões
- Entre em contato com os mantenedores

## 📄 Licença

Ao contribuir, você concorda que suas contribuições serão licenciadas sob a mesma licença do projeto (MIT).

---

**Obrigado por contribuir! 🙏**
