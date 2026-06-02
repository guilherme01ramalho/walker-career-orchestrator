# Plano de Implementação: Agente Scout (Busca de Vagas)

## Objetivo
Implementar o agente **Scout** para realizar a busca automatizada de vagas utilizando o `firecrawl` via linha de comando ou fallback para ferramentas nativas, integrando-o ao orquestrador (Walker).

## Etapas do Plano

### 1. Configuração da Skill de Busca (`skills/job-search.md`)
- Definir o protocolo de execução:
  - Tentar `firecrawl search` via CLI.
  - Se falhar, utilizar `firecrawl scrape`.
  - Se ferramentas externas falharem, implementar fallback usando a funcionalidade `webfetch` nativa do agente (acesso web).
- Documentar os passos de processamento: extração de dados, comparação de habilidades com o perfil do usuário e formatação da resposta.

### 2. Criação da Persona do Scout (`personas/scout.md`)
- Definir o comportamento como especialista em recrutamento.
- Estabelecer a obrigatoriedade de seguir o fluxo definido na `skills/job-search.md`.
- Instruir o agente a tratar erros explicitamente, reportando falhas de ferramentas antes de tentar o fallback.

### 3. Integração com o Walker
- Atualizar a lógica do Walker para processar o input do usuário (Opção A).
- Implementar o `spawn_agent` para disparar o Scout com o contexto do `data/user-profile.md`.
- Adicionar rotina de escrita para salvar resultados em `data/job-search-results.md`.

### 4. Estratégia de Fallback (Procedimento em skills/job-search.md)
- O agente deve sempre tentar `firecrawl` como prioridade.
- Se o comando de terminal retornar erro, o agente deve registrar no campo "erros" do envelope de resposta.
- Antes de desistir, o agente tentará realizar uma busca web nativa para coletar informações básicas sobre vagas nos sites mencionados (Infojobs, Vagas, Indeed), garantindo que a experiência do usuário não seja interrompida.

### 5. Validação
- Testar a execução do comando `firecrawl` no terminal.
- Verificar o fluxo de Handoff entre Walker e Scout.
- Confirmar a escrita correta dos resultados em `data/job-search-results.md`.

---
## Notas
- Seguir estritamente a arquitetura multi-agente.
- Nenhuma saída deve conter tabelas markdown; usar apenas listas numeradas com pares chave-valor.
- Todos os caminhos devem ser relativos à raiz do projeto.
