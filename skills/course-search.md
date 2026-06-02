# Skill: course-search.md

**Responsabilidade**: Buscar e recomendar cursos para preencher lacunas de habilidades.

## Protocolo de Execução
1. **Leitura de Contexto**: Ler o arquivo `data/job-search-results.md` para identificar as "habilidades_faltantes".
2. **Execução de Busca**: Para cada habilidade faltante, executar via terminal:
   `firecrawl search "curso de [habilidade] site:alura.com.br OR site:udemy.com.br OR site:guiadeti.com.br" --json`
3. **Extração e Filtragem**:
   - Analisar o JSON de retorno.
   - Extrair: título, plataforma (baseada na URL), link, nível (se disponível).
   - Priorizar cursos que cobrem a habilidade exata.
4. **Tratamento de Erros**:
   - Se `firecrawl` falhar, registrar o erro no campo "erros" do envelope de resposta e pular para a próxima habilidade ou fonte.

## Formato de Resposta (Envelope de Resposta)
```
1. titulo: [Nome do Curso]
   plataforma: [Alura/Udemy/Guia da TI]
   link: [URL]
   nivel: [Iniciante/Intermediário/Avançado]
   habilidade_alvo: [Habilidade]

2. [Próximo curso no mesmo formato]

erros: [Lista de falhas se houver]
```

## Regras
- Sempre usar `firecrawl search`.
- Nenhuma tabela markdown.
- Apenas listas numeradas.
- Reportar explicitamente se nenhuma fonte retornar resultados.
