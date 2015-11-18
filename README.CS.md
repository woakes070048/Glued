# Glued

Glued je online ERP systém vyvinutý specificky pro nestátní neziskové organizace (NNO). Systém je implementovaný v PHP do stavu funkčího prototypu, jehož další vývoj nedává pro množství ústupků / špinavých hacků smysl. 
Následující fází by proto měl být kompletní přepis systému do architektury propojených mikroslužeb/blackboxů.

S tvojí pomocí se může Glued stát jednou z nejdůležitějších věcí pomáhající dobročinnosti po celém světě.
Pokud jsi chtěl někdy kopat za dobrou věc, tohle je tvoje šance :)

## VLASTNOSTI

 - issue tracking systém
 - wiki
 - databáze kontaktů (podobná Google contacts)
 - kanban nástěnky (podobné Trellu)
 - seznam úkolů / checklist (podobný Basecamp)
 - nehierarchický sklad dokumentů (místo adresářové hierarchie štítky/tagy)
 - rezervace zdrojů (lidí, lidí s konkrétní dovedností, věcí, služeb, apod.)*
 - nabízení dílčích úkolů lidem na základě shody s jejich zájmy* (dovednosti osob vs. požadované dovedností k dokončení práce)
 - účetnictví a bankovnictví*
 - notifikace
 - kalendář, plánování, organizace
 - šablony osvědčených postupů - best practices (integrace seznamu úkolů, wiki, databáze kontaktů a základní BPM - Business Process Management)
 - diskusní fóra
 - CMS - systém správy obsahu
 - interní version control

*) částečně implementováno

## PLÁNOVANÉ VLASTNOSTI

 - integrace e-mailu
 - e-mailové skupiny
 - integrace sociálních medií
 - mobilní aplikace
 - crowdfundingová platforma
 - IoT integrace (Glued jako server pro sběr dat z IoT zařízení)


## TECHNICKÉ HLEDISKO REIMPLEMENTACE

 - architektura založená na mikroslužbách (Glued implementovaný jako sada propojených černých skříněk komunikující přes API)
 - základní implementace sestávající z
   - základní Glued služby (udržuje přehled o dostupných/připojených službách, zapíná/vypíná ladicí režim, měří výkon, ...)
   - společné Glued knihovny (společné funkce, mezipaměť, autorizace, směrování URL, mezislužbová komunikace - REST API + ZeroMQ API)
   - autentikační služba
   - služba oznámení/push notifikací 
   - služba souborového serveru / úložiště
   - referenční "hello world" funkční služba
 - funkční služby (issue tracking systém, CMS, kalendář, databáze kontaktů, ...)
 - mashup služba (CMS komponenta umožňující sloučení více funkčních služeb na jedné URL adrese)

Z důvodu zrychlení práce je možné použít pro každou komponentu jiné paradigma (např. funkcionální vs. objektově
orientované programování) nebo i jiný programovací jazyk, dokud bude možné s každou službou komunikovat 
přes verzované a jazykově nezávislé API (https REST API + výkonové SASL+ZeroMQ API), které bude pokryté unit testy. 
Cílem je přepis komponent tam, kde je to třeba a nemuset vždy znovu vynalézat kolo. 
Použití neexotických závislostí je vítáno.

## CO JE TŘEBA UDĚLAT

 - návrh architektury týkající se reimplementace mikroslužeb (co je třeba nechat centralizované a co rozdrobit na služby)
 - vytvořit základní fungující reimplementaci
 - UX návrh funkčních služeb
 - import použitelného kódu z funkčních služeb
 - nastavit CI (continuous integration)
 - nastavení licencování (nejliberálnější opensource licence a respektování použitého kódu třetích stran)
 - distribuce (packaging)
 - intenacionalizace / překlady
 - distribuce jako Docker kontejner pro SaaS (Software as a service) aplikace


## VÝZVA K AKCI

Hledáme

 - vývojáře
 - softwarové architekty
 - release managery a správce repozitáře
 - UX designery
 - experty na frontend

aby nám pomohli začít s přepisem. Je to prima příležitost podílet se na důležitém opensource projektu od jeho 
úplného začátku.

Prvotní setkání v Brněnské Industře, hlasuj pro nejlepší datum a čas:  http://doodle.com/poll/538xdqyn82xb5f7v

## PROČ GLUED

Glued byl vyvinut s cílem nabídnout NNO state-of-the-art nástroj pro správu jejich činnosti. Cílem Glued je poskytnout 
uživatelsky přívětivý nástroj, který odstíní spoustu činností spojených s provozem NNO a umožní jim soustředit se na 
to, co dělají nejlépe: správnou věc.

Glued byl navržen a testován na reálné NNO. Žádné NNO nebylo během tohoto procesu ublíženo.

