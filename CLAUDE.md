# Dev blog — instruções do projeto

## Objetivo
Site pessoal minimalista hospedado no GitHub Pages, atualizado só via git (push → deploy).
Sem backend, sem serviços pagos.

## Stack
- Gerador de site estático: proponha no plano, com trade-offs e justificativa. Considere que
  no futuro o site pode receber notas estilo Obsidian com wikilinks (não implementar agora).
- Deploy: GitHub Actions → GitHub Pages
- JS no cliente: nenhum por padrão. Qualquer JS precisa de justificativa no plano.

## Estrutura de conteúdo
- `/` (home): lista de trabalhos recentes (PRs mergeados, contribuições)
  - Fonte dos dados: `data/work.yml`, atualizado manualmente
- `/blog`: posts e worklogs em Markdown, com data e tags

## Formato de data/work.yml
Campos por entrada: title, url, date (YYYY-MM), repo, summary (1 linha)

## Estilo visual — replicar Neovim (moonfly + render-markdown.nvim)
O site deve parecer um buffer markdown renderizado no Neovim com o colorscheme moonfly
e o plugin render-markdown.nvim. Estrutura (coluna única, listas simples) segue as referências:
- https://emre570.bearblog.dev/blog/
- https://ninoristeski.github.io/

### Tipografia
- Uma única fonte monospace em tudo: Noto Sans Mono, self-hosted (.woff2), só os pesos usados
- Largura máx. do texto: 90ch
- Sem serifa, sem fonte display

### Paleta (hex exatos do moonfly)
- Fundo: #080808
- Texto: #c6c6c6
- Texto secundário (datas, metadados): #626262
- Headings h1/h2: texto #8cc85f (mesmo verde dos links); h3: #79dac8
- Headings sem prefixo, ícone ou símbolo
- h2: faixa de fundo #303030 ocupando a largura inteira do container, sem borda nem raio
- Links: #8cc85f, sublinhado só no hover
- Código inline: texto #c6c684, sem fundo
- Blocos de código: fundo #121212, texto #c6c6c6
- Itálico e negrito: #e196a2
- Bullets: ● no 1º nível, ○ no 2º, cor #c6c6c6

### Regras
- Dark mode forçado, sem tema claro
- Proibido: sombras, gradientes, ícones decorativos (incluindo ícones Nerd Font),
  animações, bordas arredondadas, imagens de fundo

## Estilo de código
- HTML semântico, CSS puro sem framework, sem dependências desnecessárias
- Toda dependência nova precisa de justificativa antes de ser adicionada

## Regras de trabalho
- Antes de criar arquivos, apresente o plano e espere aprovação.
- Commits pequenos. Idioma e formato das mensagens: inglês e conventional commits
- Não escreva conteúdo de posts; crie só templates e um post de exemplo.
