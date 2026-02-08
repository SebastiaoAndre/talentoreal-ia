# Arquitetura do Sistema — TalentoReal IA

## Objetivo
Definir a arquitetura técnica do TalentoReal IA (MVP e evolução), garantindo:
- validação de talentos por provas reais
- antifraude em vagas e perfis
- matching inteligente entre candidato e empresa
- trilhas de formação com reavaliação e score

---

## Visão Geral (alto nível)

**Clientes (Front-end)**
- Web App (MVP): Next.js / React
- Mobile (futuro): React Native ou Flutter

**Back-end**
- Firebase (MVP): Auth + Firestore + Storage
- Cloud Functions: lógica sensível (validação, score, antifraude)
- API de IA: módulo de IA (serviço interno) para análises e recomendações

**Dados**
- Firestore (dados operacionais)
- Storage (documentos/provas: PDFs, imagens, portfólios)
- Logs/telemetria (auditoria antifraude)

---

## Componentes do MVP (Fase 1)

### 1) Autenticação e Perfis
- Perfis: Profissional / Empresa / Formação
- Login: email/senha + (opcional) Google
- Regras: verificação de email, proteção contra abuso

### 2) Gestão de Vagas (Empresas)
- Criar/editar/publicar vaga
- Campos mínimos: título, local, tipo, salário (se aplicável), requisitos, etapas
- Estado da vaga: rascunho → publicada → suspensa → encerrada

### 3) Provas e Validação (Profissionais)
- Upload de provas: certificados, experiência, portfólio, links
- Micro-testes por área (níveis 1–6)
- Status do perfil: incompleto → em validação → validado

### 4) Antifraude (núcleo)
- Detecção de inconsistências: datas, duplicações, padrões suspeitos
- Verificação mínima: email + histórico de ações + reputação
- Flags de risco: baixo / médio / alto
- Auditoria: registo de eventos importantes (logs)

### 5) Score do Talento
- Score composto (0–100) baseado em:
  - provas (peso maior)
  - micro-testes
  - consistência/antifraude
  - feedback de entrevistas (futuro)
- Score gera nível: 1 a 6

### 6) Matching Inteligente
- Matching inicial por regras:
  - profissão/área, localização, nível/score, skills
- Matching evoluído (IA):
  - ranking por relevância e risco baixo
  - explicação do porquê do match (transparência)

### 7) Formação (Evolução)
- IA identifica lacunas (skills faltando)
- Recomenda trilhas
- Reavalia e atualiza score

---

## Segurança e Boas Práticas
- Firestore Security Rules por tipo de perfil
- Cloud Functions para:
  - cálculo de score
  - antifraude
  - validações sensíveis
- Proteção contra spam:
  - limite de uploads
  - limite de criação de vagas por dia (MVP)
- Privacidade:
  - provas visíveis apenas quando necessário
  - consentimento para partilha com empresas

---

## Roadmap técnico (resumo)
- Fase 1: MVP (Auth + Perfis + Vagas + Provas + Score básico + Matching simples)
- Fase 2: Antifraude forte + IA de recomendação + dashboards
- Fase 3: Mobile + integrações + parcerias + escala

---

## Tecnologias recomendadas (MVP)
- Front-end: Next.js (React)
- Back-end: Firebase (Auth, Firestore, Storage)
- Lógica: Cloud Functions (Node.js/TS)
- IA: módulo de IA (OpenAI/LLM + regras) com logs e explicabilidade
