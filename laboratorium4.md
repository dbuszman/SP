## Laboratorium 4

1\.Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże. 

```sh
ls -F | tr a-z A-Z | sed -e '/[/]$/d'
```

2\.Wyświetl listę praw dostępu do plików w aktualnym katalogu, ich rozmiar i nazwę.

```sh
ls -l | tr -s " " | cut -f 1,2,5,9 -d " " | sed -e '/^d/d'
```

3\.Wyświetl listę plików w aktualnym katalogu, posortowaną według rozmiaru pliku.

```sh
ls -l | tr -s " " | sed -e '/^d/d' | cut -f 5,9 -d " " | sort -n
```

4\.Wyświetl zawartość pliku */etc/passwd* posortowaną według numerów UID w kolejności od największego do najmniejszego.

```sh
cat /etc/passwd | sort -t ":" -k 3 -nr
```

5\.Wyświetl zawartość pliku /etc/passwd posortowaną najpierw według numerów GID w kolejności od największego do najmniejszego, a następnie UID.

```sh
cat /etc/passwd | sort -t ":" -k 4 -nr -k 3 -nr
```

6\.Podaj liczbę plików każdego użytkownika.

```sh
find / -printf "%U\n" | sort | uniq -c | sort
```

7\.Sporządź statystykę praw dostępu (dla każdego z praw dostępu podaj ile razy zostało ono przydzielone).

```sh 
find -printf "%m\n" | sort | uniq -c
```


8\.

```sh

ls -l > lsout.txt                          #  1
```
Zapisze do pliku *lsout.txt* listę plików w bieżącym katalogu.

```sh
ls -la >> lsout.txt                        #  2
```
Dopisze do pliku *lsout.txt* ukryte pliki z bieżącego katalogu.

```sh
ps >> psout.txt                            #  3
```
Dopisze do pliku *psout.txt* listę aktywnych procesow.

```sh
free -m >> ~/wynik                         #  4
```
Dopisze do pliku *wynik* znajdującego sie w katalogu domowym informacje o wolnej i wykorzystanej pamieci operacyjnej w megabajtach.

```sh
kill -1 1234 > killout.txt 2>killerr.txt   #  5
```
Kończy proces o identyfikatorze 1234 i przakazuje komunikaty informacyjnych do pliku *killout.txt*, a bledy zapisuje do pliku *killerr.txt*

```sh
kill -1 1234 > killout.txt 2>&1            #  6
```
Kończy proces o identyfikatorze 1234 - komunikaty informacyjne oraz błedy zapisuje do pliku *killout.txt*

```sh
kill -1 1234 > /dev/null 2>&1              #  7
```
Kończy proces o identyfikatorze 1234 - nie wyświetla żadnych informacji

```sh
sort psout.txt > pssort.txt                #  8
```
Sortuje dane w pliku psout.txt i zapisuje wynik sortowania w pliku *pssort.txt*

```sh
ps | sort > pssort.txt                     #  9
```
Sortuje listę aktywnych procesow i zapisuje otrzymany wynik do pliku *pssort.txt*

```sh
cat lsout.txt | sort > lssort.txt          # 10
```
Sortuje zawartość pliku *lsout.txt* i zapisuje wynik do pliku *lssort.txt*

```sh
who | sort | more                          # 11
```
Sortuje listę zalogowanych uzytkownikow i wyświetla tyle ile się zmieści na stronie - umożliwiając przewijanie listy w doł.

```sh
who | sort | less                          # 12
```
Sortuje listę zalogowanych uzytkownikow i wyświetla tyle ile się zmieści na stronie - umożliwiając przewijanie listy w doł lub góre.

```sh
find -type f | wc                          # 13
```
Wyświetla liczbę linii, słów (liczbę plików w bieżącym katalogu i podkatalogach) i bajtów 

```sh
find -type f -print0 | wc --files0-from=-  # 14
```
Wyświetla liczbę linii, słów i bajtów we wszystkich znalezionych plikach (w bieżącym katalogu i podkatalogach)
