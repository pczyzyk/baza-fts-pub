# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.4.6] - 2020-01-28
### Added
- Dodano podgląd zarejestrowanych zawodników i przypisanych sędziów do panelu sędziego głównego

### Fixed
- 

## [1.4.5] - 2019-11-15
### Added
- Dodano podgląd zarejestrowanych zawodników i przypisanych sędziów do panelu sędziego głównego

### Fixed
- Naprawiono drukowanie numerów startowych

## [1.4.4] - 2019-10-25
### Added
- Dodano obsługę wielu klubów przypisanych do jednego konta

### Fixed
- Naprawiono sprawdzanie aktywności tancerzy w panelu rejestracji (zatwierdzenie wniosków + 30 dni na załatwienie sprawy)

### Changed
- Zmieniono sortowanie sędziów w wydrukach i panelu sędziego głównego - obecnie są sortowani według liter

## [1.4.3] - 2019-10-09
### Added
- Dodano wydruk paneli sędziowskich z sędziami jako wierszami

### Changed
- Zmieniono wczytywanie informacji o licencji WDSF w panelu check-in z synchronicznego na asynchroniczny

## [1.4.2] - 2019-10-02
### Added
- Dodano wyświetlanie godzin rozpoczęcia kategorii podczas rejestracji w przypadku turniejów festiwalowych

### Fixed
- Poprawiona rejestracja par na turnieje WDSF - sprawdzanie licencji WDSF nie było poprawne w przypadku turniejów festiwalowych
- Poprawione dodawanie pary z bazy WDSF przez panel Check-in
- Poprawiona rejestracja par rekreacyjnych - nie mogą zarejestrować się na turnieje OPEN

### Changed
- Data kategorii jest pobierana jako data bloku, w którym rozgrywana jest kategoria
- Przyspieszono renderowanie formatki turnieju w panelu administracyjnym - pobieranie większości relacji podrzędnych zmieniono na EXTRA_LAZY
- Zmieniono user_manager na user_provider i dodano możliwość logowania za pomocą adresu email

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
