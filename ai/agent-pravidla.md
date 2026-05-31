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
- Oblast: odborné okruhy
- Podklady: `EMPA/empa_complete_edition.pdf`, `ELD/Elektromagnetická vlna_13_5_2021.pdf`
- Kontrola rozsahu: `hex_compost.pdf`
- Zdrojový seznam otázek: `SZZ - Odborné okruhy.md`
- Otázky EMPA/ELD:
  13. Elektrické a magnetické pole a jeho zdroje; elektrostatika, Gaussova věta, metoda zrcadlení, energie a kapacita.
  14. Stacionární magnetické pole; Biotův-Savartův zákon, Ampérův zákon, energie, indukčnost, Faradayův zákon.
  15. Elektromagnetická vlna v neomezeném prostředí; Maxwellovy rovnice, typy vln, rozhraní, totální odraz, evanescentní vlna, polarizace odrazem.
  16. Vedené a evanescentní vlny; mody, impedance, fázová a skupinová rychlost, výkon, elementární zářiče, blízké/přechodné/vzdálené pole, anizotropní prostředí.

- V běžném českém textu vždy používat správnou gramatiku včetně háčků a čárek. Bez diakritiky psát jen tam, kde to vyžaduje technický identifikátor, název souboru, příkaz, kód nebo doslovný zápis z podkladů.
