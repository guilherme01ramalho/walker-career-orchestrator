🚀 Walker Career Orchestrator

Sistema multi-agente de IA desenvolvido durante a Imersão IA da Alura para auxiliar usuários em sua jornada de recolocação profissional.

O projeto utiliza uma arquitetura baseada em agentes especializados, permitindo a busca inteligente de vagas, análise de perfil profissional, identificação de lacunas de habilidades e futuras recomendações de capacitação.

---

🎯 Objetivo

Criar uma consultoria de carreira automatizada utilizando Inteligência Artificial e agentes especializados.

O sistema é capaz de:

- Entender o perfil do usuário através de um quiz
- Armazenar informações de contexto
- Buscar vagas compatíveis com o perfil informado
- Comparar habilidades do usuário com requisitos das vagas
- Identificar lacunas de conhecimento
- Servir como base para recomendações de cursos e simulações de entrevistas

---

🏗️ Arquitetura

Usuário
   │
   ▼
Walker (Orquestrador)
   │
   ├── Scout (Busca de vagas)
   ├── Curator (Recomendação de cursos)
   └── Coach (Preparação para entrevistas)

Walker

Agente principal responsável por:

- Receber solicitações do usuário
- Coordenar os agentes especializados
- Consolidar respostas
- Gerenciar o fluxo da aplicação

Scout

Agente especializado em:

- Busca de vagas
- Análise de compatibilidade
- Extração de requisitos
- Comparação de habilidades

Curator (Em desenvolvimento)

Responsável por:

- Recomendar cursos
- Sugerir trilhas de aprendizado
- Auxiliar no desenvolvimento profissional

Coach (Em desenvolvimento)

Responsável por:

- Simulações de entrevistas
- Feedback de respostas
- Preparação para processos seletivos

---

⚙️ Tecnologias Utilizadas

- Gemini API
- Firecrawl
- Zed Editor
- Git
- GitHub
- Markdown-based Memory
- Arquitetura Multi-Agent

---

📂 Estrutura do Projeto

agent-alura/
├── AGENTS.md
├── personas/
│   ├── walker.md
│   ├── scout.md
│   ├── coach.md
│   └── skillpath.md
│
├── skills/
│   ├── job-search.md
│   ├── course-search.md
│   └── interview-coaching.md
│
├── data/
│   ├── personality-quiz.md
│   ├── user-profile.md
│   ├── job-search-results.md
│   └── course-recommendations.md
│
└── plano.md

---

🔍 Fluxo Atual

1. Usuário inicia interação com o Walker
2. Walker coleta informações do perfil
3. Scout recebe o contexto do usuário
4. Firecrawl realiza busca de vagas
5. Scout analisa os requisitos encontrados
6. Compatibilidade é calculada
7. Resultados são apresentados ao usuário
8. Informações são armazenadas para uso futuro

---

🚧 Status do Projeto

Em desenvolvimento.

Funcionalidades concluídas:

- Quiz de perfil profissional
- Persistência de contexto
- Arquitetura multi-agente
- Busca automatizada de vagas
- Integração com Gemini API
- Integração com Firecrawl
- Armazenamento de resultados

Próximos passos:

- Recomendação de cursos
- Simulação de entrevistas
- Ranking de compatibilidade
- Roadmap de carreira personalizado
- Dashboard de acompanhamento

---

📸 Demonstração

Vídeo demonstrando o fluxo do sistema disponível no LinkedIn.

---

🤝 Contribuições

Sugestões e melhorias são bem-vindas.

---

👨‍💻 Autor

Guilherme Ramalho
