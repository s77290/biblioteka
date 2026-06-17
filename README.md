# 📚 Biblioteka — projekt semestralny

Prosta aplikacja webowa do zarządzania kolekcją książek, zrealizowana w ramach przedmiotu *Wprowadzenie do technologii internetowych*.

🔗 **Działająca aplikacja:** [biblioteka-77290.web.app](https://biblioteka-77290.web.app)

---

## Opis projektu

Aplikacja pozwala na przechowywanie, przeglądanie i zarządzanie osobistą kolekcją książek online. Dane są zapisywane w chmurze (Firebase Firestore), dzięki czemu są dostępne z każdego urządzenia po wejściu na stronę aplikacji.

## Funkcjonalności

### Wymagania minimalne (zrealizowane)
- formularz dodawania książki (tytuł, autor, rok, gatunek, opis),
- zapisywanie książki do bazy danych (Firestore),
- wyświetlanie listy wszystkich książek,
- aplikacja działa online na hostingu (Firebase Hosting).

### Funkcje dodatkowe
- wyszukiwanie książek po tytule lub autorze,
- widok szczegółów książki w oknie modalnym,
- usuwanie książek z kolekcji,
- ocena książek w systemie gwiazdek (1–5),
- możliwość dodania okładki książki (URL obrazka),
- przełącznik jasnego / ciemnego motywu (zapisywany w pamięci przeglądarki),
- panel statystyk — wykres liczby książek według gatunku,
- losowanie przypadkowej książki z kolekcji.

## Stos technologiczny

| Warstwa | Technologia |
|---|---|
| Frontend | HTML, CSS, JavaScript (bez frameworków) |
| Baza danych | Firebase Firestore |
| Hosting | Firebase Hosting |

## Struktura projektu

```
biblioteka/
├── index.html      — strona główna: lista książek, wyszukiwanie, statystyki
├── add.html        — formularz dodawania nowej książki
├── style.css       — wspólne style (jasny i ciemny motyw)
├── firebase.json   — konfiguracja Firebase Hosting
└── .firebaserc     — przypisanie projektu Firebase
```

## Model danych

Każda książka zapisana w kolekcji `books` w Firestore zawiera pola:

| Pole | Typ | Opis |
|---|---|---|
| `title` | string | Tytuł książki (wymagane) |
| `author` | string | Autor (wymagane) |
| `year` | number / null | Rok wydania |
| `genre` | string / null | Gatunek |
| `description` | string / null | Opis książki |
| `coverUrl` | string / null | Adres URL okładki |
| `rating` | number (0–5) | Ocena w gwiazdkach |
| `createdAt` | timestamp | Data dodania (ustawiana automatycznie) |

## Uruchomienie lokalnie

Aplikacja nie wymaga procesu budowania — to czysty HTML/CSS/JS. Wystarczy otworzyć plik `index.html` w przeglądarce lub wystawić katalog na lokalnym serwerze.

Wdrożenie na hosting (po instalacji [Firebase CLI](https://firebase.google.com/docs/cli)):

```bash
firebase login
firebase deploy
```

## Autor

Vadym Ivantsiv, nr albumu 77290 — Uczelnia Vistula w Warszawie
