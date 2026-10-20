# Architektura

Navržená produkce: modulární monolit PHP/Laravel + MySQL/MariaDB, serverové formuláře, plánované úlohy a SMTP. Konkrétní podporované verze vybrat po ověření hostingu. Současný statický prototyp slouží jen k ověření pracovních postupů.

Vrstvy: rozhraní → aplikační pravidla a oprávnění → databáze. Integrace Fio a pošty mají vlastní služby a oddělená tajemství. Provozní vrstva zajišťuje audit, zálohy, upozornění a aktualizace.

Entity: User, Role, Permission, Member, MembershipPeriod, MembershipChange, FeeAssessment, BankTransaction, PaymentAllocation, ImportRun, AuditEvent, DiscussionSection, Topic, Post, Attachment. Člen není uživatelský účet. Předpis není bankovní transakce. Alokace umožňuje více převodů na jeden předpis i jeden převod pro více členů. Peníze ukládat přesně v nejmenších jednotkách měny.

## Bezpečnostní minimum
- Pozvánky, vypnutá veřejná registrace, heslo + TOTP a jednorázové záložní kódy. Kontrolovaná obnova MFA.
- Kontrola oprávnění na serveru včetně exportů a příloh; deny by default. Žádná autorizace pouze v JavaScriptu.
- HTTPS, host-only Secure/HttpOnly/SameSite cookies, CSRF, escapování výstupu, validace, rate limiting a expirace relací.
- Odebrání účtu/role zneplatní relace. Správce infrastruktury má technicky přístup k datům; musí být důvěryhodný.
- Samostatné prostředí od veřejného webu, vlastní DB účet, tajemství mimo webroot/Git/logy.
- Audit změn, exportů a finančních oprav. Logy bez tokenů a celých bankovních odpovědí.
- Minimalizace osobních údajů, stanovený účel a retence, oprávnění zpracovatelů a proces oprav/výmazů před ostrým importem.

## Fio
Token Sledování účtu pouze na serveru. Denní synchronizace s překrývajícím se obdobím, unikátní klíč účet + ID transakce, zámek proti souběhu. Automaticky párovat pouze jednoznačný předpis s odpovídajícím VS, částkou a měnou. Ostatní do ruční kontroly; jméno samo není klíč. Vratky, hromadné a částečné platby řešit auditovatelnými alokacemi. Při nedostupnosti doplnit chybějící interval a pozastavit urgence. Hlídání expirace tokenu a posledního úspěchu. E-mail pouze upozornění, záloha importem výpisu se stejnou deduplikací.

Oficiální zdroje: https://www.fio.cz/docs/cz/API_Bankovnictvi.pdf ; https://laravel.com/docs ; https://www.cesky-hosting.cz/webhosting/parametry-webhostingu/
