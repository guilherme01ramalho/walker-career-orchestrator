# Plano 4: Agente COACH (Preparação para Entrevistas)

## Objetivo

Implementar o agente COACH para auxiliar o usuário na preparação para entrevistas de emprego, oferecendo orientações personalizadas, dicas práticas e simulações de entrevistas com base no perfil profissional do usuário e nas vagas encontradas pelo Scout.

## Etapas do Plano

### 1. Criação da Skill de Entrevista (`skills/interview-coaching.md`)

* Definir o protocolo de preparação para entrevistas.
* Consultar obrigatoriamente:
  * `data/user-profile.md`
  * `data/job-search-results.md` (quando disponível)
* Identificar:
  * Área de interesse do usuário.
  * Nível de experiência.
  * Habilidades técnicas.
  * Soft skills.
  * Requisitos mais frequentes das vagas encontradas.
* Gerar recomendações personalizadas para entrevistas.

### 2. Criação da Persona do COACH (`personas/coach.md`)

* Definir comportamento de mentor especializado em entrevistas e empregabilidade.
* Atuar de forma encorajadora e objetiva.
* Adaptar orientações conforme:
  * Área profissional.
  * Senioridade.
  * Tipo de vaga.
* Fornecer feedback construtivo após simulações.

### 3. Integração com o Walker

* Atualizar o menu do Walker adicionando uma nova opção.

Opções atualizadas:
A - Responder o quiz
B - Buscar vagas de emprego
C - Buscar cursos de capacitação
D - Preparação para entrevistas

### 4. Funcionalidades do COACH

#### Modo 1: Dicas para Entrevistas
O agente deve:
* Ler o perfil do usuário.
* Analisar vagas encontradas pelo Scout quando existirem.
* Gerar recomendações específicas sobre:
  * Apresentação pessoal.
  * Comunicação.
  * Demonstração de experiência.
  * Destaque de habilidades técnicas.
  * Destaque de soft skills.
  * Erros comuns a evitar.
  * Perguntas frequentes da área escolhida.

#### Modo 2: Simulação de Entrevista
O agente deve:
* Criar uma entrevista simulada baseada na área de interesse do usuário.
* Fazer apenas uma pergunta por vez.
* Aguardar a resposta do usuário.
* Avaliar a resposta.
* Fornecer feedback.
* Fazer a próxima pergunta.

Ao final da simulação:
* Apresentar avaliação geral.
* Identificar pontos fortes.
* Identificar pontos de melhoria.
* Sugerir temas para estudo e prática.

### 5. Persistência dos Resultados

Criar: `data/interview-results.md`

O arquivo deve armazenar:
* Data da simulação.
* Área da entrevista.
* Perguntas realizadas.
* Respostas do usuário.
* Feedback gerado.
* Avaliação final.

### 6. Estratégia de Personalização

* Quando existirem resultados do Scout:
  * Utilizar as vagas encontradas como referência.
  * Priorizar perguntas relacionadas às tecnologias mais solicitadas.
  * Simular cenários semelhantes aos processos seletivos identificados.
* Quando não existirem vagas:
  * Utilizar apenas o perfil presente em `data/user-profile.md`.

### 7. Fluxo de Execução

1. Usuário seleciona "Preparação para entrevistas".
2. Walker lê:
   * `data/user-profile.md`
   * `data/job-search-results.md` (se existir)
3. Walker despacha o COACH.
4. COACH pergunta qual modo o usuário deseja:
   * Dicas para entrevistas
   * Simulação de entrevista
5. COACH executa a atividade escolhida.
6. Walker salva os resultados em:
   * `data/interview-results.md`
7. Walker retorna ao menu principal.

### 8. Validação

* Verificar leitura correta de `data/user-profile.md`.
* Verificar integração com `data/job-search-results.md`.
* Confirmar geração de `data/interview-results.md`.
* Confirmar que a simulação ocorre com apenas uma pergunta por vez.
* Confirmar que o feedback é gerado ao final da entrevista.

---

## Regras Críticas

* Não gerar código de implementação (scripts).
* Nenhuma saída pode conter tabelas Markdown.
* Todos os caminhos de arquivo devem ser relativos à raiz (`data/`, `personas/`, `skills/`).
* O COACH deve sempre utilizar o perfil do usuário como contexto principal.
* Durante simulações, fazer apenas uma pergunta por interação.
* Sempre fornecer feedback construtivo e acionável.
* O COACH deve reportar explicitamente qualquer erro de leitura ou preparação da entrevista.
