# 09 - Pliki i operacje na danych

## Pliki

W Python otwarcie pliku i zapis do niego wykonywany jest w bardzo łatwy sposób. Do otwarcie pliku wykorzystywana jest funkcja `open()`, do której jako argumenty podajemy ścieżkę do pliku i argumenty z jakimi ma zostać otwarty plik (`r` - odczyt, `w` - zapis (kasuje zawartość pliku), `a` - dopisuje do końca pliku, `r+` - odczyt i zapis):

```python
file_r = open('data.txt', 'r')      # otwiera plik do odczytu
data = file_r.read()                # czyta cały plik i przypisuje zawartość do zmiennej
file_r.close()                      # zamyka plik

file_w = open('new_data.txt', 'w')  # otwiera plik do zapisu
file_w.write(data)                  # zapisuje do nowego pliku zawartość odczytaną z pierwszego
file_w.close()                      # zamyka plik
```

Dużo wygodniejsze jest jednak czytanie pliku linia po linii. Otwarty plik może zostać potraktowany jako kolekcja:

```python
file = open('data.txt', 'r')

for line in file:
    print(line)

file.close()
```

Bardzo często dane zapisywane są w plikach tekstowych, w których kolejne wartości oddzielone są konkretnym znakiem, na przykład:

> 1;2;3;4  
> 45;34;12;32;54;21  
> 4;5;6332;23;2

W powyższym przykładzie kolejne liczby oddzielono znakiem średnika (';'). Najprostszym sposobem na odseparowanie kolejnych wartości jest rozdzielenie ciągu znaków odczytanej linii za pomocą funkcji `split()`. Funkcja ta zwraca listę ciągów znaków, które były odseparowane wskazanym znakiem. Poniższy skrypt sumuje liczby w każdej linii pliku:

```python
file = open('numbers_to_sum.txt', 'r')

for line in file:
    numbers_strings = line.split(';')   # dla każdej linii wykonaj pocięcie ciągu na listę
                                        # separatorem kolejnych elementów w linii jest znak: ';'
                                        # zwrócone elementy listy są ciągami znaków
                                        # należy je przekonwertować na wartości liczbowe

    numbers = []                        # utwórz pustą listę

    for nbr in numbers_strings:         # dla każdego elementu z podzielonej linii
        numbers.append(int(nbr))        # dodaj do listy "numbers" element przekonwertowany na liczbę całkowitą
                                        # konwersja na liczbę całkwitą wykonywana jest za pomocą funkcji: `int()`

    print(sum(numbers))                 # wyświetla sumę elementów listy

file.close()
```

> 10  
> 198  
> 6366

---

#### :hammer: :fire: Zadanie :fire: :hammer:

1. 

---

## Zadanie końcowe :fire: :hammer:

## Zadanie domowe :boom: :house:

---

Autorzy: *Tomasz Mańkowski*, *Jakub Tomczyński*
