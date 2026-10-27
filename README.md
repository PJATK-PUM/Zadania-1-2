# Zadania 1–2 — jeden projekt Kedro

Oba zadania realizujesz w **jednym wspólnym projekcie Kedro**.
Różnią się etapem pracy i datasetami; na końcu łączysz je w jeden pipeline.

| Etap | Katalog | Co robisz |
|------|---------|-----------|
| Zadanie 1 | [`Zadanie_1/`](./Zadanie_1/) | Tworzysz projekt Kedro, ładujesz datasety, robisz EDA |
| Zadanie 2 | [`Zadanie_2/`](./Zadanie_2/) | W **tym samym** projekcie dodajesz preprocess + model + ewaluację i spinasz pipeline |

### Idea

* **Jedno repozytorium GitHub** (jedna nazwa projektu) — w nazwie **obowiązkowo numer indeksu** studenta (lub numerów, jeśli praca zespołowa).
* **Każde zadanie ma dedykowany branch** (np. `zadanie-1`, `zadanie-2`).
* **Różne datasety** w Data Catalog (np. kilka plików CSV / różne źródła).
* **Później połączenie**: wspólny pipeline Kedro (`kedro run`), w którym EDA / prepare / train / evaluate korzystają z tych datasetów jako kolejnych stopni przepływu.

### Zasady oddania (obowiązują oba zadania)

1. **Nazwa repo** musi zawierać numer indeksu studenta (lub studentów), np. `PUM_Zadania_s12345` albo `PUM_Zadania_s12345_s67890`.
2. **Każde zadanie** oddajesz z **dedykowanego brancha** z rozwiązaniem tego zadania.
3. Oddanie do oceny: **link do brancha** z rozwiązaniem, przesłany przez **Teams jako link** (nie plik tekstowy z adresem).
4. **Każda poprawka** zadania wymaga przesłania **nowego linka** (do aktualnego stanu brancha / commitów z poprawką).
5. **Commity przesłane po ostatecznym terminie** będą traktowane jako **oszustwo**.
