## Laboratorium 2

1\. Wyświetl na ekran 2 pierwsze wiersze pliku program.c. (head)

```sh
head -2 program.c
```

2\. Wyświetl na ekran 4 ostatnie wiersze pliku program.c. (head, tail)

```sh
tail -4 program.c
```

3\. W pliku program.c znajdź wszystkie wiersze z wystąpieniem słowa „main”. (grep)

```sh
grep main program.c
```

4\. Plikowi program.c nadaj następujące uprawnienia: właściciel – czytanie, pisanie, grupa – czytanie, pozostali użytkownicy: brak uprawnień. (chmod)

```sh
chmod 640 program.c
```

5\. Będąc w katalogu temp przenieś katalog wazne-sprawy do katalogu praca.

```sh
mv dom/wazne-sprawy praca
```

6\. Zarchiwizuj cały katalog temp. (zip i tar)

```sh
tar -cf tmp.tar.gz tmp
```

7\. Usuń katalog temp.

```sh
rm -rf tmp
```

8\. Odtwórz z archiwum katalog temp. (unzip i tar)

```sh
tar -xf tmp.tar.gz
```

9\. Posprzątaj na swoim koncie.

```sh
rm -rf tmp.tar.gz
```

10\. Dodatkowe zad. Wyświetl linie ze środka programu

Wyswietla linijki od 1 - 7
```sh
head -n 7 program.c 
```
wyswietla linijki od 4 -7

```sh
head -n 7 program.c | tail -n 3
```

11\. Wyswietl 5 linii od końca.

```sh
tail -n 5 program.c 
```

Wyświetl 5,4,3 linijke od końca.

```sh
tail -n 5 program.c | head -n 3 
```

12\. To samo co ostatnio za pomoca polecenia *tac*.

```sh
tac program.c |head -n 7 | tail -n 3 | tac
```
