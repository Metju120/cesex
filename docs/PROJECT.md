# Zadání v0.2

## Cíl
Jedna spravovaná evidence členů a příspěvků, pracovní prostor výboru, revizní komise a sekretářky. Zdrojový kód na GitHubu, provoz samostatně na hostingu. Existující tabulka zůstává závaznou evidencí do řízeného přechodu.

## Rozsah první produkční verze
Pozvánky a MFA, členské karty, historie kontaktů a členství, roční předpisy, ruční úhrady, oprávnění a audit, náhled importu a řízený export. Ukončení členství ukládá datum, důvod a rozhodnutí. Neplacení neukončuje členství automaticky.

## Role (návrh)
Sekretářka: kontakty a evidence, návrh párování. Pověřený člen výboru: opravy a zápis rozhodnutí. Výbor: přehledy a diskuse. Revizní komise: čtení potřebných záznamů a historie. Správce: správa účtů, nikoli automaticky pravomoc rozhodovat o členství. Export je samostatné oprávnění. Práva a oddělení diskusních sekcí potvrdit před implementací.

## Etapy a přijetí
1. Prototyp: ověřit seznam, kartu, platby, diskusi na fiktivních datech.
2. Hosting: potvrdit oddělení prostředí, PHP, databázi, cron, SSH, SMTP, TLS a zálohy.
3. Evidence: serverové oprávnění na každé operaci, MFA a odebrání relací; zkušební import souhlasí se zdrojem.
4. Fio: pouze čtení, deduplikace, výjimky, odolnost po výpadku, audit oprav.
5. Diskuse: kontrola členství sekce i u přímého odkazu na přílohu.
6. Pilot: kontrola počtů a součtů, zkouška obnovy, lidský správce a zástupce, návod.

Další funkce: zápisy a usnesení, úkoly, mandáty a předání přístupů, exporty mezinárodním organizacím, podklady výroční zprávy, platební QR. Hromadné zprávy zapnout samostatně po schválení adresátů a obsahu. Tajné volby nejsou anketa v diskusi.

Bez ověření tarifu a migračních pravidel nezávazně odhadovat termín ani cenu. Rozpočet musí zahrnout údržbu, nikoli jen vývoj. Asistent provádí práci v pracovních relacích; nepředstavuje nepřetržitou provozní službu.
