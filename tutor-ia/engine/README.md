# Engine do MentorPS

## Objetivo

A Engine representa o núcleo de processamento do Tutor MentorPS.

Ela é responsável por decidir:

- como responder;
- quando responder;
- o que responder;
- qual estratégia pedagógica utilizar;
- qual nível cognitivo aplicar;
- qual será o próximo passo da aprendizagem.

A Engine nunca produz conteúdo diretamente.

Ela apenas coordena os demais componentes do Tutor.

---

## Arquitetura

A Engine é composta pelos seguintes módulos:

- Algoritmo Pedagógico
- Motor de Contexto
- Motor de Decisão
- Motor de Competências
- Motor de Feedback
- Motor de Progresso
- Motor de Revisão

Cada componente possui uma responsabilidade específica.

Nenhum módulo deve assumir responsabilidades pertencentes a outro módulo.
