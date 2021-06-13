# Linux Cheatsheet

------



1. [Zarządzanie modułami](#Zarządzanie modułami)
2. [Zarządzanie pakietami](#Zarządzanie pakietami)
3. [Zdalna administracja](#Zdalna administracja)

### Zarządzanie modułami

`lsmod` – pokaż załadowane moduły jądra
`rmmod` – usuwa moduł
`modprobe` – ładuje moduł
`modprobe -c` wyświetla konfiguracje modułów
`depmod -v` – wyswitla liste zależności pomiędzy modułami

### Zarządzanie pakietami

`rpm -qf /usr/bin/wget` – z jakim pakietem został zainstalowany plik
`rpm -qi wget` – informacje o pakiecie
`rpm -ql wget` – pliki zainstalowane z tym pakietem
`rpm -V wget` – jakie pliki uległy zmianie od zainstalowania pakietu
`rpm -qg wget` – pliki dokumentacji pakietu

Globalny plik konfiguracyjny dla polecenia rpm to /usr/lib/rpm/rpmrc.

`zypper sl` – repozytoria
`zypper ar http://172.17.8.101/suse repo1` - dodaj repo
`zypper rr repo1` – usuwanie repozytorium
`zypper info joe` – info o pakiecie
`zypper remove joe` – usuwa pakiet

### Zdalna administracja

`sftp user@ip`

`scp source destination`

`scp user@ip:remote/path local/path` - pobieranie
`scp local/path user@ip:remote/path` - przesylanie

Konfigurację klienta SSH wykonuje się zmieniając wpisy w pliku /etc/ssh/ssh_config lub/i dla każdego użytkownika indywidualnie - w pliku ~/.ssh/config
