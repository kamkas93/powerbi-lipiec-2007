# Materiały do dostarczenia przez autora

Ta checklista zbiera wszystko, czego brakuje w repozytorium i na stronie portfolio. ☑ = dostarczone i wstawione, ☐ = otwarte.

**Stan:** zrzuty 01–09, 11 i 12 dostarczone (zmniejszone do szer. 1920 px, paleta 256 kolorów). Otwarte: `10_topn_3_vs_10` (opcjonalny) i GIF-y.

**Jak dodać obrazek:**
1. Zapisz plik w `img/` pod podaną nazwą.
2. W README / docs usuń komentarz HTML wokół linku do obrazka (`<!-- ... -->`).
3. Na stronie portfolio: skopiuj ten sam plik do `kamil-kasinski/img/lipiec-2007/` i odkryj sekcję galerii w `projekt-lipiec-2007.html` (usuń atrybut `hidden`).

Format: PNG, płótno 1920×1080 (eksport strony albo zrzut okna w trybie czytania). GIF: maks. ok. 10 MB, 10–15 fps.

## 1. Zrzuty ekranu

| ☐ | Plik | Co ma pokazywać | Gdzie użyty |
|---|---|---|---|
| ☑ | `img/01_start.png` | Strona Start: tytuł, panele „Jak czytać kolory” i „Co możesz zrobić”, duży rower | README (baner), strony-raportu, strona www |
| ☑ | `img/02_przelom.png` | Strona 1. Przełom, rok 2007/2008 wybrany w slicerze; widoczny trend z wyróżnionym VII 2007 | README, strony-raportu, strona www |
| ☑ | `img/03_zrodla_wzrostu.png` | Strona 2. Źródła wzrostu, ranking ustawiony na TOP 5 | strony-raportu, strona www |
| ☑ | `img/04_koszyk_liczby.png` | Strona 3. Koszyk, bookmark **Liczby** | strony-raportu, strona www |
| ☑ | `img/05_koszyk_procenty.png` | Strona 3. Koszyk, bookmark **Procenty** | strony-raportu |
| ☑ | `img/06_klienci.png` | Strona 4. Klienci: słupki 100%, piktogram płci, persona | strony-raportu, strona www |
| ☑ | `img/07_szczegoly_kraju.png` | Szczegóły kraju (drill-through), np. Kanada z rowerem SVG 63% | strony-raportu, strona www |
| ☑ | `img/08_metodologia.png` | Nota metodologiczna | strony-raportu |
| ☑ | `img/09_tooltip.png` | Przykład dopracowanego tooltipa (dowolna wizualizacja) | strony-raportu |
| ☐ | `img/10_topn_3_vs_10.png` | Ranking TOP 3 i TOP 10 obok siebie (dynamiczny tytuł i podtytuł) | opcjonalnie |
| ☑ | `img/11_model.png` | Widok modelu (Model view): płatek śniegu, relacje | model-danych |
| ☑ | `img/12_miary.png` | Panel danych z tabelą `_Miary` i 7 folderami | opcjonalnie, dax/README |

## 2. GIF-y

| ☐ | Plik | Scenariusz |
|---|---|---|
| ☐ | `img/g1_drilldown.gif` | Strona 2: drill-down Kategoria → Podkategoria → Produkt i powrót w górę |
| ☐ | `img/g2_liczby_procenty.gif` | Strona 3: przełączenie Liczby → Procenty → Liczby |
| ☐ | `img/g3_drillthrough.gif` | Strona 2 lub 3: PPM na kraju → Drill through → Szczegóły kraju → przycisk powrotu |
| ☐ | `img/g4_przeglad.gif` | Opcjonalnie: szybki przegląd Start → 1 → 2 → 3 → 4 przez Page navigator (do README) |

## 3. Opcjonalne wideo (ok. 2 min)

Plik: `img/wideo_lipiec_2007.mp4` albo link do YouTube / LinkedIn.

| # | Czas | Ekran | Tekst lektora |
|---|---|---|---|
| 1 | 0:00–0:15 | Start | „To raport o sprzedaży internetowej sklepu rowerowego w latach obrotowych od 2005/2006 do 2007/2008. Pytanie: co odwróciło spadek sprzedaży?” |
| 2 | 0:15–0:35 | 1. Przełom, slicer 2006/2007 → 2007/2008 | „W roku 2006/2007 przychód spadł o około 19%, z 7,1 do 5,8 mln euro. Od lipca 2007 firma wprowadziła nową ofertę i w kolejnym roku przychód wzrósł do 16,5 mln, czyli o 186%.” |
| 3 | 0:35–0:50 | 1. Przełom, wykres klienci vs przychód na klienta | „Rok do roku klientów przybyło około 5,4 razy, z 3 222 do 17 412, a przychód na klienta spadł około 1,9 raza, z 1 788 do 946 euro. Nowi klienci przyszli po tańsze dodatki.” |
| 4 | 0:50–1:10 | 2. Źródła wzrostu, TOP 3 → TOP 10, drill-down | „Mimo to rowery dały około 91% przyrostu. Najwięcej rowery górskie, potem nowa linia turystyczna i szosowe. USA wyprzedziło Australię.” |
| 5 | 1:10–1:30 | 3. Koszyk, Liczby → Procenty | „W danych nie ma numeru zamówienia, więc koszyk liczę na zbiorach klientów. 89% rowerzystów dokupuje dodatki, ale połowa klientów, 8 786 osób, kupuje tylko dodatki.” |
| 6 | 1:30–1:45 | 4. Klienci | „Bez roweru zostają najmłodsi, 28–34 lata, najstarsi, 55+, i duże rodziny. Płeć nie różnicuje.” |
| 7 | 1:45–2:00 | Drill-through USA → rekomendacja | „Rekomendacja: kampania rowerowa do klientów, którzy kupują tylko dodatki. Najpierw w USA, gdzie to prawie 4 tysiące osób.” |

## 4. Pliki do wrzucenia do repo

| ☐ | Plik | Uwagi |
|---|---|---|
| ☐ | `report/*.pbix` | `*.pbix` jest w `.gitignore`. Jeśli chcesz udostępnić plik, usuń ten wpis albo dodaj plik do GitHub Releases. |

## 5. Placeholdery `[DO UZUPEŁNIENIA]`

Wszystkie miejsca w repo, w których brakuje faktu:

| Plik | Czego brakuje |
|---|---|
| `dax/06_grafika_svg.dax` | pełny kod miary `A RowerWypelnienie` |
| `dax/06_grafika_svg.dax` | pełny kod miary `A IkonyPlec` |
| `dax/07_formatowanie.dax` | nazwy i kod trzech miar koloru analogicznych do `C KolorZmianaPrzychodRR` (zysk, klienci, marża) |
| `dax/README.md` | dokładne nazwy tych trzech miar `C` |
| `dax/README.md` | nazwa, folder i opis 39. miary (katalog opisuje 38) |
| `README.md` | `[LINK DO RAPORTU — opcjonalnie]`: link „Publish to web”, jeśli chcesz go podać (może wygasnąć) |
