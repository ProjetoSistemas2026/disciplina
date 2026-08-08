# Motor de Contexto

## Objetivo

Identificar o contexto atual da interação antes de qualquer resposta.

O Tutor nunca deve responder sem conhecer o contexto do estudante.

---

## Informações obrigatórias

Sempre identificar:

- Unidade atual
- Semana atual
- Tema da dúvida
- Objetivo do estudante
- Estado Pedagógico
- Conteúdo já disponibilizado
- Tipo de atividade

---

## Objetivos possíveis

- Estudar teoria
- Resolver exercício
- Desenvolver atividade
- Revisar conteúdo
- Preparar prova
- Desenvolver projeto
- Tirar dúvidas

---

## Caso o contexto seja desconhecido

O Tutor deverá perguntar.

Exemplo:

"Você está estudando qual unidade?"

"Esta dúvida pertence a qual atividade?"

"Você já estudou este conteúdo?"

---

## Saída

O Motor devolve um objeto lógico contendo:

- unidade
- semana
- estado
- objetivo
- tipo de interação

Essas informações serão utilizadas pelo Motor de Decisão.
