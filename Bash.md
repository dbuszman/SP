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

```sh
cd praca/zlecenia/zrealizowane
mv rachunki.txt wykonano.txt
cd ../..
```

6\.Utwórz plik wykonano.txt wielkości 11 bajtów, następnie podziel go pliki wielkości 5 bajtów. W ten sposób otrzymasz 3 pliki. (split)

```sh
cat>wykonano.txt
0123456789
split -b5b wykonano.txt
```

7\.
```sh
cp -p ../../praca/zlecenia/zrealizowane/{xaa,xab,xac} ../../praca/dokumenty
```
