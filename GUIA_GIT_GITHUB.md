# Guia de Git e GitHub

Este guia existe para que **ninguém fique perdido** usando Git e GitHub durante a disciplina. Ele parte do zero — não é necessário ter usado Git antes.

Se depois de ler este guia você ainda tiver dúvidas, pergunte ao Tutor IA ou ao professor. Não existe pergunta boba aqui: todo mundo começou sem saber.

---

## 1. Por que usamos Git e GitHub nesta disciplina

Git é a ferramenta que profissionais de desenvolvimento usam para registrar o histórico de tudo o que escrevem, e GitHub é o site onde esse histórico fica hospedado e acessível. Usamos os dois porque:

- é como equipes reais de desenvolvimento trabalham;
- seu histórico de commits (o que você fez, quando, e como evoluiu) faz parte da sua avaliação;
- é a forma como você recebe conteúdo novo (`git pull`) e entrega suas atividades (`git push`).

---

## 2. Instalação e configuração (fazer uma única vez)

### 2.1 Instalar o Git

- **Windows:** baixe em [git-scm.com](https://git-scm.com/download/win) e instale com as opções padrão.
- **Mac:** abra o Terminal e digite `git --version` — se não estiver instalado, o próprio sistema oferece a instalação.
- **Linux:** `sudo apt install git` (Ubuntu/Debian) ou equivalente da sua distribuição.

Para conferir se funcionou, abra um terminal e digite:

```bash
git --version
```

Deve aparecer um número de versão (ex: `git version 2.43.0`).

### 2.2 Criar sua conta no GitHub

Se ainda não tem, crie em [github.com](https://github.com). Anote seu **usuário do GitHub** — você vai precisar informar ele ao professor para ter acesso ao seu repositório pessoal.

### 2.3 Configurar seu nome e e-mail no Git

Isso identifica quem fez cada commit. Rode uma vez no terminal:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
```

### 2.4 Autenticação com o GitHub

Ao fazer `git push` pela primeira vez, o Git vai pedir para você autenticar. A forma mais simples:

- Instale o [GitHub CLI](https://cli.github.com/) e rode `gh auth login`, seguindo as instruções na tela; **ou**
- Use um **Personal Access Token** no lugar da senha quando o Git pedir (Configurações do GitHub → Developer settings → Personal access tokens).

Se travar nessa etapa, é o momento mais comum de pedir ajuda — não perca tempo tentando sozinho por muito tempo.

---

## 3. Os dois repositórios que você vai usar

Durante a disciplina você trabalha com **dois repositórios diferentes**, em duas pastas separadas no seu computador. Não misture os dois.

| Repositório | O que é | O que você faz nele |
|---|---|---|
| `disciplina` | Conteúdo oficial da disciplina (aulas, atividades, desafios) | Só **leitura** — você atualiza com `git pull` |
| `SEU-USUARIO` (seu repositório pessoal) | Onde você entrega suas atividades | Você **escreve** — `git add`, `git commit`, `git push` |

Você recebe o link do seu repositório pessoal do professor depois que ele cria seu acesso.

### 3.1 Clonar os dois repositórios (fazer uma única vez)

Escolha uma pasta no seu computador para guardar os dois (ex: `Documentos/projeto-de-sistemas/`) e rode:

```bash
# 1. Material da disciplina — você vai atualizar isso toda semana
git clone https://github.com/ProjetoSistemas2026/disciplina.git

# 2. Seu repositório pessoal — troque SEU-USUARIO pelo seu usuário do GitHub
git clone https://github.com/ProjetoSistemas2026/SEU-USUARIO.git
```

Depois disso você terá duas pastas, uma ao lado da outra:

```
projeto-de-sistemas/
  disciplina/         → material, você só lê
  SEU-USUARIO/         → suas entregas, você escreve aqui
```

---

## 4. O ciclo semanal, comando por comando

### Passo 1 — Atualizar o conteúdo da disciplina

Toda semana, antes de estudar, entre na pasta `disciplina` e atualize:

```bash
cd disciplina
git pull
```

Isso baixa qualquer conteúdo novo publicado pelo professor. Se aparecerem arquivos novos ou alterados, é o material da semana.

### Passo 2 — Estudar e resolver a atividade

Leia a aula e resolva a atividade e o desafio (veja [COMO_ESTUDAR.md](COMO_ESTUDAR.md) para o roteiro completo). Você faz isso normalmente, fora do Git — o Git só entra na hora de entregar.

### Passo 3 — Escrever sua entrega no repositório pessoal

Entre na pasta do seu repositório pessoal, na subpasta da semana correspondente:

```bash
cd ../SEU-USUARIO/entregas/unidade01/semana01
```

Coloque ali os arquivos da sua atividade (código, respostas, diagramas, o que for pedido).

### Passo 4 — Ver o que mudou

Antes de enviar, é sempre bom conferir o que você alterou:

```bash
git status
```

Isso mostra, em vermelho, os arquivos novos ou modificados que ainda não foram registrados.

### Passo 5 — Adicionar os arquivos (`add`)

```bash
git add .
```

O `.` significa "todos os arquivos modificados nesta pasta". Isso não envia nada ainda — apenas prepara o que vai ser registrado no próximo passo.

### Passo 6 — Registrar o commit

Um commit é um "registro" do que você fez, com uma mensagem explicando:

```bash
git commit -m "Atividade semana 01: resolução do exercício de modelagem"
```

Dicas para a mensagem do commit:
- descreva **o que foi feito**, não "atividade pronta" ou "final";
- pode (e deve) fazer vários commits pequenos ao longo do processo, não só um no final — isso mostra sua evolução, que faz parte da avaliação.

### Passo 7 — Enviar para o GitHub (`push`)

```bash
git push
```

Isso envia seus commits para o seu repositório no GitHub. Só depois desse passo o professor consegue ver o que você fez.

### Resumo do ciclo de entrega

```bash
git add .
git commit -m "mensagem descrevendo o que foi feito"
git push
```

Repita esses três comandos sempre que quiser salvar um progresso — não é preciso esperar terminar a atividade inteira para commitar.

---

## 5. Como confirmar que sua entrega chegou

Depois do `git push`, acesse `https://github.com/ProjetoSistemas2026/SEU-USUARIO` no navegador e confira se os arquivos e commits aparecem lá. Se aparecer, a entrega chegou até o professor — não é necessário enviar por nenhum outro meio.

---

## 6. Erros comuns e como resolver

### "fatal: not a git repository"
Você não está dentro de uma pasta clonada com Git. Confira com `pwd` (Mac/Linux) ou `cd` sem argumento (Windows) se você está dentro da pasta `disciplina` ou `SEU-USUARIO`, e não uma pasta acima ou abaixo dela por engano.

### "Please tell me who you are" (ao commitar)
Você pulou a configuração da seção [2.3](#23-configurar-seu-nome-e-e-mail-no-git). Rode os dois comandos `git config --global` e tente de novo.

### `git push` pede usuário e senha e nada funciona
O GitHub não aceita mais senha comum no `git push`. Configure a autenticação como descrito na seção [2.4](#24-autenticação-com-o-github).

### "Updates were rejected because the remote contains work that you do not have locally"
Isso normalmente acontece se você editou o repositório pelo próprio site do GitHub, ou está usando dois computadores. Rode:

```bash
git pull
```

antes do `git push`, para trazer as mudanças remotas primeiro.

### Enviei no repositório errado (ex: entreguei dentro de `disciplina` por engano)
Pare, não force nada. Copie os arquivos que você criou para a pasta correta dentro do seu repositório pessoal (`SEU-USUARIO/entregas/...`) e refaça o `add`/`commit`/`push` lá. Avise o professor se já tiver dado `push` no lugar errado.

### Esqueci de dar `pull` em `disciplina` e a atividade que estou vendo está desatualizada
Rode `git pull` dentro da pasta `disciplina` antes de continuar. Nunca edite arquivos dentro da pasta `disciplina` — ela é somente leitura para você.

### Não sei se meu commit foi enviado
Rode `git status` — se aparecer "Your branch is up to date with 'origin/main'" (ou similar), está tudo enviado. Se aparecer algo como "ahead by N commits", ainda falta dar `git push`.

---

## 7. Glossário rápido

| Termo | Significado |
|---|---|
| Repositório (repo) | Uma pasta com histórico de versões controlado pelo Git |
| Clone | Copiar um repositório do GitHub para o seu computador |
| Commit | Um registro de uma mudança, com uma mensagem explicando o que foi feito |
| Push | Enviar seus commits do seu computador para o GitHub |
| Pull | Baixar mudanças do GitHub para o seu computador |
| Status | Ver o que mudou e o que ainda falta enviar |
| Remoto (remote) | A cópia do repositório que fica no GitHub (em oposição à cópia local, no seu computador) |

---

## 8. Ainda com dúvida?

1. Releia a seção correspondente deste guia.
2. Pergunte ao Tutor MentorPS, descrevendo exatamente a mensagem de erro que apareceu.
3. Procure o professor, levando o print da mensagem de erro.

Trave em Git é normal no início. Faz parte do processo — não é sinal de que você não é capaz.
