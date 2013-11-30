## Laboratorium 7

1\. W bieżącym katalogu zamienić rozszerzenia wszystkich plików z rozszerzeniem htm na html. Jeżeli w nazwie pliku istnieje spacja, to należy zamienić ją na znak podkreślenia.

```sh
#!/bin/bash

FOUND=0

for filename in *
do
     echo "$filename" | grep -q " "
     if [ $? -eq $FOUND ]
     then
       fname=$filename
       n=$(echo $fname | sed -e "s/ /_/g")
       mv "$fname" "$n"
     fi
done
for filename in *
do
     echo "$filename" | grep -q ".htm$"
     if [ $? -eq $FOUND ]
     then
       fname=$filename
       n=$(echo $fname | sed -e "s/.htm/.html/g")
       mv "$fname" "$n"
     fi
done


exit 0
```

2\. Napisać skrypt zawierający funkcję obliczającą silnię. Następnie należy obliczyć silnię z liczby, która jest argumentem skryptu. W przypadku niepoprawnego argumentu należy wypisać odpowiedni komunikat.

```sh
#!/bin/bash
echo "Podaj argument silni: \n"
read arg
for arg in $arg
do
    WYNIK=1
    LICZNIK=1
    if [ $arg -ge 0 ];
    then
    while [ $LICZNIK -le $arg ]; 
    do
        WYNIK=$[ $WYNIK * $LICZNIK ]
        LICZNIK=$[ $LICZNIK + 1]
    done
    echo "Silnia dla $arg = $WYNIK"
    else
    echo "$arg nie jest poprawnym argumentem"
    fi

done
exit 0 
```

3\. Napisać skrypt zbierający jak najwięcej informacji o użytkowniku, którego login jest argumentem skryptu. Jeżeli skrypt nie ma argumentu, to należy użyć login osoby uruchamiającej skrypt.

4\. Napisz skrypt usuwający z katalogu domowego i jego podkatalogów wszystkie pliki zwykłe o nazwie 'core' starsze niż 3 dni.
