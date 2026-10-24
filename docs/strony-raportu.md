# Strony raportu

Każda strona ma tytuł-wniosek (IBCS). Nawigacja: Page navigator w nagłówku każdej strony, przycisk „ⓘ Metodologia” i przycisk powrotu na stronach ukrytych.

## Start

![Start: tytuł raportu, autor, panele „Jak czytać kolory” i „Co możesz zrobić”, rower SVG jako przycisk wejścia](../img/01_start.png)

**Tytuł:** Lipiec 2007: jak nowa oferta odwróciła spadek sprzedaży
- autor,
- panel „Jak czytać kolory”,
- panel „Co możesz zrobić”,
- duży rower SVG jako przycisk wejścia do raportu.

## 1. Przełom

![1. Przełom: rok 2007/2008 wybrany w slicerze, 4 karty KPI z r/r, trend miesięczny z bursztynowym lipcem 2007 i adnotacją o nowej ofercie](../img/02_przelom.png)

**Tytuł:** Lipiec 2007: nowa oferta odwróciła spadek sprzedaży
**Cel:** pokazać problem (spadek w 2006/2007) i zwrot (wzrost w 2007/2008).
- 4 karty KPI: przychód, zysk, marża, klienci, każda ze zmianą r/r w kolorze,
- Button slicer roku obrotowego, który steruje **tylko kartami**,
- trend miesięczny z wyróżnionym VII 2007 i adnotacją,
- AC vs PY wg roku obrotowego: nakładane słupki IBCS, etykieta Detail z % r/r,
- klienci vs przychód na klienta.

## 2. Źródła wzrostu

![2. Źródła wzrostu: kraje AC vs PY (USA +282%, Australia +109%), ranking TOP 5 podkategorii wg przyrostu i struktura przychodu do drill-down](../img/03_zrodla_wzrostu.png)

**Tytuł:** Wzrost napędziły rowery i rynek USA
**Cel:** pokazać, gdzie powstał przyrost (kraje, podkategorie).
- kraje AC vs PY,
- ranking TOP N podkategorii wg przyrostu: Button slicer TOP 3/5/8/10, dynamiczny tytuł i podtytuł,
- drill-down Kategoria → Podkategoria → Produkt,
- ikona ⓘ z instrukcją.

## 3. Koszyk

![3. Koszyk, widok Liczby: karty 89% / 50% / 949 / 8 786, segmenty 949 / 7 677 / 8 786, kraje wg klientów bez roweru, rekomendacja z rowerem wypełnionym w 50%](../img/04_koszyk_liczby.png)

![3. Koszyk, widok Procenty: te same segmenty jako 5% / 44% / 50%](../img/05_koszyk_procenty.png)

**Tytuł:** Połowa klientów kupuje tylko dodatki
**Cel:** pokazać cross-selling i grupę docelową rekomendacji.
- 4 karty: 89%, 50%, 949, 8 786,
- segmenty klientów z przełącznikiem **Liczby / Procenty** (bookmarki),
- kraje wg liczby klientów bez roweru,
- rekomendacja i rower SVG wypełniony w 50%.

## 4. Klienci

![4. Klienci: segmenty wg stanu cywilnego, grupy wiekowej i liczby dzieci (słupki 100%), piktogram płci 49% vs 52% i persona kampanii](../img/06_klienci.png)

**Tytuł:** Bez roweru zostają najmłodsi, najstarsi i duże rodziny
**Cel:** opisać, do kogo kierować kampanię.
- 100% słupki segmentów wg grupy wiekowej, liczby dzieci i stanu cywilnego,
- piktogram płci,
- persona „Do kogo kierować kampanię rowerową”.

## Szczegóły kraju (ukryta, drill-through)

![Szczegóły kraju dla Kanady: KPI, pozycja 6 z 6 rynków, udział 7%, segmenty 3% / 34% / 63%, trend, ranking TOP 5 i rekomendacja z rowerem SVG](../img/07_szczegoly_kraju.png)

**Tytuł:** dynamiczny, „Szczegóły: [kraj]”
- KPI kraju, pozycja wśród 6 rynków, udział w przychodzie,
- segmenty, trend, ranking,
- rekomendacja i rower SVG (np. Kanada 63%).

Wszystkie tytuły na tej stronie są dynamiczne.

## Nota metodologiczna (ukryta)

![Nota metodologiczna: lista założeń (kwoty netto, okres, porównania r/r, segmenty, wiek, brak numeru zamówienia, obszar sprzedaży)](../img/08_metodologia.png)

Założenia: netto / 8% / € umowne, okno VII 2005–VI 2008, rok obrotowy, segmenty w 2007/2008, wiek na 30.06.2008, brak numeru zamówienia, obszar sprzedaży. Pełny opis: [metodologia.md](metodologia.md).

## Mapa wymagań zaliczenia

| Wymaganie | Gdzie |
|---|---|
| CALCULATE | większość miar |
| Time Intelligence | `SAMEPERIODLASTYEAR` (folder 2) |
| 39 miar | `_Miary` |
| Drill-down | str. 2, Kategoria → Podkategoria → Produkt |
| Drill-through | Szczegóły kraju |
| Bookmarki | str. 3, Liczby / Procenty |
| Parametr | TOP N (str. 2) |
| Niestandardowe etykiety | etykieta Detail z % r/r (str. 1) |
| Dynamiczne obiekty | miary `A` (teksty) i `C` (kolory) |
| Niestandardowe wizualizacje | miary SVG (rower, piktogram) |
| Nawigacja i przyciski | Page navigator, Metodologia, powrót |
| IBCS | tytuły-wnioski, AC/PY, kolory odchyleń |
| Tooltipy | dopracowane albo wyłączone na każdej wizualizacji |

![Przykład tooltipa na wykresie grup wiekowych: grupa 45–54, rower + dodatki 2 179 (46,17%)](../img/09_tooltip.png)
