# 🧛‍♀️ ius-projekt1

## 📚 Zadání

Navrhněte informační systém pro upíří krevní banku. Krevní banka si zve své **dárce** k dalšímu odběru podle stavu krevní banky a data posledního odběru daného dárce. Každý takový dárce obdrží pozvánku na konkrétní pobočku krevní banky. V IS jsou uloženy informace, zda dárce na pozvánku zareagoval - dostavil se k odběru či nikoliv. Před vlastním odběrem dárce podstoupí test, zda mu může být odebrána krev, pokud je test v pořádku je dárci odebrána krev (**jedna dávka**), která dále musí znovu podstoupit test, z něhož se vyhodnotí její vhodnost ke konzumaci. Vzniklou dávku si u krevní banky mohou rezervovat různí **klienti**, o nichž je v databázi uložen záznam. Rezervace se provádí pro zadané množství dávek u pobočky, na které je materiál uskladněn, na určité datum.

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
