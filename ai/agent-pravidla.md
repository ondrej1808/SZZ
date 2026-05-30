# Pravidla pro tvorbu skript na státnice

- Výstupy ukládat jako Markdown do Obsidian vaultu.
- Struktura vaultu:
  - `ai/` pro interní logování, kontext a pracovní wiki agenta.
  - Složka pro každý předmět, ve které budou zpracované otázky.
- Používat pouze informace z PDF serveru a z PDF podkladů dodaných ve složce daného předmětu. Nevymýšlet informace mimo podklady.
- `hex_compost.pdf` používat jako kontrolní kompas rozsahu a očekávané hloubky pro studenta mířícího na B; faktické definice ověřovat proti předmětovým PDF.
- Cílit na úroveň B: přesné definice, podmínky použití a hlavní výpočetní postupy; nepřetěžovat důkazy, pokud nejsou pro pochopení nutné.
- Související témata propojovat pomocí `[[wikilinks]]`.
- Ke každé sekci uvádět zdroj jako Obsidian wikilink na PDF, např. `[[akla_2023_09_15.pdf#page=15|AKLA s. 15]]`. Pokud je vhodné uvést kontrolní kompost, také přes wikilink, např. `[[hex_compost.pdf#page=4|HEX s. 4]]`.
- Matematiku v poznámkách psát jako Obsidian LaTeX: inline `$...$`, samostatné vzorce blokově `$$...$$`. Nepoužívat textové code bloky pro rovnice.
- Pokud informace v podkladech není nalezena, explicitně to označit.

## Aktuální práce
- Předmět: KANA
- Podklady: `KANA/testkom.pdf`, `KANA/transformace.pdf`
- Zdrojový seznam otázek: `SZZ - Teoretické okruhy.md`
- Otázky KANA:
  9. Funkce komplexní proměnné a jejich derivace. Křivkový integrál. Singularity. Mocninné řady, Taylorovy a Laurentovy rozvoje. Rezidua, reziduová věta a její aplikace.
  10. Fourierovy řady, Fourierova a Laplaceova transformace - význam, gramatika, věty o inverzi. Přímá a zpětná transformace Z. Aplikace transformací na řešení diferenciálních a diferenčních rovnic.

- V běžném českém textu vždy používat správnou gramatiku včetně háčků a čárek. Bez diakritiky psát jen tam, kde to vyžaduje technický identifikátor, název souboru, příkaz, kód nebo doslovný zápis z podkladů.