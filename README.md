# Zadania 1–2 — jeden projekt Kedro

Oba zadania realizujesz w **jednym wspólnym projekcie Kedro**.
Różnią się etapem pracy i datasetami; na końcu łączysz je w jeden pipeline.

| Etap | Katalog | Co robisz |
|------|---------|-----------|
| Zadanie 1 | [`Zadanie_1/`](./Zadanie_1/) | Tworzysz projekt Kedro, ładujesz datasety, robisz EDA |
| Zadanie 2 | [`Zadanie_2/`](./Zadanie_2/) | W **tym samym** projekcie dodajesz preprocess + model + ewaluację i spinasz pipeline |

### Idea

* **Jeden repozytorium GitHub** (jedna nazwa projektu).
* **Różne datasety** w Data Catalog (np. kilka plików CSV / różne źródła).
* **Później połączenie**: wspólny pipeline Kedro (`kedro run`), w którym EDA / prepare / train / evaluate korzystają z tych datasetów jako kolejnych stopni przepływu.
