# Provozní připravenost

## Před produkcí
- Ověřený hostingový tarif, PHP a rozšíření, composer/build postup, vlastní DB, SSH/SFTP, cron a odchozí HTTPS k Fio.
- Nastavení subdomény a TLS až na cílovém hostingu; nezměnit veřejný web ani poštu.
- Webroot pouze public; tajemství a přílohy mimo něj. Žádné produkční credentials v Actions logu.
- Testovací prostředí a fiktivní data; oddělená konfigurace produkce.
- SMTP s ověřeným odesílatelem; zkušební pošta jen určenému testerovi.
- Denní šifrovaná záloha mimo produkční účet, klíč odděleně. Cíl RPO 24 hodin, RTO jeden pracovní den, ověřit obnovou.
- Jmenovaný správce a zástupce, aktualizace, postup při incidentu a výměně výboru.

## Vydání
Změna ve větvi, kontrola a testy, testovací nasazení, označené vydání. Před změnou databáze záloha a migrační plán. Vrácení kódu samo nevrací databázi. Po nasazení kontrola přihlášení, oprávnění, synchronizace a záloh.

## Testovací scénáře pro produkci
Zakázaný přímý přístup k členu/exportu/příloze, odebraná relace, obnova MFA, neplatné CSRF, uložené HTML jako text, import stejné bankovní transakce dvakrát, více měn, část platby, hromadná platba, vratka, výpadek Fio, opakování migrace a obnova zálohy.

## Co zatím není hotové
Backend, databáze, MFA, autorizace, integrace Fio, migrace skutečných dat, SMTP a nasazení na subdoménu. Nelze je nahradit statickým prototypem.
