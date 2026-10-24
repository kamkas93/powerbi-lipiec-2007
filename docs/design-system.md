# Design system

Motyw JSON: [`theme/Motyw_Rowery_Fiolet_v2.json`](../theme/Motyw_Rowery_Fiolet_v2.json), nazwa „Rowery – Fiolet IBCS v2”.

## Kolory i ich role

| Kolor | Hex | Rola |
|---|---|---|
| ciemny fiolet | `#4B3F72` | wartości bieżące (AC) |
| szary liliowy | `#B9B3C9` | rok poprzedni (PY), tło porównania |
| bursztyn | `#E0A43A` | **jedyny akcent**: VII 2007, klienci kupujący tylko dodatki |
| zielony | `#2E9E7A` | odchylenie dodatnie |
| czerwony | `#C8463D` | odchylenie ujemne |
| tekst | `#2B2833` | tekst główny |
| tekst pomocniczy | `#5E5A66` | podtytuły, etykiety |
| tło strony | `#F4F3F7` | tło płótna |

Zielony i czerwony mają różną jasność, więc da się je odróżnić także przy zaburzeniach widzenia barw.

<!-- ![Panel „Jak czytać kolory”](../assets/svg/Panel_kolory.svg) -->

Panel „Jak czytać kolory” ze strony Start: [`assets/svg/Panel_kolory.svg`](../assets/svg/Panel_kolory.svg).

## Typografia i siatka

- Font: Segoe UI. Tytuł strony 28 pt, podtytuł 16 pt.
- Płótno 1920×1080.
- Nagłówek: pozycja 24/24, rozmiar 1110×114. Page navigator: 1170/24.
- Pierwszy rząd wizualizacji: Y = 156. Odstępy: 24 px.

## Zasady IBCS w raporcie

- Tytuły-wnioski z liczbą, np. „Połowa klientów kupuje tylko dodatki”.
- Podtytuły z jednostką i okresem, np. „Przyrost przychodu netto r/r, €, TOP 5 podkategorii, rok obrotowy 2007/2008”.
- Brak osi i siatki tam, gdzie są etykiety danych.
- PY częściowo schowany za AC (nakładane słupki).

## Lekcja: motyw v1 → v2

Pierwsza wersja motywu ustawiała style wszystkim wizualizacjom (`visualStyles: "*"`). W nowszej wersji Power BI przez to nie rysowała się nowa karta KPI. Wersja v2 zostawia tylko paletę, fonty i tło strony.
