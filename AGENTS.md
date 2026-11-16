# docs

Documentação pública da Campos Cloud (docs.camposcloud.com), feita com Mintlify.

## Estrutura
- `docs.json`: tema, cores e **navegação**. Toda página nova precisa entrar aqui, senão não aparece.
- `index.mdx` e as páginas `.mdx` de guias.
- `api-reference/`: introdução, autenticação, limites, e `openapi.json`, que gera as páginas de endpoint (`api-reference/endpoint`).
- `sdk/javascript`, `sdk/python`: documentação dos SDKs.

## Comandos
- `mint dev` — prévia local (CLI: `npm i -g mint`).
- `mint broken-links` — conferir links quebrados antes de subir.

## Cuidados
- O `openapi.json` precisa refletir a API real do camposcloud-control. Mudou um endpoint lá? Atualize aqui na mesma rodada, com PRs citando um ao outro.
- O mesmo vale para o SDK (camposcloud-sdk) e as páginas em `sdk/`.

## Fluxo de trabalho (obrigatório)
- Toda modificação numa worktree própria:
  `git fetch origin && git worktree add -b <tipo>/<assunto> .claude/worktrees/<assunto> origin/main`.
  Nunca editar o checkout principal nem commitar na `main`.
- Um assunto por branch.
- Antes de subir: `mint broken-links` e uma olhada na prévia.
- Push da branch → PR para `main` (rascunho enquanto não estiver pronto) → revisão (`/code-review`) → correções. **Quem faz o merge na `main` é o Vitor**; agentes nunca fazem merge, push na `main` nem force-push.
