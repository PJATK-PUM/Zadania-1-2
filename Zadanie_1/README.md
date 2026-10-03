## 🧩 Zadanie 1 – Eksploracja danych w Kedro + GitHub

### 🎯 Cel zadania

Nauczyć się pracy w projekcie **Kedro** oraz podstaw wykorzystania **GitHuba** do dokumentowania i udostępniania wyników analizy danych poprzez:

* załadowanie i wstępne poznanie zbioru danych,
* wykonanie podstawowej analizy i wizualizacji,
* sformułowanie prostych wniosków,
* publikację wyników i kodu (np. plików CSV, raportów, zrzutów ekranu) w repozytorium GitHub.

---

### 🧱 Kroki do wykonania

#### 1️⃣ Utwórz nowy projekt Kedro

1. Zainstaluj Kedro (Python 3.10+), np.:
   ```bash
   pip install kedro kedro-datasets
   ```
2. Utwórz projekt:
   ```bash
   kedro new --name pum_zajecia1_[twojenazwisko]
   ```
3. Wejdź do katalogu projektu i zainstaluj zależności środowiska zgodnie z wygenerowanym `requirements.txt` / `pyproject.toml`.
4. W `README.md` projektu wpisz krótki opis, np. „Eksploracja danych Titanic”.

---

#### 2️⃣ Załaduj dane do projektu

1. Pobierz dataset: **Titanic.csv**
   (np. z [Kaggle: Titanic Dataset](https://www.kaggle.com/c/titanic/data)).
2. Umieść plik w katalogu danych surowych, np.:
   ```
   data/01_raw/Titanic.csv
   ```
3. Zarejestruj dataset w Data Catalog (`conf/base/catalog.yml`), np. jako `titanic_raw`.
4. Sprawdź dane (notebook Kedro, `kedro ipython` albo prosty node/pipeline), m.in.:

   * ile jest rekordów,
   * jakie są kolumny i ich typy (tekstowe, liczbowe, logiczne),
   * czy występują wartości brakujące.

---

#### 3️⃣ Zbadaj dane

Wykonaj podstawowe wizualizacje (pandas + matplotlib/seaborn/plotly), np. w `notebooks/` albo w osobnym node’ie EDA:

* histogram wieku pasażerów,
* odsetek osób, które przeżyły (kolumna *Survived*),
* rozkład płci (*Sex*),
* zależność wieku od przeżycia (wykres rozrzutu lub boxplot).

💡 **Podpowiedź:** wynikowe wykresy zapisz do `data/08_reporting/` (lub `screenshots/`) i dołącz je do repozytorium.

---

#### 4️⃣ Zapisz swoje obserwacje

Odpowiedz na poniższe pytania (możesz zapisać odpowiedzi jako plik `raport.md` lub `raport.txt`):

* Ile rekordów i kolumn zawiera zbiór?
* Jakie trzy zmienne (Twoim zdaniem) najbardziej wpływają na przeżycie?
* Jakie wartości brakujące występują w danych?
* Jakie dwie obserwacje są dla Ciebie najciekawsze?

---

#### 5️⃣ Przygotuj repozytorium GitHub

1. Utwórz **nowe prywatne repozytorium** na GitHubie w organizacji **PJATK-PUM** o nazwie:

   ```
   PUM_Zajęcia1_[TwojeNazwisko]
   ```

2. W repozytorium umieść:

   * plik `README.md` z krótkim opisem projektu (cel, dane, wnioski),
   * plik `raport.md` lub `raport.txt` z odpowiedziami na pytania z kroku 4,
   * zrzuty ekranu / artefakty z Kedro (np. struktura projektu, `kedro-viz`, przykładowe wykresy),
   * opcjonalnie: eksport danych lub wizualizacji (np. `.csv`, `.png`, `.pdf`).

3. Uporządkuj repozytorium, np. w strukturze Kedro:

   ```
   conf/
     base/
       catalog.yml
   data/
     01_raw/
       Titanic.csv
     08_reporting/
       chart_age.png
   notebooks/
     eda.ipynb
   src/
   raport.md
   README.md
   ```

4. Dodaj / uzupełnij plik `.gitignore` (Kedro generuje domyślny — upewnij się, że nie wrzucasz plików tymczasowych ani zbędnie dużych danych).

---

#### 6️⃣ Prześlij do oceny

1. Upewnij się, że wszystkie pliki są **zatwierdzone i wypchnięte (push)** na GitHub.
2. Wyślij prowadzącemu **link do repozytorium GitHub**, zamiast przesyłać pliki e-mailem.

💡 **Dodatkowo:** możesz dodać do README krótkie refleksje z pracy z Kedro (np. co było najtrudniejsze w katalogu danych / strukturze projektu).

---

### 📦 Efekt końcowy

Po ukończeniu zadania powinieneś mieć:

* lokalny projekt Kedro z przeprowadzoną analizą eksploracyjną,
* repozytorium GitHub z dokumentacją i wynikami,
* podstawową znajomość pracy z Git i GitHub w kontekście analizy danych.
