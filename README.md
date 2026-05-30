# SZZ Obsidian Notes

Poznamky ke statnicim jsou psane jako Obsidian vault. Agent pri zpracovani pouziva PDF podklady pres MCP a vystupy uklada jako Markdown do slozek predmetu.

## Potrebne MCP servery

### PDF MCP

Repo: <https://github.com/jztan/pdf-mcp>

Instalace:

```bash
pip install 'pdf-mcp[semantic]'
```

Registrace do Codexu:

```bash
codex mcp add pdf-mcp -- pdf-mcp
```

### Obsidian MCP

Obsidian musi mit dostupny MCP endpoint na lokalni adrese `http://127.0.0.1:27123/mcp/`.

Token nastavte do promenne prostredi:

```bash
export OBSIDIAN_TOKEN='vas-token'
```

Registrace do Codexu:

```bash
codex mcp add obsidian \
  --url http://127.0.0.1:27123/mcp/ \
  --bearer-token-env-var OBSIDIAN_TOKEN
```

## Pravidla pro generovani poznamek

- Pouzivat pouze informace z PDF podkladu.
- Markdown vystupy ukladat primo do Obsidian vaultu.
- Matematiku psat v Obsidian LaTeXu: inline `$...$`, blokove `$$...$$`.
- Zdroje psat jako Obsidian wikilinky na PDF, napr. `[[akla_2023_09_15.pdf#page=15|AKLA s. 15]]`.
- Souvisejici temata propojovat pres `[[wikilinks]]`.
- `hex_compost.pdf` slouzi jako kontrola rozsahu a hloubky, predmetova PDF jsou autoritativni zdroj faktu.
