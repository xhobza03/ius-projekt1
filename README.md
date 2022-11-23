# 🧛‍♀️ ius-projekt1

## 📚 Zadání

Navrhněte informační systém pro upíří krevní banku. Krevní banka si zve své **dárce** k dalšímu odběru podle stavu krevní banky a data posledního odběru daného dárce. Každý takový dárce obdrží pozvánku na konkrétní pobočku krevní banky. V IS jsou uloženy informace, zda dárce na pozvánku zareagoval - dostavil se k odběru či nikoliv. Před vlastním odběrem dárce podstoupí test, zda mu může být odebrána krev, pokud je test v pořádku je dárci odebrána krev (**jedna dávka**), která dále musí znovu podstoupit test, z něhož se vyhodnotí její vhodnost ke konzumaci. Vzniklou dávku si u krevní banky mohou rezervovat různí **klienti**, o nichž je v databázi uložen záznam. Rezervace se provádí pro zadané množství dávek u pobočky, na které je materiál uskladněn, na určité datum.

### Konzistence jednotlivých modelů

Všechny modely musí splňovat funkcionalitu a být konzistentní, to znamená mimo jiné:

- Názvy entitních a vztahových množin ER diagramu musí korespondovat se jmény v názvech a popisech případů užití.
- Ke každému případu užití musí existovat vhodné entitní množiny, se kterými se manipuluje: Například pokud mám případ užití *Zadat novou žádost*, musím mít v ER diagramu entitní množinu, která obsahuje údaje o zadaných žádostech.
- Naopak ke každé entitní množině by měl existovat případ užití, který přidá/mění/maže položky příslušné entitní množiny: Pokud mám například entitní množinu *Uživatel*, je nutnou součástí modelu případu užití možnost správy uživatelů.
- Názvy tříd a metod v diagramu tříd, sekvenčním diagramu a diagramu komunikace musí být v souladu.
- Ke každému případu užití musí existovat vhodná metoda v diagramu tříd, která tento UC provádí.
- Naopak každá metoda, která předpokládá uživatelský vstup, by měla odpovídat nějakému UC.
- Pokud je sekvence akcí iniciována nějakým případem užití, ten musí být v diagramu případu užití. Stejně tak každé volání metody musí odpovídat příslušné metodě v diagramu tříd.

## 📊 Diagramy

- [ ] Model případu užití - **@já**
- [ ] ER diagram - **@Dast**
- [ ] Diagram tříd - **@Nasťa**
- [ ] Sekvenční diagram - **@Kuba**
- [ ] Diagram komunikace - **@Kuba**
- [ ] Stavový diagram - **@Katy**

## 👺 Entity

- **dárce**
  - datum posledního odběru
  - reagoval na zprávu - _dostavil se/nedostavil se_
  - výsledek testu pro odběr - _krev může být odebrána/nemůže být odebrána_
- **dávka**
  - výsledek testu vhodnosti ke konzumaci
  - vztahy:
    - jsou odebrány **dárci**
- **klient**
  - vztahy:
    - tvoří **rezervace**
- **rezervace**
  - počet dávek
  - datum
- **pobočka**
  - počet dávek
  - vztahy:
    - uskladňují **dávky**

## 🙋‍♂️ Otázky

- *Odebírá si dávku sám dárce, či je na pobočce nějaký pracovník, který provede odběr a tudíž i zápis patřičných údajů do systému?*
  - Dávku odebírá pracovník, který se stará o vše.
- *Reakce na pozvánku znamená přijít samo o sobě, nebo musí prve dárce odpovědět na pozvánku?*
- *Znamená vhodnost pro konzumaci, že by dávka měla v systému být/nebýt, nebo je to jen nějaký atribut, který má být veden o dávce?*
