# Project TODO - Amigo Oculto com Controle de IP

## Features

- [x] Replicar o código original de sorteio com melhorias
- [x] Ajustar a distância de "Natal Social" para 100px
- [x] Atualizar a lista de nomes (13 participantes)
- [x] Implementar controle de sorteio por IP (impedir múltiplos sorteios do mesmo IP)
- [x] Reduzir o tempo de exibição do nome sorteado para 3 segundos
- [x] Criar schema de banco de dados para armazenar sorteios
- [x] Implementar API tRPC para gerenciar sorteios
- [x] Criar testes vitest para validar funcionalidades
- [x] Testar a aplicação completa

## Otimização Mobile (Android e iOS)

- [x] Otimizar layout para mobile-first
- [x] Adicionar meta tags de viewport
- [x] Otimizar tamanho de fontes para mobile
- [x] Melhorar espaçamento e touch targets
- [x] Otimizar imagens para mobile
- [x] Testar em Android
- [x] Testar em iOS
- [x] Adicionar suporte a notch/safe area
- [x] Otimizar performance para conexões lentas

## Validação de Duplicação e Integridade

- [x] Garantir que não haja duplicação de resultados
- [x] Garantir que cada pessoa só receba uma vez
- [x] Garantir que cada pessoa só entregue uma vez
- [x] Implementar validações robustas no servidor
- [x] Testar cenários de race condition
- [x] Validar integridade dos dados no banco de dados

## Funcionalidade de Compartilhamento

- [ ] Implementar botão de "Compartilhar Link"
- [ ] Adicionar suporte a Web Share API
- [ ] Adicionar fallback para copiar link
- [ ] Testar em diferentes navegadores
- [ ] Testar em dispositivos móveis

## Nova Funcionalidade - Sistema de Votação

- [x] Atualizar schema do banco de dados para tabela de votos
- [x] Criar procedimentos tRPC para votação
- [x] Implementar interface visual de votação com lista de participantes
- [x] Adicionar contagem de votos em tempo real
- [x] Exibir ranking de participantes mais votados
- [x] Testar funcionalidade de votação com vitest
- [x] Validar que cada IP só vota uma vez por participante
- [x] Salvar checkpoint com nova funcionalidade

## Correção de Erros - Middleware Express/Vite

- [x] Diagnosticar erro "Unexpected token '<', '<!doctype'" na API tRPC
- [x] Identificar que middleware Vite estava capturando requisições de API
- [x] Corrigir ordem dos middlewares (tRPC antes do Vite)
- [x] Validar que API retorna JSON corretamente
- [x] Testar que todos os 6 testes passam

## Alterações de UI/UX

- [x] Alterar mensagem "Você já realizou seu sorteio" para "Realize aqui o seu sorteio"

## Sistema de Votação com Categorias

- [x] Atualizar schema do banco de dados para adicionar campo de categoria nas votações
- [x] Criar lista de candidatos para "Social do Ano" (10 candidatos)
- [x] Criar lista de candidatos para "Social Revelação" (13 candidatos)
- [x] Implementar procedimentos tRPC para votação por categoria
- [x] Criar interface visual com abas para cada categoria
- [x] Implementar validação: cada IP só vota uma vez por categoria
- [x] Implementar lógica de exibição de resultados com data/hora (6 de Dezembro 2025 12:00)
- [x] Testar votação em ambas as categorias
- [x] Validar que resultados são ocultos até a data especificada
- [x] Salvar checkpoint com novo sistema de votação

## Correção de Erros - Input Validation

- [x] Corrigir erro de validação de input nas queries de votação por categoria
- [x] Corrigir grafia de "social-revelação" para "social-revelacao" em todo o código
- [x] Adicionar vírgula faltante após getCounts no routers.ts

## Limpeza de Dados

- [x] Limpar dados antigos de sorteios e votos do banco de dados
- [x] Resetar contadores de sorteios para novo evento
