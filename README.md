# ✈️ Flight Departures Scraper

Web scraper do pobierania danych o odlotach z wybranej strony internetowej, napisany w JavaScript z użyciem Puppeteer.

## 📌 Opis

Skrypt automatycznie otwiera stronę z odlotami, pobiera informacje o lotach (takie jak data, godzina, lotnisko, linia lotnicza i numer lotu), a następnie zapisuje je w formacie CSV.

## ⚙️ Technologie

- [Node.js](https://nodejs.org/)
- [Puppeteer](https://pptr.dev/)
- GitHub Actions (automatyzacja)

## 📦 Instalacja

1. Sklonuj repozytorium:

```bash
git clone https://github.com/grzegorz-nowacki/departures-scraper.git
cd departures-scraper
```

2. Zainstaluj zależności:

```bash
npm install
```

3. Uruchomienie:

```bash
node scraper.js
```

## 📦 Alternatywnie: Uruchom w GitHub Codespaces

Jeśli nie chcesz instalować niczego lokalnie, możesz uruchomić i edytować scraper bezpośrednio w przeglądarce dzięki GitHub Codespaces.

Kliknij przycisk "Code" w repozytorium, a następnie wybierz "Create codespace on main". Wymagane będzie zainstalowanie zależności zgodnie z instrukcją powyżej.

## 🔄 Automatyczne pobieranie danych

Repozytorium zawiera skonfigurowany GitHub Actions Workflow, który uruchamia scraper co godzinę, automatycznie zapisując najnowsze dane do pliku CSV.

### ✏️ Utrzymanie scraperów

Jeśli strona danego lotniska zmieni układ lub klasy CSS (np. nazwy klas HTML), scraper może przestać działać poprawnie.

W takim przypadku należy:

1. Zidentyfikować, które lotnisko przestało działać.
2. Otworzyć odpowiednią funkcję w kodzie scraper.js, np. `function scrapBZG()` dla lotniska Bydgoszcz.
3. Zaktualizować selektory (np. `querySelector`, `classList`, itp.), aby odpowiadały nowej strukturze strony.

To kluczowe dla dalszego poprawnego działania automatycznego scrapowania.