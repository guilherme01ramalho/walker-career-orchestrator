# Plano 3: Agente SKILLPATH (Busca de Cursos)

## Objetivo
Implementar o agente **SKILLPATH** para buscar cursos complementares na Alura, Udemy e Guia da TI, baseando-se nas lacunas de habilidades identificadas entre o perfil do usuário (quiz) e as vagas encontradas.

## Etapas do Plano

### 1. Criação da Skill de Busca de Cursos (`skills/course-search.md`)
- Definir o protocolo de busca:
  - Utilizar `firecrawl` para navegar nos sites: `alura.com.br`, `udemy.com.br` e `guiadeti.com.br`.
  - Focar em cursos que cubram as "habilidades em falta" listadas em `data/job-search-results.md`.
- Documentar os passos de extração:
  - Capturar título, plataforma, link e nível do curso.
  - Priorizar resultados que correspondam à stack técnica exigida pelas vagas.

### 2. Criação da Persona do SKILLPATH (`personas/skillpath.md`)
- Definir comportamento de um mentor de carreira focado em aprendizado contínuo.
- Estabelecer a obrigatoriedade de consultar `data/job-search-results.md` antes de iniciar a busca.
- Instruir o agente a apresentar sugestões de cursos como "pontes" para as vagas desejadas.

### 3. Integração com o Walker
- Atualizar o menu do Walker (adicionar nova opção de busca de cursos).
- Implementar o `spawn_agent` para disparar o SKILLPATH com o contexto consolidado de lacunas de habilidades.
- Adicionar rotina de escrita para salvar recomendações em `data/course-recommendations.md`.

### 4. Estratégia de busca
- O agente deve realizar buscas direcionadas por habilidade (ex: "curso de [habilidade] alura").
- Analisar os resultados para garantir que são cursos relevantes e atuais.
- Se a busca falhar em uma fonte, deve tentar a próxima automaticamente.

### 5. Validação
- Testar a execução do `firecrawl` para listagem de cursos.
- Verificar se o Walker consegue ler as lacunas de habilidades e passar para o SKILLPATH.
- Confirmar a geração do arquivo `data/course-recommendations.md`.

---
## Regras Críticas
- Não gerar código de implementação (scripts); a persona atua via comportamento.
- Nenhuma saída pode conter tabelas Markdown (apenas listas numeradas chave-valor).
- Todos os caminhos de arquivo devem ser relativos à raiz (`data/`, `personas/`, `skills/`).
- O SKILLPATH deve sempre reportar erros de busca explicitamente.
