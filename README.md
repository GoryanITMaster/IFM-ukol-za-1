# Věž -- textová dobrodružná hra

## O projektu

Tento projekt je jednoduchá textová adventura napsaná v Pythonu. Hráč se
probudí na nekonečné pláni a před sebou uvidí tajemnou věž. Během
průchodu věží bojuje s démony, získává zbraně a postupuje do dalších
pater. Hra obsahuje také několik tajných soubojů a zakončení.

## Požadavky

-   Python 3
-   Modul `random`, který je součástí standardní knihovny Pythonu

Není potřeba instalovat žádné další knihovny.

## Spuštění

Soubor je možné spustit například:

-   v prostředí Jupyter Notebook -- otevři soubor `.ipynb` a spusť buňku
    s kódem;
-   v běžném Pythonu -- po uložení kódu do souboru `.py` spusť tento
    soubor příkazem:

``` bash
python nazev_souboru.py
```

## Jak se hra hraje

Hra se ovládá zadáváním odpovědí do konzole.

Na začátku se hráč rozhodne, jestli vstoupí do věže. Pokud se dostane
dovnitř, může přijmout nebo odmítnout dýku od Starého muže. Přijetí dýky
umožní pokračovat ve hře.

V soubojích jsou dostupné tyto možnosti:

  Volba   Akce
  ------- ---------------
  `1`     Zaútočit
  `2`     Použít léčení
  `3`     Vzdát se

Hráč i démon mají vlastní počet životů (HP). Při útoku hráč způsobí
démonovi poškození a zároveň ztratí část vlastních životů. Léčení
obnovuje hráčovy životy a může obnovit i životy démona. Pokud hráči
klesnou životy na nulu, hra končí.

## Zbraně a předměty

-   **Dýka (`dagger`)** -- základní zbraň, kterou hráč získá od Starého
    muže.
-   **Blood dagger** -- náhodně nalezená zbraň, která přidává 10
    poškození při útoku.
-   **Tajny mec** -- tajný meč získatelný po souboji s bossem čtvrtého
    patra; přidává 20 poškození při útoku.
-   **Červené dítě** -- předmět související s jednou z tajných částí
    hry.

## Nepřátelé a obtížnost

Běžní nepřátelé jsou vybíráni náhodně ze seznamu:

  Démon           Počáteční HP
  ------------- --------------
  GORTH'MAK                 80
  Azgorith                 100
  Xul'varoth               120
  Ograthul                 150
  Baelzhar                 180
  Skar'morath              200

Kromě běžných démonů se ve hře objevují také speciální bossové. Jejich
životy jsou nastavené zvlášť podle konkrétního souboje.

## Postup hrou

1.  Hráč se probudí na pláni a rozhodne se, jestli vstoupí do věže.
2.  Při úspěšném otevření brány potká Starého muže.
3.  Po přijetí dýky postupuje přes jednotlivá patra a bojuje s démony.
4.  Ve čtvrtém patře čeká boss, po jehož poražení může hráč získat tajný
    meč.
5.  V dalších patrech hráč pokračuje až k finálnímu bossovi v desátém
    patře.
6.  Po vítězství může hráč zadáním tajného slova odemknout další
    speciální souboje a konce.

## Náhodné události

Hra používá modul `random` pro náhodné události. Například:

-   šance na otevření vstupní brány;
-   náhodný výběr běžného démona;
-   šance na nalezení Blood dagger;
-   šance na získání tajného meče po poražení bosse.

## Technické informace

Hlavní části programu:

-   `debil(text)` -- načítá číselnou volbu hráče a při nečíselném vstupu
    nastaví konec hry;
-   `fight_system(boss_hp=None)` -- zajišťuje souboje s běžnými
    nepřáteli i bossy;
-   `inventory` -- seznam získaných předmětů;
-   `enemies` -- slovník démonů a jejich počátečních životů;
-   `health` -- životy hráče;
-   `patro` -- aktuální patro věže;
-   `game_over` -- určuje, zda hra skončila.

## Poznámka

Hra je školní/projektová ukázka textové adventury. Některé náhodné
události a vysoká obtížnost jsou záměrnou součástí jejího návrhu.
