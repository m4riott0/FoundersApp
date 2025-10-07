# **FoundersApp**

## 🎯 Visão Geral

O **FoundersApp** é uma **rede social focada em projetos, startups, novas ideias e tudo em questao do mundo empresarial**, que conecta **fundadores, colaboradores, investidores e mentores**.

O app terá dois pilares principais:

* **Feed social** de micro-posts, com comentários, curtidas e networking.
* **Gestão de projetos** com vagas, progresso, métricas e recursos premium.

---

## 🎨 Identidade Visual (Cores e Layout)

Inspirado em um estilo **minimalista, escuro e moderno**, com foco em clareza e contraste:

* **Preto (#000000)** → fundo principal (background).
* **Cinza escuro (#1C1C1C)** → cards, áreas de destaque (posts, caixas de projeto).
* **Cinza claro (#A0A0A0 – #C0C0C0)** → barras de progresso, divisores sutis.
* **Branco (#FFFFFF)** → textos principais e ícones neutros.
* **Azul (#1D9BF0)** → botões principais (“Ver”), ícones de verificação, links.
* **Vermelho (#FF0000)** → coração de like (interação emocional).

👉 Estilo: **rede social minimalista, dark mode, social-first.**

---

## 🛠️ Tecnologias

* **Frontend** → React
* **Backend** → node.js
* **Banco de dados**:
  * **Supabase** → autenticação, perfis, feed social, notificações realtime, storage de mídias, projetos/ new statup ou outra categoria que serao definidas, vagas, métricas, investimentos, histórico avançado.
* **Gateway de Pagamentos** → Abacate Pay (assinaturas premium e monetização).
* **Infra** → containers (Docker/Kubernetes), CI/CD (GitHub Actions).

---

# 🗄️ Arquitetura de dados

### 🔹 **Módulo de Usuários & Social**

* Autenticação (Supabase Auth).
* Perfil estendido com bio, foto, interesses e **links sociais (LinkedIn, GitHub, Instagram, etc.)**.
* Feed social **estilo LinkedIn** (posts com texto, mídia, compartilhamentos, reações e comentários).
* Notificações em tempo real.
* Upload de imagens/vídeos curtos no feed.

**Tabelas principais:**

* `users` → gerenciado pelo Supabase Auth.
* `profiles` → dados extras do usuário (bio, interesses, foto).
* `social_links` → links externos do usuário (LinkedIn, GitHub, Instagram, etc.).
* `posts` → conteúdo do feed (texto, imagem, vídeo).
* `post_reactions` → curtidas/reações nos posts.
* `comments` → comentários em posts.
* `shares` → compartilhamentos de posts.
* `notifications` → alertas em tempo real.

---

### 🔹 **Módulo de Projetos & Startups**

* Criação de projetos/startups.
* Perfil de projeto com **nível/maturidade**:

  * `hobby` → só diversão.
  * `personal` → projeto pessoal.
  * `collab` → colaboração aberta.
  * `startup` → empresa nascente.
  * `enterprise` → projeto mais robusto.
* Roadmap e milestones.
* Gestão de vagas + candidaturas.
* Histórico de contribuições.

**Tabelas principais:**

* `projects` → info básica do projeto.

  * campo `maturity_level` (enum: `hobby`, `personal`, `collab`, `startup`, `enterprise`).
* `project_links` → links sociais ou institucionais do projeto (site, pitch deck, GitHub, LinkedIn).
* `project_members` → participantes do projeto.
* `vacancies` → vagas abertas.
* `applications` → candidaturas dos usuários.
* `milestones` → metas e progresso.
* `contributions` → histórico de contribuições de membros.

---

### 🔹 **Módulo de Métricas & Engajamento**

* Estatísticas de engajamento de usuários e projetos.
* Ranking de projetos e perfis.
* Registro de interações (analytics).

**Tabelas principais:**

* `metrics`
* `engagement_logs`

---

### 🔹 **Premium & Monetização (via Abacate Pay)**

O modelo **freemium → premium** garante escala e diferenciação.

**Recursos Free**

* Criar perfil.
* Seguir projetos.
* Curtir e comentar.
* Aplicar em até **2 vagas ativas**.
* Acesso ao feed completo.

**Recursos Premium**

* Aplicar em **vagas ilimitadas**.
* Criar **projetos ilimitados**.
* Destaque do perfil em buscas/recomendações.
* Métricas avançadas (quem viu seu projeto, engajamento detalhado).
* Salas de pitch interativas (vídeo/áudio ao vivo).
* Conexão direta com investidores.

**Tabelas principais:**

* `subscriptions` → controla status premium do usuário.
* `premium_features` → log de uso de recursos premium.
* `transactions` → histórico de pagamentos (via Abacate Pay).

---

# 🔄 Fluxo Resumido

1. **Cadastro** → usuário cria conta no `Supabase Auth`.
2. **Perfil** → salvo em `profiles`, com links externos em `social_links`.
3. **Feed Social** → posts, comentários, curtidas, compartilhamentos.
4. **Projetos** → criados em `projects`, com maturidade (`maturity_level`) e links (`project_links`).
5. **Colaboração** → vagas, candidaturas e contribuições.
6. **Premium** → validado pelo **Abacate Pay**, salvo em `subscriptions` e aplicado em recursos.

---

## 🧭 Roadmap Inicial

### MVP

* Login + feed social (React + Supabase + .NET).
* Criação de projetos simples (Postgres).
* Vagas com aplicação.
* Curtidas, comentários, seguidores.
* Premium básico (limite de vagas e projetos).

### Fase 2

* Matchmaking inteligente (IA).
* Estatísticas avançadas.
* Pitch em vídeo/áudio.
* Integração com GitHub/Jira.

### Fase 3

* Investimentos & equity tracking.
* Tokenização de contribuições (opcional Web3).
* Marketplace de serviços (design, marketing, devs).

---
