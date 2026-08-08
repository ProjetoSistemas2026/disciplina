# Guia de Uso da IA (Tutor MentorPS)

Este guia explica **como conversar com o Tutor MentorPS** usando uma ferramenta de IA — paga ou gratuita, à sua escolha. Ele não é um produto pronto: é um **prompt** (arquivo `tutor-ia/PROMPT_BASE.md`) que você carrega em uma IA de sua preferência, junto com o material da semana. A IA passa a se comportar como o MentorPS enquanto essa conversa durar.

Você não precisa pagar nada para usar o Tutor IA. Todas as opções abaixo funcionam — a diferença é conveniência, não qualidade de acesso ao conteúdo.

---

## 1. O que você vai carregar na IA, sempre

Toda opção abaixo segue a mesma lógica:

1. **O prompt do tutor** — conteúdo de [`tutor-ia/PROMPT_BASE.md`](tutor-ia/PROMPT_BASE.md).
2. **O material da semana atual** — os arquivos dentro de `unidades/unidadeXX/semanaYY/` (aula, atividade, guia de IA da semana, etc.).

A IA só deve responder com base nesses arquivos — é isso que o prompt garante. Se você carregar só a pergunta, sem o prompt e sem o material, a IA vai responder como uma IA genérica, não como o MentorPS.

---

## 2. Opção A — Claude Code (paga, a mais integrada)

O [Claude Code](https://claude.com/claude-code) é uma ferramenta de linha de comando que já opera **dentro** do seu repositório clonado — ela lê os arquivos diretamente, sem você precisar copiar e colar nada.

```bash
cd disciplina
claude
```

Dentro da conversa, peça para ela assumir o papel do tutor, por exemplo:

```
Leia tutor-ia/PROMPT_BASE.md e assuma esse papel a partir de agora.
Estou na unidade01/semana01. Me ajude a entender a aula.
```

Vantagem: ela pode ler qualquer arquivo do repositório sozinha, sem você precisar colar conteúdo. Requer assinatura.

---

## 3. Opção B — Chat gratuito na web, colando o conteúdo (ChatGPT, Claude, Gemini, etc.)

Funciona em qualquer chat de IA gratuito no navegador. Você mesmo copia e cola o conteúdo:

1. Abra [`tutor-ia/PROMPT_BASE.md`](tutor-ia/PROMPT_BASE.md) no GitHub, copie todo o texto e cole na primeira mensagem do chat.
2. Na sequência (ou na mesma mensagem), copie e cole o conteúdo do `AULA.md` da semana atual (`unidades/unidadeXX/semanaYY/AULA.md`).
3. A partir daí, converse normalmente — a IA vai responder como o MentorPS, seguindo as regras do prompt.

Isso funciona nos planos gratuitos do ChatGPT, Claude, Gemini e similares — nenhum deles exige pagamento para esse uso básico de colar texto.

---

## 4. Opção C — Enviar o repositório inteiro em `.zip` (ChatGPT com upload de arquivos)

Algumas IAs (como o ChatGPT, em contas que aceitam upload de arquivo) conseguem ler um `.zip` inteiro, o que evita ter que copiar arquivo por arquivo.

**Passo 1 — Baixar o repositório em `.zip`, sem precisar instalar Git:**

1. Acesse `https://github.com/ProjetoSistemas2026/disciplina`.
2. Clique no botão verde **Code** → aba **Local** → **Download ZIP**.
3. Isso baixa o repositório inteiro compactado, sem precisar de nenhum comando.

**Passo 2 — Enviar para a IA:**

1. Abra o chat da IA e use o botão de anexar/enviar arquivo.
2. Envie o `.zip` baixado.
3. Na mensagem, cole o conteúdo de `tutor-ia/PROMPT_BASE.md` (copie do GitHub, como na Opção B) e diga à IA para seguir esse comportamento usando os arquivos do `.zip` enviado.
4. Informe em qual unidade/semana você está, para a IA focar no material certo.

**Atenção:** este `.zip` é o repositório `disciplina` (conteúdo da disciplina), **nunca** o seu repositório pessoal de entregas. Não anexe suas atividades resolvidas para pedir a resposta pronta — o objetivo é estudar, não terceirizar a atividade.

---

## 5. Opção D — Modelo gratuito via OpenRouter

O [OpenRouter](https://openrouter.ai) reúne vários modelos de IA em um único chat, incluindo modelos com uso **gratuito** (marcados com `:free` no nome do modelo).

1. Crie uma conta gratuita em [openrouter.ai](https://openrouter.ai).
2. Acesse o [Chat do OpenRouter](https://openrouter.ai/chat).
3. Escolha, na lista de modelos, um marcado como gratuito (`:free`).
4. Cole o conteúdo de `tutor-ia/PROMPT_BASE.md` na primeira mensagem, seguido do material da semana — igual à Opção B.

Modelos gratuitos costumam ter limite de mensagens por dia. Se atingir o limite, tente outro modelo `:free` da lista ou volte no dia seguinte.

---

## 6. Opção E — GitHub Copilot Chat (dentro do VS Code)

Se você usa o [VS Code](https://code.visualstudio.com/) com a extensão **GitHub Copilot Chat** (tem plano gratuito limitado para estudantes e uso pessoal):

1. Abra a pasta `disciplina` no VS Code (`Arquivo → Abrir Pasta`).
2. Abra o painel do Copilot Chat.
3. Referencie os arquivos diretamente na conversa, usando `#`, por exemplo:
   ```
   #tutor-ia/PROMPT_BASE.md assuma esse papel.
   #unidades/unidade01/semana01/AULA.md me ajude a entender esta aula.
   ```
4. O Copilot lê o conteúdo dos arquivos referenciados automaticamente, sem precisar colar manualmente.

---

## 7. Qual opção escolher?

| Você quer... | Use |
|---|---|
| Já tenho Claude Code ou posso assinar | Opção A |
| Só quero algo grátis e simples, sem instalar nada | Opção B |
| Quero levar o repositório inteiro de uma vez | Opção C |
| Quero algo grátis sem depender de um único provedor | Opção D |
| Já uso VS Code no dia a dia | Opção E |

Todas as opções dão acesso ao **mesmo** Tutor MentorPS — a diferença é só a conveniência de cada ferramenta. Use a que for mais fácil para você.

---

## 8. Regras que valem em qualquer opção escolhida

- O Tutor IA **não resolve a atividade por você** — o prompt em `tutor-ia/PROMPT_BASE.md` proíbe isso explicitamente. Se a IA entregar a resposta pronta, ela não está seguindo o papel corretamente — reforce o prompt ou avise o professor.
- Nunca envie suas atividades resolvidas para uma IA pedindo a "resposta certa" antes de entregar — isso vai contra o [Código de Conduta](CODIGO_DE_CONDUTA.md) da disciplina.
- O conteúdo que você carrega deve ser sempre o já publicado no repositório `disciplina` — não peça à IA para "adiantar" unidades futuras.

---

## 9. Ainda com dúvida?

Pergunte ao Tutor MentorPS mesmo — ele consegue te orientar sobre qual ferramenta usar, além do conteúdo da disciplina. Se preferir, procure o professor.
