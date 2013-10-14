### Laboratorium 1

1\. Używając linii poleceń stwórz strukturę katalogów:

```sh
mkdir -p dom nauka/{c,logo,pascal} praca/{dokumenty,zlecenia/{niezrealizowane,zrealizowane}}
```

2\. Przejdź do katalogu dom i utwórz katalog wazne-sprawy.

```sh
cd dom
mkdir wazne-sprawy
cd ..
```

3\.Wejdź do katalogu wazne-sprawy i utwórz tam pusty plik rachunki.txt.
```sh
cd dom/wazne-sprawy
touch rachunki.txt
cd ..
```

4\.Będąc w katalogu wazne-sprawy skopiuj plik rachunki.txt do katalogu zrealizowane.
```sh
cd dom/wazne-sprawy
cp rachunki.txt ../../praca/zlecenia/zrealizowane
cd ../..
```

5\. Przejdź do katalogu zrealizowane i zmień nazwę pliku rachunki.txt na wykonano.txt.

Polecenia: split, cat, diff

```sh
cd praca/zlecenia/zrealizowane


cd ../..
```
