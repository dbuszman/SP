## Laboratorium 4

1\.Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże. 

```sh
ls -F | tr a-z A-Z | sed -e '/[/]$/d'
```

2\.Wyświetl listę praw dostępu do plików w aktualnym katalogu, ich rozmiar i nazwę.

```sh
ls -l | tr -s "[ ]" "[ ]" | cut -f 1,2,5,9 -d " " | sed -e '/^d/d'
```

3\.Wyświetl listę plików w aktualnym katalogu, posortowaną według rozmiaru pliku.

```sh
ls -l | tr -s "[ ]" "[ ]"| sed -e '/^d/d' | cut -f 5,9 -d " " | sort -n
```

4\.Wyświetl zawartość pliku */etc/passwd* posortowaną według numerów UID w kolejności od największego do najmniejszego.

```sh
cat /etc/passwd | sort -t ":" -k 3 -n
```

5\.Wyświetl zawartość pliku /etc/passwd posortowaną najpierw według numerów GID w kolejności od największego do najmniejszego, a następnie UID.

```sh
cat /etc/passwd | sort -t ":" -k 4 -nr -k 3 -nr
```
