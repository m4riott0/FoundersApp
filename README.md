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
* **Backend** → .NET
* **Banco de dados**:

  * **Supabase** → autenticação, perfis, feed social, notificações realtime, storage de mídias.
  * **PostgreSQL** → projetos, vagas, métricas, investimentos, histórico avançado.
* **Gateway de Pagamentos** → Abacate Pay (assinaturas premium e monetização).
* **Infra** → containers (Docker/Kubernetes), CI/CD (GitHub Actions).

---

## 🗄️ Arquitetura de Bancos

### 🔹 **Supabase (simples, rápido, social)**

* Autenticação de usuários.
* Perfis básicos (nome, bio, foto, interesses).
* Feed social (posts, comentários, curtidas).
* Notificações em tempo real.
* Upload de imagens/vídeos curtos.

**Tabelas principais (Supabase):**

* `users`
* `profiles`
* `posts`
* `comments`
* `likes`

---

### 🔹 **PostgreSQL (robusto, crítico, escalável)**

* Projetos e suas informações avançadas.
* Roadmap e milestones.
* Gestão de vagas (com aplicantes e status).
* Métricas de uso e engajamento.
* Matchmaking (skills e recomendações de projetos).
* Histórico de contribuições.

**Tabelas principais (Postgres):**

* `projects`
* `project_members`
* `vacancies`
* `applications`
* `metrics`

---

## 💎 Premium & Monetização

O modelo **freemium** garantirá acesso básico gratuito e desbloqueio de recursos avançados via **Abacate Pay**.

### 👤 Usuário Free

* Criar perfil.
* Seguir projetos.
* Curtir e comentar.
* Aplicar em até **2 vagas ativas**.
* Acessar feed social completo.

### 💎 Usuário Premium

* Aplicar em **vagas ilimitadas**.
* Criar **projetos ilimitados**.
* Destaque do perfil em buscas e recomendações.
* Estatísticas avançadas (quem viu seu projeto, métricas de engajamento).
* Salas de pitch interativas (vídeo/áudio ao vivo).
* Conexão direta com investidores.

### 📊 Banco de Dados Premium

* `subscriptions` → controla se o usuário é premium (via Abacate Pay).
* `premium_features` → histórico de uso de funcionalidades premium.
* Integrado tanto ao **Supabase (users/profiles)** quanto ao **PostgreSQL (projects, metrics)**.

---

## 🚀 Fluxo entre Supabase & PostgreSQL

1. Usuário cria conta → Supabase Auth.
2. Perfil sincronizado → `profiles` (Supabase) e `users_core` (Postgres).
3. Interações rápidas (likes, posts, comments) → **Supabase**.
4. Dados críticos de projeto (vagas, métricas, progresso) → **Postgres**.
5. Premium → validado via Abacate Pay, armazenado em Supabase e refletido no Postgres.

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

📌 **Resumo**:
Este documento define a visão do **FoundersApp**, seu layout visual, tecnologias principais (React + .NET + Supabase + PostgreSQL + Abacate Pay), modelo freemium/premium e roadmap de evolução.
A meta é criar uma **nova rede social de projetos/startups** moderna, escalável e monetizável.
