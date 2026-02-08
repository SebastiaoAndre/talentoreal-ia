# Modelo de Dados — TalentoReal IA
## Diagrama do Modelo de Dados

![ERD TalentoReal IA](ERD_TalentoRealIA.png)

## Objetivo

Definir a estrutura de dados do sistema TalentoReal IA para suportar:

- Validação de talentos
- Sistema antifraude
- Score de Talento
- Matching inteligente
- Gestão de vagas e empresas

Preparado para Firebase / Backend escalável.

---

## Entidades Principais

### 1. Utilizadores (Users)

Representa todos os utilizadores da plataforma.

Campos:

- id
- nome
- email
- tipo (talento | empresa | admin)
- país
- data_criação
- estado_conta
- nível_confiança

---

### 2. Perfis de Talento (Talent Profiles)

Campos:

- user_id
- área_profissional
- competências
- experiência
- provas_submetidas
- score_talento
- nível_verificação
- histórico_evolução

---

### 3. Provas de Competência (Proofs)

Campos:

- id
- user_id
- tipo_prova (teste | projeto | certificação | desafio)
- resultado
- validação_IA
- data_submissão
- nível_confiança

---

### 4. Sistema Antifraude (Fraud Detection)

Campos:

- user_id
- inconsistências_detectadas
- score_risco
- comportamento_suspeito
- validação_manual
- estado_segurança

---

### 5. Score de Talento (Talent Score)

Campos:

- user_id
- score_total
- competências_validadas
- confiabilidade
- evolução
- ranking

---

### 6. Empresas (Companies)

Campos:

- id
- nome_empresa
- país
- sector
- vagas_publicadas
- nível_confiança

---

### 7. Vagas (Jobs)

Campos:

- id
- empresa_id
- título
- requisitos
- nível_competência
- validação_IA
- estado_vaga

---

### 8. Matching Inteligente (Matching Engine)

Campos:

- talento_id
- vaga_id
- score_correspondência
- nível_confiança
- probabilidade_sucesso
- estado_matching

---

## Preparação Técnica

O modelo está preparado para:

- Firebase Firestore
- Backend escalável
- Machine Learning
- Sistema antifraude
- Expansão global

---

## Estado Atual

Modelo definido para fase MVP.  
Estrutura pronta para implementação técnica.

## Diagrama de Entidades (ERD)

O diagrama abaixo representa a estrutura lógica de dados do sistema TalentoReal IA, incluindo utilizadores, perfis, empresas, provas, antifraude, pontuação de talento e motor de correspondência.
