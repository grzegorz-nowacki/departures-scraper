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
```

2. Zainstaluj zależności:

```bash
cd departures-scraper/scraper
npm install
```

3. Uruchomienie:

```bash
node scraper.js
```

## 📦 Alternatywnie: Uruchom w GitHub Codespaces

Jeśli nie chcesz instalować niczego lokalnie, możesz uruchomić i edytować scraper bezpośrednio w przeglądarce dzięki GitHub Codespaces.

1. Kliknij przycisk "Code" w repozytorium, a następnie wybierz "Create codespace on main". 

2. Znajdź pole Terminal na dole okna i tam zainstaluj zależności:

```bash
cd scraper
npm install
sudo rm -f /etc/apt/sources.list.d/yarn.list && \
sudo apt-get update && \
sudo apt-get install -y \
  libatk1.0-0t64 \
  libatk-bridge2.0-0t64 \
  libcups2t64 \
  libxkbcommon0 \
  libxcomposite1 \
  libxdamage1 \
  libxfixes3 \
  libxrandr2 \
  libgbm1 \
  libasound2t64 \
  && sudo ldconfig
```

3. Uruchomienie:

```bash
node scraper.js
```

## 🔄 Automatyczne pobieranie danych

Repozytorium zawiera skonfigurowany GitHub Actions Workflow, który uruchamia scraper co godzinę, automatycznie zapisując najnowsze dane do pliku CSV.

⚠️ Uwaga o kosztach: GitHub Actions działa w modelu limitów i rozliczeń (dla kont prywatnych obowiązują opłaty po przekroczeniu darmowego limitu). W aktualnej konfiguracji uruchomienie raz na godzinę mieści się w darmowym zakresie użycia, jeśli w przyszłości model rozliczeń się zmieni i limit się zmniejszy, właściciel konta otrzyma wiadomość mailową dotyczącą zbliżania się do końca darmowego limitu.

### ✏️ Utrzymanie scraperów

Jeśli strona danego lotniska zmieni układ lub klasy CSS (np. nazwy klas HTML), scraper może przestać działać poprawnie.

W takim przypadku należy:

1. Zidentyfikować, które lotnisko przestało działać.
2. Otworzyć odpowiednią funkcję w kodzie scraper.js, np. `function scrapBZG()` dla lotniska Bydgoszcz.
3. Zaktualizować selektory (np. `querySelector`, `classList`, itp.), aby odpowiadały nowej strukturze strony.

To kluczowe dla dalszego poprawnego działania automatycznego scrapowania.