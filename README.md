# Repositório remoto em dupla: branches, pull requests e merge

> Exercício de Git em dupla com repositório no GitHub, duas branches de feature e nove pull requests.

**Contexto:** IFAC · Técnico em Informática para Internet (TIPI) · Web Academy · 2023

## Sobre

Atividade da Web Academy, feita em 14 de agosto de 2023, para praticar o trabalho com um repositório remoto compartilhado. Cada integrante da dupla trabalhou numa branch própria, abriu pull requests para a `main` e fez o merge pelo GitHub. A cada rodada as duas branches eram mescladas de novo na `main`, e um dos commits foi registrado com coautoria.

Os arquivos `.txt` não têm conteúdo útil: servem só para gerar mudanças, commits e conflitos.

## Funcionalidades

O que o histórico mostra:

- **Branches de feature:** `feature-1` (Diego) e `feature-2` (Jânio), ambas ainda publicadas no remoto.
- **Pull requests:** nove PRs mesclados na `main`, intercalando as duas branches (tabela abaixo).
- **Trabalho em paralelo:** as duas branches avançam ao mesmo tempo e são mescladas várias vezes; o `arquivo1.txt` termina com uma linha de cada integrante ("Kelme fez essa linha." / "Jânio fez essa linha.").
- **Coautoria:** o commit `63fec92` (v5) usa o trailer `Co-authored-by` para creditar os dois autores.
- **Correção de nome de arquivo:** na `feature-2`, `aqruivo-1.txt` foi criado com erro de digitação e renomeado para `arquivo-1.txt` num commit posterior (`944e7a2`).

| PR | Branch | Autor |
|---|---|---|
| #1, #3, #6, #8, #9 | `feature-1` | @itskelme |
| #2, #4, #5, #7 | `feature-2` | @j4nio |

## Tecnologias

- Git
- GitHub (pull requests, merge pela interface web, coautoria)

## Estrutura do projeto

| Caminho | Descrição |
|---|---|
| `text.txt` | Primeiro arquivo, criado direto na `main` antes das branches. |
| `arquivo1.txt` | Alterado na `feature-1`; recebe linhas dos dois integrantes. |
| `arquivo-2.txt` | Alterado na `feature-2`. |
| `arquivo-1.txt` | Criado na `feature-2` (antes `aqruivo-1.txt`). |

## Como rodar

### Pré-requisitos

- Git
- Conta no GitHub (para repetir o exercício com PRs)

### Passo a passo

```bash
git clone https://github.com/itskelme/ifac-tipi-webacademy-repo-remoto.git
cd ifac-tipi-webacademy-repo-remoto

# traz as branches de feature
git fetch origin
git branch -a
```

## Como usar

Para estudar o histórico:

```bash
# grafo com as duas branches e os merges
git log --graph --oneline --all

# commit com coautoria
git show 63fec92

# só os merges que entraram na main, em ordem
git log --oneline --first-parent main

# histórico de cada branch
git log --oneline origin/feature-1
git log --oneline origin/feature-2
```

Os pull requests podem ser vistos em https://github.com/itskelme/ifac-tipi-webacademy-repo-remoto/pulls?q=is%3Apr+is%3Aclosed ou com `gh pr list --state all -R itskelme/ifac-tipi-webacademy-repo-remoto`.

Para refazer o exercício em dupla:

1. Uma pessoa cria o repositório no GitHub e adiciona a outra como colaboradora.
2. Cada uma cria sua branch: `git switch -c feature-1` (ou `feature-2`).
3. Altere um arquivo, faça `git add`, `git commit` e `git push -u origin feature-1`.
4. Abra um pull request para a `main` no GitHub e faça o merge.
5. Antes de continuar, atualize a branch com `git pull origin main` e resolva os conflitos que aparecerem.
6. Para registrar coautoria, termine a mensagem do commit com `Co-authored-by: Nome <email>`.

## Referências

- [Pro Git (em português)](https://git-scm.com/book/pt-br/v2), capítulos 3 (Branches) e 5 (Git distribuído)
- [GitHub Docs: sobre pull requests](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
- [GitHub Docs: resolver conflitos de merge](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line)
- [GitHub Docs: commits com vários autores](https://docs.github.com/pt/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/creating-a-commit-with-multiple-authors)

## Autores

- Diego Kelme Santos da Silva — [@itskelme](https://github.com/itskelme)
- Jânio — [@j4nio](https://github.com/j4nio) (branch `feature-2` e coautoria do commit v5)

## Licença

Este projeto está sob a licença [CC BY-NC 4.0](LICENSE): uso pessoal e modificação permitidos com atribuição; uso comercial proibido.
