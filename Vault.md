Vault jest autorską usługą przechowywania danych w chmurze, najczęściej wykorzystywaną jako miejsce do trzymania kopii zapasowych. Istnieje również możliwość wykorzystania go jako tzw. persistance storage dla kontenerów dockerowych.

## Dostęp
### - przez konsolę webową
##### *Dostęp uzyskuje się wybierając opcję "Konsola" w górnym menu (3 kropkowe).* 

Pierwsze wywołanie / połączenie z konsolą może potrwać dłuższą chwilę. Spowodowane jest to koniecznością uruchomienia tymczasowego kontenera, umożliwiającego dostęp zdalny.

### - przez ssh/scp
Dokładny adres do połączenia wraz z użytkownikiem można znaleźć w zakładce "Ogólne". Przykładowo 5aa15fb64b1baa75e781@vault.pl-waw-1.hyperone.com. Dostęp możliwy jest po kluczu lub przy użyciu hasła. Tutaj podobnie jak w przypadku konsoli webowej, trzeba zaczekać kilkanaście sekund w przypadku pierwszego dostępu w określonym czasie.

##Metody autentyfikacji
Dosyć niespotykana jest możliwość tworzenie wielu dostępów dla tego samego użytkownika. Do wyboru jest autoryzacja po kluczu publicznym ssh lub przy użyciu hasła. Oczywiście ta pierwsza jest zalecana. 

## Migawki
Dla każdego vaulta można wykonać wiele migawek, czyli tzw. snapshotów. Dostęp do nich odbywa się poprzez konsolę/ssh/sftp, a dokładniej /data/.zfs/snapshot/identyfikator_migawki. Są one dostępne w trybie tylko do odczytu. Daje to zwiększony poziom bezpieczeństwa, ponieważ dane nie są narażone na modyfikacje np. poprzez złośliwe oprogramowanie. Wykorzystano tu system plików zfs.

## Funkcje dodane
Przede wszystkim ilość vaultów i ich migawek jest nieograniczona. Dobrą praktyką jest tworzenie osobnych vaultów per serwer. Istnieje oczywiście możliwość nadawania im oraz poszczególnym migawkom indywidualnych nazw w celu lepszego uporządkowania. Służy do tego wykropkowany przycisk przy nazwie każdego z nich. Zawsze możemy zmienić rozmiar naszego vaulta (10GB-1000GB). Wraz z "naszym magazynem" plików dostajemy bardzo przydatne narzędzie jakim jest konsola linuksowa, dająca do dyspozycji kilka niezbędnych komend do zarządzania plikami. Użytkownicy systemów unixowych napewno to docenią.

## Kończenie pracy
Przed usunięciem danego vaulta, należy wpierw pozbyć się wszystkich jego snapshotów. 