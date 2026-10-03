## 🧠 Zadanie 2 – Budowa prostego modelu uczenia maszynowego w Kedro + GitHub

### 🎯 Cel zadania

Nauczyć się tworzenia i uruchamiania prostego pipeline’u uczenia maszynowego w **Kedro**, wykorzystując dane z pliku `wasz-plik.csv` (Titanic lub inny dowolny data set), oraz udokumentować projekt w **repozytorium GitHub**.

---

### 🧱 Zakres pracy

W ramach zadania wykonaj:

1. Przygotowanie danych,
2. Stworzenie i trening modelu klasyfikacyjnego (np. przewidującego przeżycie pasażera),
3. Ocena jakości modelu,
4. Udokumentowanie wyników w GitHubie.

---

### 📍 Kroki do wykonania

#### 1️⃣ Utwórz projekt Kedro

1. Zainstaluj Kedro (Python 3.10+), np.:
   ```bash
   pip install kedro kedro-datasets scikit-learn pandas
   ```
2. Utwórz nowy projekt (albo rozbuduj projekt z Zadania 1):
   ```bash
   kedro new --name pum_zajecia2_[twojenazwisko]
   ```
3. W `README.md` projektu wpisz opis, np.: „Model predykcji przeżycia pasażerów Titanic”.

---

#### 2️⃣ Załaduj dane

1. Dodaj do projektu plik `<wasz-plik>.csv` (dostępny w materiałach lub z repozytorium Kaggle), np.:
   ```
   data/01_raw/train.csv
   ```
2. Zarejestruj dataset w `conf/base/catalog.yml`.
3. Sprawdź dane (notebook / `kedro ipython` / prosty node) — m.in. liczbę rekordów, kolumny i typy danych.

---

#### 3️⃣ Przygotuj dane do modelowania

Zaimplementuj node (lub node’y) preprocessingu w pipeline Kedro, który:

* usuwa kolumny nieistotne, np. `Name`, `Ticket`, `Cabin`,
* uzupełnia brakujące wartości w `Age` (np. medianą),
* zamienia zmienne tekstowe (`Sex`, `Embarked`) na numeryczne (np. one-hot / ordinal encoding).

Zapisz wynik jako dataset pośredni w katalogu (np. `data/03_primary/` lub `data/05_model_input/`).

💡 **Podpowiedź:** trzymaj parametry (lista kolumn do usunięcia, strategia imputacji) w `conf/base/parameters.yml`.

---

#### 4️⃣ Zbuduj model w pipeline Kedro

1. Dodaj node treningu modelu:

   * Target: `Survived`
   * Typ problemu: **Classification**
   * Algorytm: np. **Logistic Regression** lub **Random Forest** (`scikit-learn`)

2. Dodaj node ewaluacji i policz metryki:

   * Accuracy
   * Precision / Recall
   * Confusion matrix

3. Zapisz artefakty (model, metryki, macierz pomyłek) przez Data Catalog, np. do `data/06_models/` i `data/08_reporting/`.
4. Uruchom pipeline:
   ```bash
   kedro run
   ```

---

#### 5️⃣ Zaimplementuj kod w node’ach Kedro

W `src/.../pipelines/` (np. `nodes.py` + `pipeline.py`) zaimplementuj logikę odpowiadającą poniższemu szkieletowi:

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score

# Wczytanie danych
!!! miejsce na Twój kod !!!

# Przygotowanie danych
!!! miejsce na Twój kod !!!

# Podział na zbiory
!!! miejsce na Twój kod !!!

# Trening modelu
!!! miejsce na Twój kod !!!

# Ewaluacja
!!! miejsce na Twój kod !!!
```

Pipeline powinien dać się uruchomić komendą `kedro run` (bez ręcznego kopiowania kodu poza projekt).

---

#### 6️⃣ Udokumentuj projekt w GitHub

1. Utwórz repozytorium:

   ```
   PUM_Zajęcia2_[TwojeNazwisko]
   ```

2. Dodaj do niego:

   * plik `README.md` z opisem projektu,
   * plik `model_summary.md` z wynikami (accuracy, confusion matrix itp.),
   * kod pipeline’u Kedro (`src/`, `conf/`),
   * zrzuty ekranu / artefakty (np. `kedro-viz`, struktura pipeline’ów, wykresy metryk),
   * opcjonalnie: wyeksportowany model lub raporty z `data/08_reporting/`.

3. Przykładowa struktura repozytorium:

   ```
   conf/
     base/
       catalog.yml
       parameters.yml
   data/
     01_raw/
       train.csv
     08_reporting/
       model_metrics.png
   src/
     .../pipelines/
       data_science/
         nodes.py
         pipeline.py
   README.md
   model_summary.md
   ```

---

#### 7️⃣ Prześlij do oceny

Wyślij **link do swojego repozytorium GitHub** prowadzącemu.
Nie wysyłaj plików przez e-mail.

---

### 🧾 Kryteria oceny (propozycja)

| Kryterium                                         | Punkty     |
| ------------------------------------------------- | ---------- |
| Poprawne przygotowanie danych                     | 2          |
| Utworzenie i trenowanie modelu                    | 3          |
| Ocena wyników i wnioski                           | 2          |
| Implementacja pipeline’u Kedro (node’y + `kedro run`) | 2      |
| Dokumentacja i repozytorium GitHub                | 1          |
| **Łącznie**                                       | **10 pkt** |
