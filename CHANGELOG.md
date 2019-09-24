# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.4.2] - 2019-09-24
### Added
- Dodano wyświetlanie godzin rozpoczęcia kategorii podczas rejestracji w przypadku turniejów festiwalowych

### Fixed
- Poprawiona rejestracja par na turnieje WDSF - sprawdzanie licencji WDSF nie było poprawne w przypadku turniejów festiwalowych

### Changed
- Data kategorii jest pobierana jako data bloku, w którym rozgrywana jest kategoria
- Przyspieszono renderowanie formatki turnieju w panelu administracyjnym - pobieranie większości relacji podrzędnych zmieniono na EXTRA_LAZY

## [1.4.1] - 2019-09-15
### Added
- Transliteracja cyrylicy i znaków narodowych do alfabetu łacińskiego w pliku UNOS i checkin.csv
- Obsługa statusu check-in - można zamykać/otwierać poszczególne kategorie. Przy logowaniu jako skrutiner możliwe jest dopisywanie/rejestrowanie par ignorując status. Z tego powodu bezwzględnie dla osób trzecich obsługujących check-in należy udostępniać login i hasło dedykowane (zmieniające się każdego dnia)
- W panelu sędziego głównego, w widoku kategorii dostępny jest status check-in oraz aktualna liczba zarejestrowanych par
- W check-in dodano przełącznik WDSF API, który pozwala włączyć/wyłączyć komunikację z API WDSF i sprawdzanie MIN i RLS
- W panelu check-in dodano obsługę czytnika kodów kreskowych

### Fixed
- Poprawione generowanie numerów startowych w Check-in - poprawiona obsługa "jeden numer na parę/oddzielnie na każdy dzień"
- Zabezpieczono błąd, który wyrzucał 500 w przypadku zalogowania do rejestracji kontem, które nie posiada przypisanego żadnego klubu
- Zabezpieczono próbę synchronizacji z WDSF API pary, która w momencie rejestracji nie posiadała przypisanego numeru RLS (występuje w przypadku braku połączenia z WDSF API i rejestracji przez check-in)
- Poprawiono nazwę kategorii w modalu sprawdzania wyników (panel skrutinera) na zgodną z listą kategorii
- Poprawiono wyświetlanie formularza logowania dla klubów FTS w przypadku angielskiej wersji strony rejestracji

### Changed
- Przy generowaniu UNOS i checkin.csv dla kategorii DSE dla polskich tancerzy z bazy brany jest MIN (tak jak wcześniej) a w przypaddku jego braku brany jest polski ID. Dzięki temu bez problemu wczytują się wyniki do bazy. W check-on dla kategorii DSE jest to odzwierciedlone na liście
- Funkcja ściągania plików CSV WDSF została przeniesiona do panelu skrutinera (zębatka)
