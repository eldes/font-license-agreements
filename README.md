# Font License Agreements

Texto dos contratos de licença (EULA) das fontes da Eldes Studio, em Markdown.
Fonte única consumida por:

- **salander-agency-api** — gera o PDF do contrato na pasta de cada licenciado e
  serve o texto em `GET /eulas/:type/:locale`;
- **eldes-website-2021** — exibe os contratos em `/licenses/:slug` (via API);
- qualquer lugar onde as fontes sejam distribuídas (referência pública).

## Estrutura

```
{type}/{locale}.md
```

- `type`: `desktop`, `logotype`, `site`, `ebook`, `app`
- `locale`: `br` (português do Brasil), `pt` (português de Portugal), `en` (inglês)

Cada arquivo é o contrato **completo**, com a numeração escrita no próprio
markdown (`### 1.`, `#### 2.1`) — a numeração varia entre tipos (ex.: Logotype e
Site têm a seção 2.7 "Outros usos"). Itálico (`_texto_`) e negrito (`**texto**`)
são usados onde o contrato original os usa. Parágrafos em uma única linha.

## Convenções

- Aspas curvas (“ ”) em todos os idiomas.
- `br` segue o português do Brasil; `pt` segue o português de Portugal (AO90):
  "utilizador", "ficheiro", "descarregar", "cessação" etc.
- Termo definido para a fonte: "Fonte" (pt/br) e "Font" (en); "Web-fonte"/"Web-font" no tipo `site`.
- Mudanças de texto vão num PR/commit próprio e entram no `CHANGELOG.md`;
  releases são tags `vX.Y.Z` (os consumidores fixam uma tag).

## Versões

Cada release é uma tag `version-X.Y.Z` (mesmo padrão dos outros repositórios), valendo para o
repositório inteiro. A versão **não** é escrita nos `.md`: a salander-agency-api a lê da tag que
estiver em `EULA_REF` e a mostra no rodapé do PDF e no cabeçalho `X-Eula-Version` de
`GET /eulas/:type/:locale` (o site a exibe no fim do contrato); a tag também fica registrada em cada
`Eula` gerada. Mudança de texto → entrada no `CHANGELOG.md` → tag nova → atualizar `EULA_REF`.

