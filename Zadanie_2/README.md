## 🧠 Zadanie 2 – Model ML i połączenie datasetów w tym samym projekcie Kedro

### 🎯 Cel zadania

W **tym samym projekcie Kedro co Zadanie 1** dodać pipeline uczenia maszynowego, przeprocesować datasety i **połączyć je w jeden spójny przepływ** (`kedro run`), a wyniki opisać na GitHubie.

> Nie twórz nowego projektu Kedro ani nowego repo — kontynuujesz `pum_zadania_[nazwisko]` / `PUM_Zadania_[Nazwisko]`.

---

### 🧱 Zakres pracy

1. Preprocessing datasetów z Zadania 1,
2. Trening modelu klasyfikacyjnego (lub osobnych modeli per gałąź, potem wspólne raportowanie),
3. Ocena jakości,
4. **Połączenie** etapów EDA → prepare → train → evaluate w jednym pipeline Kedro,
5. Aktualizacja dokumentacji w tym samym repo GitHub.

---

### 📍 Kroki do wykonania

#### 1️⃣ Otwórz istniejący projekt z Zadania 1

1. Upewnij się, że masz zależności:
   ```bash
   pip install kedro kedro-datasets scikit-learn pandas
   ```
2. Datasety z Z1 nadal są w `data/01_raw/` i w `catalog.yml`.
3. Zaktualizuj `README.md`: dopisz sekcję o modelowaniu i połączeniu pipeline’ów.

---

#### 2️⃣ Ustal, jak łączysz datasety

Wybierz i opisz w `model_summary.md` jedną z strategii (albo własną, uzasadnioną):

* **Osobne gałęzie, wspólny pipeline** — każdy dataset ma własny prepare/train, a pipeline składa je w jeden graf (`kedro run` odpala wszystko).
* **Wspólny schemat** — te same kroki preprocessingu parametryzowane per dataset (`parameters.yml`).
* **Połączenie tabel** — jeśli jest sensowny klucz / wspólna domena, zrób join / concat w node’ie i trenuj na zbiorze połączonym.

Nie musisz sztucznie sklejać niepasujących tabel — ważne, żeby w Kedro był **jeden projekt i jeden (lub wyraźnie złożony) pipeline**, a nie osobne luźne skrypty.

---

#### 3️⃣ Preprocessing (node’y Kedro)

Dla datasetów używanych do modelu:

* usuń nieistotne kolumny,
* uzupełnij braki (np. mediana dla numerycznych),
* zakoduj zmienne kategoryczne,
* zapisz wyniki do warstw katalogu (np. `03_primary` / `05_model_input`),
* parametry trzymaj w `conf/base/parameters.yml`.

Przykład (Titanic-like): drop `Name`/`Ticket`/`Cabin`, imputacja `Age`, encoding `Sex`/`Embarked`, target `Survived`.

---

#### 4️⃣ Trening i ewaluacja

1. Node treningu: klasyfikacja (np. Logistic Regression lub Random Forest).
2. Node ewaluacji: Accuracy, Precision/Recall, confusion matrix.
3. Artefakty w catalogu: model (`data/06_models/`), raporty (`data/08_reporting/`).
4. Uruchom całość:
   ```bash
   kedro run
   ```

Pipeline powinien obejmować **więcej niż jeden dataset** albo wyraźnie łączyć etapy z Z1 (np. tagi/pipeline’y `eda` + `data_science` rejestrowane w jednym projekcie).

---

#### 5️⃣ Kod w node’ach (szkielet)

W `src/.../pipelines/` zaimplementuj logikę w stylu:

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score

# Wczytanie danych (z catalog / argumentów node'a)
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

Całość ma działać przez `kedro run`, nie jako osobny skrypt obok projektu.

---

#### 6️⃣ Dokumentacja w tym samym repo

Repo nadal:

```
PUM_Zadania_[TwojeNazwisko]
```

Dodaj / zaktualizuj:

* `README.md` — jak datasety są połączone w pipeline,
* `model_summary.md` — metryki, confusion matrix, krótki wniosek,
* kod `src/` + `conf/`,
* artefakty (`kedro-viz`, wykresy metryk, schemat pipeline’u).

Przykładowa struktura po Z2:

```
conf/base/
  catalog.yml
  parameters.yml
data/
  01_raw/
    dataset_a.csv
    dataset_b.csv
  05_model_input/
  06_models/
  08_reporting/
src/.../pipelines/
  eda/
  data_science/
    nodes.py
    pipeline.py
README.md
raport.md          # z Zadania 1
model_summary.md   # z Zadania 2
```

---

#### 7️⃣ Oddanie

Wyślij **ten sam link** do repo `PUM_Zadania_[TwojeNazwisko]` (po `push` z pipeline’em).

---

### 🧾 Kryteria oceny (propozycja)

| Kryterium                                                    | Punkty     |
| ------------------------------------------------------------ | ---------- |
| Preprocessing datasetów w Kedro                              | 2          |
| Trening modelu i metryki                                     | 3          |
| Połączenie w jeden projekt/pipeline (wiele datasetów / gałęzi) | 2        |
| Wnioski (`model_summary.md`)                                 | 2          |
| Dokumentacja i repo GitHub                                   | 1          |
| **Łącznie**                                                  | **10 pkt** |
