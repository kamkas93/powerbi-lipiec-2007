# Log decyzji (ADR-lite)

Każdy wpis: **kontekst → decyzja → alternatywy → konsekwencje**.

---

## D1. Rok obrotowy zamiast kalendarzowego

- **Kontekst:** w latach kalendarzowych rok 2008 miał tylko 6 miesięcy danych w oknie analizy i na wykresie wyglądał jak plateau.
- **Decyzja:** oś analizy to rok obrotowy VII–VI (2005/2006, 2006/2007, 2007/2008), kolumna `DimData[RokObrotowy]`.
- **Alternatywy:** lata kalendarzowe; porównanie samych miesięcy I–VI.
- **Konsekwencje:** widać prawdziwą historię: spadek o ok. 19%, potem +186%. Porównanie miesięcy I–VI w latach kalendarzowych potwierdza ten sam wniosek.

## D2. Hipoteza „wzrost dały dodatki” sprawdzona na danych

- **Kontekst:** od lipca 2007 w sprzedaży są akcesoria i odzież. Pierwsza intuicja: to one dały wzrost.
- **Decyzja:** zbudować ranking przyrostu r/r wg podkategorii (TOP N) i dopiero na tej podstawie pisać wnioski.
- **Alternatywy:** oprzeć się na intuicji albo na udziałach w przychodzie.
- **Konsekwencje:** ok. 91% przyrostu dały rowery (ok. 9,7 z 10,7 mln €). Ranking pokazał też, że do oferty weszła **nowa linia rowerów turystycznych**.

## D3. Kontrola „części sumują się do całości”

- **Kontekst:** w rankingu trzy podkategorie dawały więcej niż cały przyrost firmy.
- **Decyzja:** porównywać wyniki z liczbami kontrolnymi. Przyczyna: brak filtra roku na stronie. Filtr dodany.
- **Konsekwencje:** ranking jest spójny z całością. Testy spójności segmentów klientów: patrz [metodologia.md](metodologia.md).

## D4. Cross-selling bez numeru zamówienia

- **Kontekst:** w danych nie ma numeru zamówienia, więc nie da się zbudować koszyków.
- **Decyzja:** analiza na zbiorach klientów: `INTERSECT` (rower i dodatki), `EXCEPT` (tylko dodatki, tylko rower) w roku 2007/2008.
- **Alternatywy:** przybliżanie zamówienia przez klienta + datę.
- **Konsekwencje:** definicja i ograniczenie są opisane w nocie metodologicznej.

## D5. Piktogram zamiast sylwetki wypełnianej po wysokości

- **Kontekst:** pierwsza wersja `A IkonyPlec` wypełniała jedną sylwetkę po wysokości. Wypełnienie do połowy wysokości zakrywało ok. 75–80% powierzchni, więc obraz przekłamywał proporcje.
- **Decyzja:** piktogram (unit chart) z 10 sylwetek, 1 sylwetka = 10%.
- **Konsekwencje:** powierzchnia odpowiada wartości.

## D6. Motyw JSON v2 bez `visualStyles: "*"`

- **Kontekst:** motyw v1 ustawiał style wszystkim wizualizacjom. W nowszej wersji Power BI przez to nie rysowała się nowa karta KPI.
- **Decyzja:** v2 zostawia tylko paletę, fonty i tło strony.
- **Konsekwencje:** wszystkie wizualizacje działają, formatowanie jest ustawiane na poziomie wizualizacji.

## D7. Świadomie odrzucone

| Pomysł | Dlaczego nie |
|---|---|
| Panel filtrów jako bookmark | Kłóciłby się ze statycznymi tytułami-wnioskami. |
| Wskaźnik lift | Przy ok. 95% klientów kupujących dodatki punkt odniesienia jest zbyt wysoki. Lift ≈ 0,94 nie różnicuje grup. |
| `CROSSFILTER` | Zbędny. Klientów liczę w tabeli, do której filtr dociera (fakt). |
| `SUMX` dla zysku | Ilość zawsze = 1, więc iteracja nic nie wnosi. |
