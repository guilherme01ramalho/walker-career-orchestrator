# Skill: Busca de Vagas (Job Search)

## Objetivo
Buscar, filtrar e analisar vagas de emprego de acordo com o perfil do usuário.

## Protocolo de Execução
1. **Busca Inicial**: Executar `firecrawl search "vagas [area_de_interesse] [localizacao]" --json` via terminal.
2. **Processamento**:
   - Analisar o JSON retornado.
   - Para cada vaga, se necessário, executar `firecrawl scrape <url> --format markdown`.
3. **Análise de Habilidades**:
   - Comparar requisitos da vaga com habilidades do `data/user-profile.md` (insensível a maiúsculas/minúsculas).
   - Contar correspondências e identificar habilidades faltantes.
4. **Tratamento de Erros**:
   - Se `firecrawl` falhar, reportar no campo "erros" do envelope de resposta.
   - **Fallback**: Se o comando via terminal falhar, utilizar a ferramenta nativa de acesso web para buscar informações básicas.
   - Não continuar silenciosamente; falhas devem ser explicitadas.

## Formato de Resposta (Envelope)
1. titulo: [título]
   empresa: [nome]
   localizacao: [cidade/Remoto]
   link: [URL]
   habilidades_correspondentes: [lista]
   habilidades_faltantes: [lista]
   contagem_correspondencia: [X de Y]
   erros: [se houver]
