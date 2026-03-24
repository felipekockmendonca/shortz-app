# Plano de Teste - Shortz-App

## 1. Identificação
- **Projeto:** Shortz-App
- **Versão:** 1.0 (Módulo de Usuários e Autenticação)
- **Grupo:** Felipe Kock Mendonça, Matheus Tonolli, Arthur Barp
- **Data de criação:** 10/03/2026
- **Objetivo:** O objetivo do plano é efetuar uma documentação com base nos testes que iremos efetuar no sistema do Shortz-App

## 2. Escopo

### O que será testado
- Tela de Cadastro
- Tela de Login
- Envio de Vídeos
- Sistema dos Vídeos
- Acesso ao BD
### O que não será testado (nesta fase)
- [Feature fora do escopo]

## 3. Estratégia

### Niveis de Teste
**Unitários:** 
- 1. Verificação se o nome do usuário é valido.
- 2. Rejeita nome de usuário com menos de 3 caracteres.
- 3. Rejeita nome de usuário com mais de 20 caracteres.
- 4. Rejeita nome com caractere inválido.
- 5. Verifica se o Email está em formato válido.
- 6. Rejeita email sem domínio válido.
- 7. Deve aceitar senha forte.
- 8. Rejeita senha com menos de 8 caracteres.
- 9. Rejeita senha com letra maiúscula.
- 10. Rejeita senha sem número.

**Integração:** [rotas/endpoints a testar com Supertest]
- Ainda não enconstramos testes de integração.

### Ferramentas
- Vitest, 
- Supertest, 
- c8/coverage, 
- GitHub Actions

## 4. Riscos Identificados

| ID | Descrição do Risco | Sistema de Referência | Categoria | Probabilidade | Impacto | Prioridade |
|----|--------------------|----------------------|-----------|--------------|---------|-----------|
| R1 | Falha na validação de cadastro permitindo usuários duplicados | Facebook | Funcional | Alta | Crítico | Crítica |
| R2 | Erro no sistema de autenticação permitindo login com credenciais inválidas | Yahoo Voices | Funcional | Alta | Crítico | Crítica |
| R3 | Upload de vídeo aceitar arquivos acima do limite permitido | Gmail | Funcional | Alta | Alta | Alta |
| R4 | Falha no processamento de vídeo impedindo exibição no feed | App de Vídeos | Não-Funcional (Usabilidade) | Alta | Alta | Alta |
| R5 | Erro no sistema de likes causando contagem incorreta | App de Redes Sociais | Negócio / Reputacional | Alta | Média | Média |
| R6 | Falha no algoritmo de feed mostrando conteúdo incorreto | App de Redes Sociais | Negócio / Reputacional | Alta | Média | Média |
| R7 | Sistema de busca retornar resultados incorretos | Sites de Pesquisa | Negócio / Reputacional | Alta | Crítico | Crítica |
| R8 | Falha no sistema de comentários permitindo conteúdo inválido | Instagram | Funcional | Alta | Crítico | Crítica |
| R9 | Usuário acessar dados privados de outro usuário | App de Redes Sociais | Funcional | Alta | Crítico | Crítica |
| R10 | Sistema não suportar muitos usuários simultâneos | App de Redes Sociais | Não-Funcional (Desempenho) | Alta | Crítico | Crítica |

## 5. Recursos e Ambiente
- **Ambiente:** Node.js 20+, MySQL local, Vitest + Supertest
**Dados de teste:** [seeds / fixtures planejados]
**CI:** GitHub Actions (npm test em cada push)

## 6. Cronograma

| Semana | Atividade | Entrega |
|--------|-----------|---------|
| 4      | Protótipo do Plano (esta aula) | plano-de-teste.md |
| 5      | Casos de teste manuais | tests/manuais/casos-de-teste.md |
| 6      | Plano de Teste finalizado | Entrega 1 |

## 7. Critérios de Entrada e Saída
- **Entrada:** Ambiente configurado + migration ok + build passando
- **Saída:** Cobertura >= 70% + zero falhas em riscos Críticos/Altos
- **Suspensão:** Falha grave no ambiente que impede execução de testes