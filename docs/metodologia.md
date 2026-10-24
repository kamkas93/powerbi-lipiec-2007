# Metodologia

Ten sam zestaw założeń jest w raporcie na ukrytej stronie **Nota metodologiczna** (przycisk „ⓘ Metodologia” w nagłówku).

## Źródło danych

- Baza SQL Server udostępniona w ramach kursu: przetłumaczona wersja przykładowej bazy Microsoft AdventureWorks. Tryb **Import**, więc dane są zapisane w pliku `.pbix`.
- Tabele: `FactInternetSales`, `DimKlient`, `DimGeografia`, `DimObszarSprzedazy`, `DimProdukt`, `DimPodkategoria`, `DimKategoria` + własna tabela dat `DimData`.
- Dane są przykładowe. Kwoty są pokazane w umownej walucie €.

## Ustalenia z eksploracji danych (data profiling)

| Ustalenie | Konsekwencja w analizie |
|---|---|
| `Wartość sprzedaży` to kwota **netto**, a `Podatek` to stałe **8%** w każdym kraju | Przychód = netto, podatek pominięty |
| `Ilość` zawsze = 1 | Zysk bez `SUMX` |
| **Brak numeru zamówienia** | Analiza koszyka na poziomie **klientów**, nie zamówień |
| Dane od VII 2005; rowery sprzedawane do **30.06.2008**; akcesoria i odzież od **01.07.2007** do 31.07.2008 | Okno analizy kończy się 30.06.2008 |
| Rowery turystyczne pojawiają się dopiero w VII 2007 (w roku poprzednim brak sprzedaży we wszystkich krajach) | Cały przyrost tej linii to nowa oferta |
| Lipiec 2008 niekompletny (brak rowerów) | Wyłączony z okna analizy |

## Okno analizy i rok obrotowy

- Analiza obejmuje trzy **lata obrotowe VII–VI**: 2005/2006, 2006/2007, 2007/2008. Filtr okna działa na wszystkich stronach.
- Dlaczego rok obrotowy: w latach kalendarzowych rok 2008 miał tylko 6 miesięcy i wyglądał na plateau. Rok obrotowy pokazuje rzeczywisty przebieg: spadek o ok. 19%, potem +186%. Wniosek potwierdza też porównanie tych samych miesięcy (I–VI) w latach kalendarzowych.

## Definicje

- **Przychód:** kwota netto w €.
- **Rowery** = kategoria „Rowery”. **Dodatki** = akcesoria i odzież (wszystko poza rowerami).
- **Segmenty klientów** (liczone w roku obrotowym 2007/2008, czyli w pierwszym roku, w którym były w sprzedaży dodatki):
  - *rower i dodatki*: klient kupił w tym roku rower i co najmniej jeden dodatek (`INTERSECT`),
  - *tylko dodatki*: kupił dodatki i nie kupił roweru (`EXCEPT`),
  - *tylko rower*: kupił rower bez dodatków (`EXCEPT`).
- **Wiek:** pełne lata na 30.06.2008 (koniec okna).
- **Geografia:** **obszar sprzedaży** przypisany do transakcji, nie miejsce zamieszkania klienta.

## Kontrola jakości

Testy spójności segmentów (2007/2008):

| Test | Wynik |
|---|---|
| tylko rower + rower i dodatki | 949 + 7 677 = **8 626** rowerzystów |
| tylko dodatki + rower i dodatki | 8 786 + 7 677 = **16 463** kupujących dodatki |
| suma trzech segmentów | 949 + 7 677 + 8 786 = **17 412** klientów |

Ranking źródeł wzrostu był sprawdzany zasadą „części sumują się do całości”. Dzięki temu wyszedł błąd: bez filtra roku na stronie trzy podkategorie dawały więcej niż cały przyrost firmy.

## Ograniczenia

- Bez numeru zamówienia nie da się powiedzieć, czy rower i dodatki były w **jednym** koszyku. Wiadomo tylko, że ten sam klient kupił je w tym samym roku obrotowym.
- Wskaźnik lift został odrzucony. Przy ok. 95% klientów kupujących dodatki punkt odniesienia jest zbyt wysoki (lift ≈ 0,94) i nie różnicuje grup.
- Dane są przykładowe (AdventureWorks), więc wnioski mają charakter ćwiczeniowy.
