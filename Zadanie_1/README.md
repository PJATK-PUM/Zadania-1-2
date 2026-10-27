## 🧩 Zadanie 1 – Eksploracja danych w Kedro + GitHub

### 🎯 Cel zadania

Nauczyć się pracy w projekcie **Kedro** oraz podstaw **GitHuba** poprzez:

* utworzenie **jednego** projektu Kedro (tego samego, który rozwiniesz w Zadaniu 2),
* załadowanie **kilku datasetów** do Data Catalog,
* wykonanie podstawowej analizy i wizualizacji,
* sformułowanie wniosków i publikację wyników w repozytorium GitHub.

> **Ważne:** Zadanie 1 i Zadanie 2 to **jeden projekt Kedro** — różne datasety i etapy, później połączone w wspólny pipeline.

---

### 🧱 Kroki do wykonania

#### 1️⃣ Utwórz jeden projekt Kedro (na oba zadania)

1. Zainstaluj Kedro (Python 3.10+), np.:
   ```bash
   pip install kedro kedro-datasets
   ```
2. Utwórz projekt (nazwa na cały kurs zadań 1–2; **numer indeksu w nazwie**):
   ```bash
   kedro new --name pum_zadania_s[nr_indeksu]
   ```
   Przykład: `pum_zadania_s12345` (praca indywidualna — jeden numer indeksu).
3. Wejdź do katalogu projektu i doinstaluj zależności.
4. W `README.md` opisz, że to wspólny projekt na Zadanie 1 i 2 (EDA → modelowanie).

---

#### 2️⃣ Załaduj datasety (więcej niż jeden)

1. Przygotuj **co najmniej 2 datasety** (np. Titanic + drugi zestaw CSV z materiałów: Kaggle / inna tabela).
   Przykład pierwszego: [Titanic Dataset](https://www.kaggle.com/c/titanic/data).
2. Umieść je w danych surowych, np.:
   ```
   data/01_raw/dataset_a.csv
   data/01_raw/dataset_b.csv
   ```
3. Zarejestruj **oba** w `conf/base/catalog.yml` (osobne wpisy, np. `dataset_a_raw`, `dataset_b_raw`).
4. Dla każdego zbioru sprawdź:

   * liczbę rekordów,
   * kolumny i typy,
   * braki danych.

💡 Na tym etapie datasety mogą być jeszcze niezależne — połączenie w jeden przepływ zrobisz w Zadaniu 2.

---

#### 3️⃣ Zbadaj dane (EDA per dataset)

Dla **każdego** datasetu wykonaj podstawowe wizualizacje (notebook w `notebooks/` albo node EDA):

* rozkłady kluczowych zmiennych numerycznych,
* rozkład zmiennej celu (jeśli jest) lub najważniejszej kategorii,
* zależność 1–2 cech względem celu / siebie nawzajem,
* krótkie porównanie: czym datasety się różnią (rozmiar, typy, braki).

Zapisz wykresy np. do `data/08_reporting/`.

---

#### 4️⃣ Zapisz obserwacje

W pliku `raport.md` (lub `raport.txt`) odpowiedz:

* Ile rekordów i kolumn ma **każdy** zbiór?
* Jakie 2–3 zmienne wydają się najważniejsze w każdym zbiorze?
* Jakie braki / problemy jakości danych zauważasz?
* Jak (na razie koncepcyjnie) można by później **połączyć** te datasety w jednym pipeline Kedro (wspólny klucz? osobne gałęzie? ten sam schemat preprocessingu)?

---

#### 5️⃣ Repo GitHub (jedno na Z1+Z2) + branch zadania

1. Utwórz **jedno prywatne** repo w organizacji **PJATK-PUM**. Praca **indywidualna** — nazwa **musi zawierać Twój numer indeksu**:

   ```
   PUM_Zadania_s[nr_indeksu]
   ```

   Przykład: `PUM_Zadania_s12345`.

2. Rozwiązanie Zadania 1 umieść na **dedykowanym branchu**, np.:

   ```bash
   git checkout -b zadanie-1
   ```

3. Wrzuć projekt Kedro z:

   * `README.md` (cel, datasety, wnioski z EDA),
   * `raport.md` / `raport.txt`,
   * artefaktami EDA (wykresy, ewentualnie `kedro-viz`),
   * `conf/base/catalog.yml` z wpisami dla wszystkich datasetów.

4. Przykładowa struktura:

   ```
   conf/base/catalog.yml
   data/01_raw/
     dataset_a.csv
     dataset_b.csv
   data/08_reporting/
   notebooks/eda.ipynb
   src/
   raport.md
   README.md
   ```

5. Uzupełnij `.gitignore` (nie commituj zbędnie dużych plików).

---

#### 6️⃣ Oddanie

1. `push` brancha `zadanie-1` na GitHub.
2. Przez **Teams** wyślij prowadzącemu **link do brancha** z rozwiązaniem (np. `…/tree/zadanie-1`) — **jako link**, nie jako plik tekstowy.
3. Każda **poprawka** wymaga przesłania **nowego linka** (do zaktualizowanego brancha / commitów z poprawką).
4. **Commity przesłane po ostatecznym terminie** będą traktowane jako **oszustwo**.

---

### 📦 Efekt końcowy

* jeden projekt Kedro z **kilkoma datasetami** w katalogu,
* EDA i raport,
* repo (z numerem indeksu w nazwie) i branch `zadanie-1` gotowe do rozbudowy w Zadaniu 2 (pipeline łączący datasety).
