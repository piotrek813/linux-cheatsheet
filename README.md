# Linux Cheatsheet



1. [Zarządzanie modułami](#Zarządzanie-modułami)
2. [Zarządzanie pakietami](#Zarządzanie-pakietami)
3. [Zdalna administracja](#Zdalna-administracja)
4. [Tar](#Tar)
5. [Zarządzanie użytkownikami i grupami](#Zarządzanie-użytkownikami-i-grupami)
6. [Zarządzanie dyskami / partycjonowanie](#Zarządzanie-dyskami-/-partycjonowanie)

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



### Tar

`tar -czvf archiwum.tar.gz pliki_do_spakowania `- pakuje

`tar -xzvf archiwum.tar.g` - rozpakowuje

`tar -tzvf archiwum.tar.gz` - wyświetla pliki

`tar -rvf archiwum.tar.gz nowy_plik` - dodaje plik do archiwum

tar -uvf archiwum.tar.gz katalog_z_plikami



`tar czv-g /tmp/snapshot_file -f /tmp/htdocs_full.tar.gz htdocs` - kopia pełna

`tar czv-g /tmp/snapshot_file–f /tmp/htdocs_incremental.tar.gz htdocs` - kopia przyrostowa

`tar xzf/tmp/htdocs_incremental.tar.gz` - odtworzenie kopii zapasowej



### Zarządzanie użytkownikami i grupami

`useradd imię -c "Pełne imię" -m`

`-m` dodaje katalog domowy

`userdel -r imię` - usuwa użytkownika wraz z katalogiem domowym

![passwd](https://imgur.com/1K62uPD.png)

![shadow](https://imgur.com/aohIwnJ.png)



### Zarządzanie dyskami / partycjonowanie

`df -hT` - pokazuje wolne miejsce na dyskach

`-h` - rozmiar

`-T` - wypisuje typy plików systemowych
