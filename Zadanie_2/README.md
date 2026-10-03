## 🧠 Zadanie 2 – Budowa prostego modelu uczenia maszynowego w Dataiku DSS + GitHub

### 🎯 Cel zadania

Nauczyć się tworzenia i wdrażania prostego modelu uczenia maszynowego w **Dataiku DSS**, wykorzystując dane z pliku `wasz-plik.csv` (Titanic lub inny dowolny data set), oraz udokumentować projekt w **repozytorium GitHub**.

---

### 🧱 Zakres pracy

W ramach zadania wykonaj:

1. Przygotowanie danych,
2. Stworzenie i trening modelu klasyfikacyjnego (np. przewidującego przeżycie pasażera),
3. Ocena jakości modelu,
4. Udokumentowanie wyników w GitHubie.

---

### 📍 Kroki do wykonania

#### 1️⃣ Utwórz projekt w Dataiku DSS

1. Zaloguj się do [http://dataiku.pjwstk.edu.pl:11000/](http://dataiku.pjwstk.edu.pl:11000/).
2. Utwórz nowy projekt w folderze:
   ```
   Piotr Kojalowicz/PUM2025/<numer-grupy>c/Zajęcia_2/
   ```

   ```
   [TwojeNazwisko]
   ```
3. W opisie wpisz: „Model predykcji przeżycia pasażerów Titanic”.

---

#### 2️⃣ Zaimportuj dane

1. Dodaj do projektu plik `<wasz-plik>.csv` (dostępny w materiałach lub z repozytorium Kaggle).
2. Obejrzyj dane w zakładce **Explore** – sprawdź m.in. liczbę rekordów, kolumny i typy danych.

---

#### 3️⃣ Przygotuj dane do modelowania

Wykonaj proste czyszczenie i przygotowanie danych:

* usuń kolumny nieistotne, np. `Name`, `Ticket`, `Cabin`,
* uzupełnij brakujące wartości w `Age` (np. medianą),
* zamień zmienne tekstowe (`Sex`, `Embarked`) na numeryczne, np. za pomocą **Prepare recipe** lub **Python recipe**.

💡 **Podpowiedź:** możesz też użyć wbudowanej funkcji **AutoML Prepare** w Dataiku.

---

#### 4️⃣ Zbuduj model

1. Utwórz **nowy model predykcyjny**:

   * Target: `Survived`
   * Typ problemu: **Classification**
   * Algorytm: np. **Logistic Regression** lub **Random Forest**

2. Przeprowadź trening modelu i sprawdź metryki:

   * Accuracy
   * Precision / Recall
   * Confusion matrix

3. Zapisz najlepszy model i nazwij go np.:

   ```
   Titanic_Model_[TwojeNazwisko]
   ```

---

#### 5️⃣ (Opcjonalnie) – Stwórz własny kod w Python Recipe

Dodaj **Python recipe**, który:

* wczytuje dane `train.csv`,
* przygotowuje je do modelowania,
* trenuje model np. przy użyciu `scikit-learn`:

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

4. Wyświetl wynik w logu recipe lub zapisz do nowego datasetu.

---

#### 6️⃣ Udokumentuj projekt w GitHub

1. Utwórz repozytorium:

   ```
   PUM_Zajęcia2_[TwojeNazwisko]
   ```

2. Dodaj do niego:

   * plik `README.md` z opisem projektu,
   * plik `model_summary.md` z wynikami (accuracy, confusion matrix itp.),
   * kod z recipe (np. `model.py`),
   * zrzuty ekranu z Dataiku (model flow, wykresy, wyniki),
   * opcjonalnie: eksport modelu lub datasetu.

3. Przykładowa struktura repozytorium:

   ```
   /data
     train.csv
   /code
     model.py
   /screenshots
     model_metrics.png
     data_flow.png
   README.md
   model_summary.md
   ```

---

#### 7️⃣ Prześlij do oceny

Wyślij **link do swojego repozytorium GitHub** prowadzącemu.
Nie wysyłaj plików przez e-mail.

---

### 🧾 Kryteria oceny (propozycja)

| Kryterium                                    | Punkty     |
| -------------------------------------------- | ---------- |
| Poprawne przygotowanie danych                | 2          |
| Utworzenie i trenowanie modelu               | 3          |
| Ocena wyników i wnioski                      | 2          |
| Implementacja kodu w Dataiku (Python recipe) | 2          |
| Dokumentacja i repozytorium GitHub           | 1          |
| **Łącznie**                                  | **10 pkt** |
