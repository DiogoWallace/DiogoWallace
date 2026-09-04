# Diogo Wallace

**Full Stack** — backend, dados e IA aplicada. Lavras, MG.

Trabalho no caminho inteiro do dado: da coleta em campo (telemetria de frota) até
o dashboard e o chatbot que responde em linguagem natural. Backend em Laravel e
Python, banco em SQL Server e Postgres, e a camada de IA em cima — NL2SQL,
agentes e automações que tiram o relatório manual do meio do caminho.

O que me interessa não é a stack, é a decisão: por que monorepo e não dois
repos, por que JSONB e não tabela normalizada, por que a simulação roda no
cliente. Registro essas decisões — dá pra ler no `docs/adr` do Orbital.

## Como eu trabalho

- **Decisões viram documento.** O [Orbital](https://github.com/DiogoWallace/orbital) tem 14 ADRs versionados em `docs/adr` — de `0001-monorepo-dois-deployables` a `0014-reprodutibilidade-de-uma-analise`. Cada escolha de arquitetura tem contexto, alternativas e consequência escritos.
- **Convenção que o repo cobra sozinho.** Git hooks versionados em `.githooks` + template de commit, ligados com um `make hooks`. O padrão de mensagem não depende de eu lembrar dele.
- **Prompt é código.** No [NL2SQL](https://github.com/DiogoWallace/Bot-AI-NL2SQL-) os prompts moram em `app/prompts/*.md`, versionados e revisáveis — não enterrados numa f-string no meio da lógica.
- **Ambiente reprodutível.** Docker Compose com php-fpm 8.4, nginx, Postgres 16 e Redis. `docker compose up -d` e roda igual em qualquer máquina.

## Projetos

### [Orbital](https://github.com/DiogoWallace/orbital) — no ar em [orbitalexperiments.com](https://orbitalexperiments.com)
`Laravel 13` `Next.js 16` `PostgreSQL 16` `Redis` `Docker`

Plataforma científica interativa: simulações, visualizações e análise de dados em
física, astronomia, engenharia e química.

Monorepo com dois deployables — API REST versionada (`/api/v1`) e front em
Next.js usando RSC + BFF, com auth via Sanctum. As decisões que sustentam isso
estão escritas: **módulo como plugin** para novos experimentos entrarem sem tocar
no core, **spec do experimento em JSONB** para o schema não travar a cada
simulação nova, **simulação rodando no cliente** para o servidor não virar
gargalo de cálculo, e **reprodutibilidade de uma análise** — quem abre um
resultado consegue chegar nele de novo.

### [Darwin AI — NL2SQL](https://github.com/DiogoWallace/Bot-AI-NL2SQL-)
`Python` `Gemini` `SQL Server` `n8n`

Chatbot de telemetria que traduz pergunta em português para SQL, consulta a base
de frota e devolve a resposta pronta. Substitui o "me manda aquele relatório".

Organizado em camadas — `text_to_sql`, `chat` e `summarizer` separados, cada um
com seu prompt em arquivo próprio, mais `security.py` e allowlist de usuários na
frente. A tradução para SQL é o passo perigoso: fica isolada, com prompt que dá
pra revisar em diff.

### [Bot de Frotas](https://github.com/DiogoWallace/bot-python)
`Python`

Monitoramento e alertas automatizados para gestão de frota.

### [Sistema Clínica](https://github.com/DiogoWallace/clinica)
`Laravel` `TypeScript`

Gestão completa para clínica de pilates — agenda, pacientes e financeiro.
Backend em Laravel, interface em TypeScript.

### [ERP Adega](https://github.com/DiogoWallace/erp-lambadega)
`PHP`

Estoque, vendas e financeiro para adegas.

### Dashboards Power BI
Frota, consumo de combustível, jornada de motorista e financeiro — alimentados
por ETL próprio sobre SQL Server.

## Stack

**Backend** Laravel · PHP · CodeIgniter · Python · Node.js
**Dados** SQL Server · PostgreSQL · MySQL · ETL · Power BI
**Frontend** TypeScript · Next.js · React · Bootstrap
**Mobile** Flutter · Dart
**Infra & Automação** Docker · n8n · Webhooks · APIs REST

## Estudando agora

Arquitetura limpa, NL2SQL e agentes de IA — e como registrar decisão de
arquitetura de um jeito que o próprio repositório cobre.

## GitHub

<div align="center">
  <img src="https://streak-stats.demolab.com/?user=DiogoWallace&theme=dracula&hide_border=true&background=282A36" alt="Streak de commits" />

  <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=DiogoWallace&theme=dracula" alt="Resumo do perfil" />

  <img height="180" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=DiogoWallace&theme=dracula" alt="Linguagens mais usadas, por commit" />
  <img height="180" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=DiogoWallace&theme=dracula" alt="Estatisticas gerais" />
</div>

---

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/diogo-wallace-043904273/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:diogo.wallaceferreira@gmail.com)
