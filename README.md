# CESEX

Interní administrativa odborné společnosti. Stav: interaktivní prototyp v0.1, pouze fiktivní data. Není určen pro skutečné osobní údaje ani provozní evidenci.

## Vyzkoušení
Stáhněte repozitář jako ZIP, rozbalte a otevřete `prototype/index.html` v prohlížeči. Prototyp nevyžaduje server, připojení ani instalaci. Úpravy jsou jen v paměti a po obnovení stránky zmizí. Nikam se neodesílají.

Obsahuje přehled, vyhledávání a filtrování členů, kartu člena, úpravu kontaktu, návrh ukončení členství, přehled plateb a ukázkovou diskusi.

## Dokumentace
- [Zadání a etapy](docs/PROJECT.md)
- [Architektura a bezpečnost](docs/ARCHITECTURE.md)
- [Migrace evidence](docs/MIGRATION.md)
- [Provoz a nasazení](docs/OPERATIONS.md)

## Ověření
`node --check prototype/app.js`

Produkční backend, přihlášení, oprávnění a napojení Fio ještě nejsou implementované. Ukázková role v prototypu není bezpečnostní mechanismus.

Repozitář byl při zahájení veřejný. Obsahuje výhradně obecnou dokumentaci a syntetická data; žádné členské exporty, identifikátory zdrojových tabulek či tajné klíče. Před vložením interních podkladů změnit na soukromý. Ani soukromý Git není úložištěm bankovních tokenů nebo členské databáze.
