# ius-projekt1

## Zadání

Navrhněte informační systém pro upíří krevní banku. Krevní banka si zve své **dárce** k dalšímu odběru podle stavu krevní banky a data posledního odběru daného dárce. Každý takový dárce obdrží pozvánku na konkrétní pobočku krevní banky. V IS jsou uloženy informace, zda dárce na pozvánku zareagoval - dostavil se k odběru či nikoliv. Před vlastním odběrem dárce podstoupí test, zda mu může být odebrána krev, pokud je test v pořádku je dárci odebrána krev (**jedna dávka**), která dále musí znovu podstoupit test, z něhož se vyhodnotí její vhodnost ke konzumaci. Vzniklou dávku si u krevní banky mohou rezervovat různí **klienti**, o nichž je v databázi uložen záznam. Rezervace se provádí pro zadané množství dávek u pobočky, na které je materiál uskladněn, na určité datum.

## Diagramy

- [ ] Model případu užití
- [ ] ER diagram - **@Dast**
- [ ] Diagram tříd
- [ ] Sekvenční diagram
- [ ] Diagram komunikace
- [ ] Stavový diagram

## Entity

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
