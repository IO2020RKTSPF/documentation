# "Podziel się książką"

## Spis treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Opis ogólny](#2-opis-ogólny)
3. [Wymagania funkcjonalne](#3-wymagania-funkcjonalne)
4. [Wymagania niefunkcjonalne](#4-wymagania-niefunkcjonalne)
5. [Model systemu](#5-model-systemu)
6. [Autorzy](#6-autorzy)

## 1. Wprowadzenie

Każdy czytający książki wie, że zdobycie interesującej go pozycji nie zawsze jest proste. Strona internetowa "Podziel się książką" umożliwia łatwe dzielenie się swoją kolekcją książek przy użyciu prywatnych wirtualnych bibliotek, w których inni użytkownicy mogą odnaleźć interesujące ich tytuły. Dzięki temu, książki zalegające dotychczas na półce mogą odnaleźć nowych czytelników, po czym zostaną zwrócone do ich właściciela. Łatwa wymiana książkami to prawdziwa gratka dla ich miłośników.

## 2. Opis ogólny

Aplikacja "Podziel się książką" to strona internetowa na której użytkownicy dokonują wymian oraz wypożyczeń książek. Wymiana/wypożyczenie może odbywać się za darmo lub za drobną opłatą. Użytkownicy aplikacji mogą tworzyć własne wirtualne biblioteki które każdy może przeglądać. Jeżeli użytkownik zdecyduje się na wypożyczenie książki, jej właściciel zostaje o tym poinformowany i kontaktuje się z zainteresowanym. Użytkownicy wystawiają sobie wzajemnie oceny, co pozwala na zmniejszenie ryzyka utraty książki.

### Frontend
  Nazwa pliku  | Zrzut ekranu |
|--------------|--------------|
| SearchPage   | ![index](https://github.com/IO2020RKTSPF/documentation/blob/master/images/index.png)
| MyBookPage   | ![my-books](https://github.com/IO2020RKTSPF/documentation/blob/master/images/my-books.png)
| AddBookPage  | ![index](https://github.com/IO2020RKTSPF/documentation/blob/master/images/index.png)
| MessagesPage | ![my-books](https://github.com/IO2020RKTSPF/documentation/blob/master/images/my-books.png)
| MessagePage  | ![index](https://github.com/IO2020RKTSPF/documentation/blob/master/images/index.png)

## 3. Wymagania funkcjonalne

### Podstawowe

1. Logowanie/wylogowywanie
   - Użytkownik może się logować przy użyciu konta Facebook lub konta Google. Oraz wylogować się w każdym momencie
2. Dodawanie książek do własnej wirtualnej biblioteki
   - Wirtualna biblioteka to spis książek które chcemy komuś wypożyczyć
3. Wypożyczanie książki
   - Wypożyczenie książki sprawia że książka ta znika z biblioteki
4. Przeszukiwanie całego zbioru książek dostępnych do wypożyczenia
5. Wysyłanie propozycji wymiany do właściciela
6. Przeglądanie biblioteki innego użytkownika
   -Każdy użytkownik ma możliwość przeglądania książek w bibliotece innego użytkownika
7. Chat między użytkownikami w celu uzgodnienia szczegółów wypożyczenia
8. Usuwanie książki w wirtualnej biblioteki
   -Użytkownik ma możliwość w dowolnym momencie usunąć wcześniej dodaną książkę bez podawania przyczyny

### Poboczne

1. Dodawanie pozycji do swojej listy życzeń
2. Przeglądanie książek odpowiadających tym, które są w liście życzeń
3. Filtrowanie - Według tagów - Według gatunków - Według średniej oceny użytkownika - Według odległości
   4.Ocena użytkownika po dokonaniu wypożyczenia

## 4. Wymagania niefunkcjonalne

1. Bezpieczeństwo logowania
   - Bezpieczństwo logowania osiągamy dzięki logowaniu za pomocą facebook/google
2. Dostosowanie strony do użytkowania przez osoby niepełnosprawne
   - Zmiana kontrastu
   - Zmiana rozmiaru czcionki
3. Opcja zmiany języka między polskim i angielskim
4. Wysłanie prośby o wypożyczenie nie powinno zajmować dłużej niż 1 minutę
5. Dodanie nowej oferty wypożyczenia nie powinno zajmować dłużej niż 2 minuty
6. Zmiana zdjęcia profilowego

## 5. Model systemu

### Front-end

1. Strona internetowa - React.js

   - Interfejs graficzny
   - Rudo-szara kolorystyka
   - Wysyłanie danych do API
   - Odbieranie danych z API

2. Aplikacja mobilna na system Androd

   - UI w frameworku flutter
   - Napisana w jęzuku Kotlin
   - Firebase
     - Obsługa logowania
     - Obsługa powiadomień
     - Komunikacja z API

### Back-end

1. ASP.NET (API)

   - Łączy się z bazą danych i sprawuję pomost między bazą danych a stroną internetową/aplikacją mobilną
   - Przetwarza dane wysłane ze strony
   - Testowanie oraz generowanie dokumentacji przy użyciu **_swaggera_**
   - Autentykacja przy użyciu **_facebook/oauth_**

2. Docker

   - Oddzielenie architektury projektu od systemu operacyjnego serwera

3. Baza danych

   - Baza danych na serwerze MariaDB
   - Struktura bazy danych:

     1. **Users**
        - **_UserID_**
        - Name
        - Email
        - Token
        - ImgUrl
        - City
     2. **Books**
        - Title
        - PricePerMonth
        - Description
        - ImgUrl
        - Tag
        - Genre
     3. **Transactions**
        - TransactionID
        - UserID
        - BookID
        - RentalTime

## 6. Autorzy

- Tomasz Steblik
- Rafał Kulka
- Piotr Florczak
