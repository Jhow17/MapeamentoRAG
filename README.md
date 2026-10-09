# Base de conhecimento Securiti (Shield Security)

Base da documentação oficial da Securiti em Markdown, usada como fonte para RAG e para as IAs da equipe. Uma base, vários projetos.

## Estrutura

- `00-geral/`: Getting Started, What's New, Release Notes gerais e Solution Briefs.
- `01-dspm/` a `06-platform/`: uma pasta por área do Help Center e, dentro, uma pasta por módulo.
- Dentro de cada módulo:
  - `guias/`: páginas de documentação (todo módulo tem)
  - `releases/`: só nos módulos que têm Release Notes
  - `api/`: só nos módulos que têm API Ref
- `_templates/modelo.md`: exemplo de arquivo pronto.
- `manifest.csv`: uma linha para cada arquivo salvo.

## Subpastas dentro de guias/

Dentro de `guias/`, crie uma subpasta para cada seção de primeiro nível do menu lateral do módulo, com o nome da seção em minúsculas, sem acento e com hífen. Exemplo: a seção "Using Enterprise Data Catalog" vira `guias/using-enterprise-data-catalog/`.

- Só o primeiro nível. Se a seção tiver subseções, as páginas delas vão para a pasta da seção de primeiro nível.
- Páginas soltas no menu, fora de qualquer seção, ficam direto em `guias/`.

Fora isso, não crie pastas novas. Se achar conteúdo que não se encaixa, anote na coluna `observacao` do manifest e avise.

## Passo a passo por página

1. Copiar a página em .md pelo Help Center.
2. Criar o arquivo na pasta da seção correspondente do menu com o nome igual ao `slug` do cabeçalho: `getting-started-with-enterprise-data-catalog.md`.
3. Colar o conteúdo sem alterar nada.
4. Acrescentar estas 4 linhas no fim do cabeçalho, antes do `---` de fechamento:
   ```
   area: governance
   modulo: enterprise-data-catalog
   tipo: guia
   data_captura: 2026-09-29
   ```
   - `area` e `modulo`: iguais aos nomes das pastas, sem o número.
   - `tipo`: `guia`, `api` ou `release`.
   - `data_captura`: dia em que copiou, formato AAAA-MM-DD.
5. Registrar o arquivo no `manifest.csv`.

## Regras

1. Um arquivo por página. Nunca juntar páginas.
2. Não resumir, não traduzir, não editar o conteúdo. Isso inclui imagens, links, tabelas e vídeos incorporados: fica tudo como veio. A limpeza será feita depois, por script.
3. Não apagar nem alterar os campos que já vêm no cabeçalho (`title`, `slug`, `updated`, `published`, `canonical`, `stale`).
4. Se a página exportada vier com texto faltando (por exemplo, FAQ com as respostas mas sem as perguntas), anotar em `observacao` no manifest. Não corrigir à mão.
5. API: se a página de API Ref permitir exportar o arquivo original (OpenAPI/JSON ou Postman collection), salvar esse arquivo na pasta `api/` do módulo com o nome original e registrar no manifest.
6. Releases: um arquivo por versão.
7. Videos e Interactive Demos não viram arquivo. Registrar só o link no manifest com `tipo` = `video`.
8. IaaS Connectors aparece em DSPM e em Integrations no site. Salvar só em `05-integrations/iaas-connectors/`.
9. Release Notes geral x por módulo: se a geral só repete o que está nos módulos, salvar só por módulo. Se tiver itens de plataforma que não aparecem nos módulos, salvar em `00-geral/release-notes/`.
10. Nada de print ou dado de ambiente de cliente. Só documentação oficial.
11. Os arquivos `.gitkeep` existem só para manter as pastas vazias no Git. Não apagar.

## Status no manifest

`pendente`, `feito`, `revisar`.
