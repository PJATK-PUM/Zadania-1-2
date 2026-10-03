
## 🧩 Zadanie 1 – Eksploracja danych w Dataiku DSS + GitHub

### 🎯 Cel zadania

Nauczyć się pracy w środowisku **Dataiku DSS** oraz podstaw wykorzystania **GitHuba** do dokumentowania i udostępniania wyników analizy danych poprzez:

* zaimportowanie i wstępne poznanie zbioru danych,
* wykonanie podstawowej analizy i wizualizacji,
* sformułowanie prostych wniosków,
* publikację wyników i kodu (np. plików CSV, raportów, zrzutów ekranu) w repozytorium GitHub.

---

### 🧱 Kroki do wykonania

#### 1️⃣ Utwórz nowy projekt w Dataiku DSS

1. Zaloguj się do Dataiku DSS: [http://dataiku.pjwstk.edu.pl:11000/](http://dataiku.pjwstk.edu.pl:11000/)
2. Wejdź do folderu
```
   Kojalowicz/PUM2025/<numer-grupy>c/Zajęcia1/
```
4. Kliknij **+ New Project** i nadaj mu nazwę:
```
   [TwojeNazwisko]
```

5. W polu **Description** wpisz krótki opis, np. „Eksploracja danych Titanic”.

---

#### 2️⃣ Zaimportuj dane

1. Wybierz dataset: **Titanic.csv**
   (jeśli nie ma go w Dataiku, pobierz z [Kaggle: Titanic Dataset](https://www.kaggle.com/c/titanic/data)).
2. Zaimportuj plik do swojego projektu.
3. W zakładce **Explore** sprawdź:

   * ile jest rekordów,
   * jakie są kolumny i ich typy (tekstowe, liczbowe, logiczne),
   * czy występują wartości brakujące.

---

#### 3️⃣ Zbadaj dane

W zakładce **Statistics** lub **Charts** wykonaj podstawowe wizualizacje:

* histogram wieku pasażerów,
* odsetek osób, które przeżyły (kolumna *Survived*),
* rozkład płci (*Sex*),
* zależność wieku od przeżycia (wykres rozrzutu lub boxplot).

💡 **Podpowiedź:** możesz użyć narzędzia drag-and-drop w zakładce **Charts**.

---

#### 4️⃣ Zapisz swoje obserwacje

Odpowiedz na poniższe pytania (możesz zapisać odpowiedzi jako plik `raport.md` lub `raport.txt`):

* Ile rekordów i kolumn zawiera zbiór?
* Jakie trzy zmienne (Twoim zdaniem) najbardziej wpływają na przeżycie?
* Jakie wartości brakujące występują w danych?
* Jakie dwie obserwacje są dla Ciebie najciekawsze?

---

#### 5️⃣ Przygotuj repozytorium GitHub

1. Utwórz **nowe prywatne repozytorium** na GitHubie w ogranizacji **PJATK-PUM** o nazwie:

   ```
   PUM_Zajęcia1_[TwojeNazwisko]
   ```

2. W repozytorium umieść:

   * plik `README.md` z krótkim opisem projektu (cel, dane, wnioski),
   * plik `raport.md` lub `raport.txt` z odpowiedziami na pytania z kroku 4,
   * zrzuty ekranu z Dataiku (np. flow projektu, przykładowe wykresy),
   * opcjonalnie: eksport danych lub wizualizacji (np. `.csv`, `.png`, `.pdf`).

3. Uporządkuj repozytorium, np. w strukturze:

   ```
   /data
     Titanic.csv
   /screenshots
     flow.png
     chart_age.png
   raport.md
   README.md
   ```

4. Dodaj plik `.gitignore` (np. aby nie przesyłać plików tymczasowych lub dużych danych).

---

#### 6️⃣ Prześlij do oceny

1. Upewnij się, że wszystkie pliki są **zatwierdzone i wypchnięte (push)** na GitHub.
2. Wyślij prowadzącemu **link do repozytorium GitHub**, zamiast przesyłać pliki e-mailem.

💡 **Dodatkowo:** możesz dodać do README link do swojego profilu na Dataiku lub krótkie refleksje z pracy.

---

### 📦 Efekt końcowy

Po ukończeniu zadania powinieneś mieć:

* projekt w Dataiku DSS z przeprowadzoną analizą,
* repozytorium GitHub z dokumentacją i wynikami,
* podstawową znajomość pracy z Git i GitHub w kontekście analizy danych.

---

Czy chcesz, żebym dodał do tego też **ocenę punktową (rubrykę)** z kryteriami — np. punkty za poprawność analizy, strukturę repozytorium, jakość README itp.?
