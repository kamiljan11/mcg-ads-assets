# RUNBOOK — mcg-ads-assets (repo z samymi assetami)

Hosting plikow reklamowych. Zero aplikacji, zero kodu, zero CI. Skrocona wersja runbooka.

## Podstawy
- Repo: github.com/kamiljan11/mcg-ads-assets — PUBLICZNE (celowo, sprawdzone `gh repo view`, 2026-10-05), domyslna galaz `main`
- Po co: Canva i narzedzia reklamowe Meta importuja grafike z bezposredniego URL; surowy plik z GitHuba jest stalym, darmowym linkiem
- Adres pliku: `https://raw.githubusercontent.com/kamiljan11/mcg-ads-assets/main/<plik>`
- Sekrety: brak w repo i brak sekretow Actions/CI (repo nie ma workflow). Konta reklamowe i Canva: poza repo. [DO UZUPELNIENIA przez Kamila: gdzie sa dane logowania do Canva i konta reklamowego — nie w repo.]

## Skad pochodza assety
- Zrodlowe, edytowalne kreacje: pliki `*_EDYTOWALNY.pptx` (warstwowe PowerPoint). Eksporty do reklam: pliki `.png` 1080x1350.
- Kampania "zostaw auto / leave your car" (Polish + EN): pierwsza wersja 2026-08-16, kolejne iteracje to mapa OpenStreetMap, korekta pinu lotniska i wersja angielska (patrz `CHANGELOG.md`).
- Trzy kreacje o przegladzie technicznym pojazdow (Skoðun): `MCG_skodun-3-kreacje_EDYTOWALNY.pptx` (3 slajdy), dodane 2026-09-03.
- Mapa w kreacjach: dane OpenStreetMap — w grafice jest atrybucja "map © OpenStreetMap contributors"; zostaw ja przy kazdej edycji (wymog licencji OSM).
- Zdjecie portretowe (`MCG_gosia_avatar.jpg`, 1200x1200): osoba pokazana w kreacjach; README repo deklaruje, ze opublikowano je za jej zgoda. [DO UZUPELNIENIA przez Kamila: gdzie jest przechowywany zapis zgody (poza repo) i czy obejmuje reklamy publiczne.]
- Autorstwo grafik/zrodlo layoutow: [DO UZUPELNIENIA przez Kamila: kto jest autorem layoutow i czy uzyto zewnetrznych fontow/zasobow z wlasna licencja].

## Licencja
Plik `LICENSE`: wszystkie prawa zastrzezone (Mountain All Service ehf. / Kamil Jan). Pliki sa publiczne tylko po to, by narzedzia mogly je pobrac przez URL — nie do ponownego uzycia.

## Jak uzywac
1. Wybierz plik `.png` (eksport) do reklamy albo `.pptx` do edycji.
2. Canva: "Import from URL" -> wklej adres z sekcji "Podstawy".
3. Nie zmieniaj nazw ani nie usuwaj plikow, ktore sa juz podlinkowane — projekty w Canva i reklamy przestana dzialac. Nowa wersja = nowy plik.

## Dodanie / edycja assetu
```bash
git switch -c assets/<opis>
# dodaj plik .pptx (zrodlo) i jego eksport .png 1080x1350
git add <pliki> && git commit -m "feat(assets): <opis>"
git push -u origin assets/<opis>
# PR do main i merge. Repo NIE ma ochrony galezi ani CI — nikt nie sprawdza zawartosci automatycznie.
```
Zanim cokolwiek trafi do tego PUBLICZNEGO repo: tylko materialy przeznaczone do publikacji jako reklama; zadnych danych klientow, dokumentow wewnetrznych, cennikow ani niezgodzonych portretow.

## Rollback
```bash
git revert <sha>   # cofa dodanie/zmiane pliku; link raw do starej wersji znika razem z nia
```
Gdy plik zostal wrzucony przez pomylke: usuniecie z `main` nie kasuje historii — plik zostaje osiagalny w starszych commitach. Potraktuj to jako opublikowany.

## Typowe awarie
| Objaw | Pierwszy krok |
|---|---|
| Canva nie importuje obrazka z URL | sprawdz adres w przegladarce (musi zwracac sam plik); zwroc uwage na wielkosc liter i nazwe galezi `main` |
| Reklama pokazuje stara grafike | mozliwe cache po stronie narzedzia (Canva/Meta); dodaj plik pod nowa nazwa zamiast nadpisywac |
| Linki przestaly dzialac po zmianie nazwy | przywroc stara nazwe (`git mv`) |
| Repo przestalo byc publiczne | raw URL zwraca 404 bez autoryzacji — przywroc widocznosc Public w ustawieniach repo (decyzja wlasciciela) |

## Porzadki
- Zdalna galaz `docs/pg-readme` to pozostalosc po zmergowanym PR #1 (README + licencja) — mozna usunac. [DO UZUPELNIENIA przez Kamila: potwierdz usuniecie.]
- Brak ochrony galezi `main` i brak workflow (inaczej niz w pozostalych repo MAS) — swiadoma decyzja? [DO UZUPELNIENIA przez Kamila]

## Kontakty
- Wlasciciel: Kamil Jan (MAS Group), konto GitHub `kamiljan11`; kontakt licencyjny wg pliku `LICENSE`.
