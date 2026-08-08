# Material

Esta pasta contém o material de apoio bruto da disciplina: slides, diagramas e PDFs.

Ela é separada de `unidades/` de propósito:

- `unidades/` guarda o **conteúdo pedagógico em Markdown** (aula escrita, atividade, desafio, checklist etc.) — é o que o Tutor MentorPS lê e referencia.
- `material/` guarda os **arquivos de apoio** que não fazem sentido em Markdown puro: apresentações, diagramas exportados, PDFs de referência.

---

## Estrutura

```
material/
  unidade01/
    semana01/
      slides/
      diagramas/
      pdfs/
    semana02/
    ...
  unidade02/
  unidade03/
  unidade04/
```

Siga sempre `unidadeXX/semanaYY/` para espelhar a estrutura de `unidades/`.

---

## Convenção de nomenclatura

`unidadeXX-semanaYY-tipo-descricao.ext`

Exemplos:

- `unidade01-semana01-slides-introducao.pdf`
- `unidade01-semana01-diagrama-caso-de-uso-clinica.png`

---

## Diagramas (UML / PlantUML)

Diagramas feitos em PlantUML devem ser versionados como **código-fonte** (`.puml`), não apenas como imagem:

- `diagrama-x.puml` — fonte, editável e revisável em Pull Request.
- `diagrama-x.png` — exportação gerada a partir do `.puml`, para visualização direta no GitHub.

Sempre commitar os dois juntos. O `.puml` é a fonte da verdade; a imagem é derivada.

Diagramas feitos em Draw.io devem ser exportados como `.png` (para visualização) mantendo o `.drawio` original junto, pelo mesmo motivo: o `.drawio` é a fonte editável.

---

## Arquivos binários grandes

PDFs e apresentações grandes (`.pdf`, `.pptx`, `.png`, `.jpg`) são tratados como binários pelo Git (ver `.gitattributes` na raiz do repositório). Evite subir arquivos de vídeo ou binários muito grandes (>20MB) diretamente no repositório — prefira link externo (Google Drive, YouTube não listado etc.) referenciado no Markdown correspondente em `unidades/`.
