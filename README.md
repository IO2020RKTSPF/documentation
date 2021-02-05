<p align="center">
  <a href="http://podzielsieksiazka.northeurope.cloudapp.azure.com/">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>
  <h1 align="center"><a href="http://podzielsieksiazka.northeurope.cloudapp.azure.com/" target="_blank">Podziel się książką</a></h3>
</p>

## Spis treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Ogólny opis](#2-ogólny-opis)
3. [Konfiguracja](#3-konfiguracja)
4. [Wymagania funkcjonalne](#4-wymagania-funkcjonalne)
5. [Wymagania niefunkcjonalne](#5-wymagania-niefunkcjonalne)
6. [Model systemu](#6-model-systemu)
7. [Autorzy](#7-autorzy)

## 1. Wprowadzenie

Każdy czytający książki wie, że zdobycie interesującej go pozycji nie zawsze jest proste. Strona internetowa "Podziel się książką" umożliwia łatwe dzielenie się swoją kolekcją książek przy użyciu prywatnych wirtualnych bibliotek, w których inni użytkownicy mogą odnaleźć interesujące ich tytuły. Dzięki temu, książki zalegające dotychczas na półce mogą odnaleźć nowych czytelników, po czym zostaną zwrócone do ich właściciela. Łatwa wymiana książkami to prawdziwa gratka dla ich miłośników.

## 2. Ogólny opis

Aplikacja "Podziel się książką" to strona internetowa na której użytkownicy dokonują wymian oraz wypożyczeń książek. Wymiana/wypożyczenie może odbywać się za darmo lub za drobną opłatą. Użytkownicy aplikacji mogą tworzyć własne wirtualne biblioteki. Jeżeli użytkownik zdecyduje się na wypożyczenie książki, jej właściciel zostaje o tym poinformowany i kontaktuje się z zainteresowanym.

### Frontend
  Nazwa pliku  | Zrzut ekranu |
|--------------|--------------|
| SearchPage   | ![index](https://github.com/IO2020RKTSPF/documentation/blob/master/images/index.png)
| MyBookPage   | ![my-books](https://github.com/IO2020RKTSPF/documentation/blob/master/images/my-books.png)
| AddBookPage  | ![add-book](https://github.com/IO2020RKTSPF/documentation/blob/master/images/add-book.png)
| MessagesPage | ![messages](https://github.com/IO2020RKTSPF/documentation/blob/master/images/messages.png)
| MessagePage  | ![message](https://github.com/IO2020RKTSPF/documentation/blob/master/images/message.png)
| LoginPage  | ![login](https://github.com/IO2020RKTSPF/documentation/blob/master/images/login.png)

### Aplikacja mobilna

Nazwa pliku  | Zrzut ekranu |
|--------------|--------------|
| AllBooks     | ![all-books-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/all-books-mobile.jpg)
| SearchPage   | ![search-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/search-mobile.jpg)
| Drawer       | ![drawer-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/drawer-mobile.jpg)
| MyBookPage   | ![your-books-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/your-books-mobile.jpg)
| AddBookPage  | ![offer-create-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/offer-create-mobile.jpg)
| OfferEdit    | ![offer-edit-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/offer-edit-mobile.jpg)
| BookDesc     | ![offer-description-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/offer-description-mobile.jpg)
| Transactions | ![transactions-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/transactions-mobile.jpg)
| MessagePage  | ![transaction-messaging-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/transaction-messaging-mobile.jpg)
| LoginPage  | ![login-mobile](https://github.com/IO2020RKTSPF/documentation/blob/master/images/login-mobile.jpg)

### API
   Opis        | Zrzut ekranu |
|--------------|--------------|
| Przykładowy endpoint służący do logowania się do aplikacji | ![login](https://github.com/IO2020RKTSPF/documentation/blob/master/images/logowanie.PNG)
| Przykładowa struktura obiektu w bazie danych | ![struktura](https://github.com/IO2020RKTSPF/documentation/blob/master/images/struktura.PNG)

### Pozostałe endpointy oraz obiekty można znaleźć na: http://podzielsieksiazka.northeurope.cloudapp.azure.com:8080/index.html

## 3. Konfiguracja
### Przed uruchomieniem
Upewnij się, że środowisko, w którym będziesz chciał wykonać inicjalizacje aplikacjie ma:
1. Skonfigurowanego Dockera
```
$ docker version

Client:
 Version:           19.03.8
 API version:       1.40
 Go version:        go1.12.17
 Git commit:        afacb8b
 Built:             Wed Mar 11 01:21:11 2020
 OS/Arch:           darwin/amd64
 Context:           default
 Experimental:      true

Server:
 Engine:
  Version:          19.03.8
  API version:      1.40 (minimum version 1.12)
  Go version:       go1.12.17
  Git commit:       afacb8b
  Built:            Wed Mar 11 01:29:16 2020
  OS/Arch:          linux/amd64
  Experimental:     true
 containerd:
  Version:          v1.2.13
  GitCommit:        7ad184331fa3e55e52b890ea95e65ba581ae3429
 runc:
  Version:          1.0.0-rc10
  GitCommit:        dc9208a3303feef5b3839f4323d9beb36df0a9dd
 docker-init:
  Version:          0.18.0
  GitCommit:        fec3683
```
2. Skonfigurowanego Docker Compose
```
docker-compose --version

docker-compose version 1.27.4, build 01110ad01
```
### Inicjalizacja
1. Sklonuj repozytoria ![api](https://github.com/IO2020RKTSPF/api) oraz ![frontend](https://github.com/IO2020RKTSPF/frontend).
```
$ mkdir podziel-sie-ksiazka
$ cd podziel-sieksiazka
$ git clone https://github.com/IO2020RKTSPF/api.git
$ git clone https://github.com/IO2020RKTSPF/frontend.git
```
2. Przejdź do katalogu frontend i skonfiguruj plik .env. W miejcre [ ] wprowadź własne apps.googleusercontent.com.
```
$ cd podziel-sie-ksiazka/frontend
$ cp .env.sample .env
$ vi .env

REACT_APP_WEBSITE_NAME=Podziel się książką
REACT_APP_GOOGLE_CLIENT_ID=[TUTAJ WPISZ WłASNE APPS.GOOGLEUSERCONTENT.COM]
REACT_APP_API_URL=http://localhost:8080/
```
3. Teraz przejdź do katalogu api i również skonfiguruj plik .env. W miejsce [ ] wpisz nazwę bazy danych oraz hasło dostępu.
```
$ cd podziel-sie-ksiazka/api
$ cp .env.sample .env
$ vi .env

MYSQL_DATABASE=[TUTAJ WPISZ NAZWĘ BAZY DANYCH]
MYSQL_ROOT_PASSWORD=[TUTAJ WPISZ HASŁO DO UŻYTKOWNIKA ROOT W BAZIE DANYCH]
```
### Uruchomienie
1. Uruchom środowisko aplikacji. **Ważne aby znajdować się w katalogu api**.
```
$ cd podziel-sie-ksiazka/api
$ docker-compose up
```
### Sprawdzenie poprawności działani konfiguracji
Jeżeli wszystko poszło pomyślnie. To na stronie http://localhost:3000/ powinieneś zobaczyć działającą aplikacjię.

### Inicjalizacja aplikacji mobilnej

1. Aplikacja do działania wymaga Firebase i Scaledrone. Należy utworzyć odpowiednie konta w tych usługach.

2. Należy utworzyć google-services.json z Firebase i umieścić w katalogu app w plikach źródłowych aplikacji mobilnej. Jest to konieczne dla funkcjonowania logowania google. Dodatkowo należy utworzyć nową aplikację w konsoli Firebase, włączyć logowanie google, oraz dodać w niej klucz sha-1 z android sdk którym została zbudowana.

3. Następnie należy utworzyć kanał na Scaledrone i umieścić jego id w kodzie aplikacji co pozwoli na obsługę wiadomości między użytkownikami. 

## 4. Wymagania funkcjonalne

### Podstawowe

1. Logowanie/wylogowywanie
   - Użytkownik może się logować przy użyciu konta Facebook lub konta Google. Oraz wylogować się w każdym momencie
2. Dodawanie książek do własnej wirtualnej biblioteki
   - Wirtualna biblioteka to spis książek które chcemy komuś wypożyczyć
3. Wypożyczanie książki
   - Wypożyczenie książki sprawia że książka ta znika z biblioteki
4. Przeszukiwanie całego zbioru książek dostępnych do wypożyczenia
5. Wysyłanie propozycji wymiany do właściciela

### Poboczne

1. Chat między użytkownikami w celu uzgodnienia szczegółów wypożyczenia

## 5. Wymagania niefunkcjonalne

1. Bezpieczeństwo logowania
   - Bezpieczństwo logowania osiągamy dzięki logowaniu za pomocą facebook/google
2. Opcja zmiany języka między polskim i angielskim
3. Wysłanie prośby o wypożyczenie nie powinno zajmować dłużej niż 1 minutę
4. Dodanie nowej oferty wypożyczenia nie powinno zajmować dłużej niż 2 minuty


## 6. Model systemu

### Front-end

1. Strona internetowa - React.js

   - Interfejs graficzny
   - Kolorystyka zgodna z logiem
   - Wysyłanie danych do API
   - Odbieranie danych z API

2. Aplikacja mobilna na system Androd

   - Napisana w jęzuku Java
   - Firebase
     - Obsługa logowania
     - Obsługa powiadomień
   - Retrofit
     - Komunikacja z API
   - Scaledrone
     - Obsługa chatu między użytkownikami

### Back-end

1. ASP.NET (API)

   - Łączy się z bazą danych i sprawuję pomost między bazą danych a stroną internetową/aplikacją mobilną
   - Przetwarza dane wysłane ze strony
   - Testowanie oraz generowanie dokumentacji przy użyciu **_swaggera_**
   - Autentykacja przy użyciu **_facebook/oauth_**
   - Do autoryzacji wykorzystany token jwt
   - Baza danych oraz API napisane z podejściem **CODE FIRST**

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

## 7. Autorzy

- Tomasz Steblik
- Rafał Kulka
- Piotr Florczak
