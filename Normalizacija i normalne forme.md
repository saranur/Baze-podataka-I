## Normalizacija i normalne forme

<hr>

Normalizacija - proces koji koristimo da optimiziramo i organizujemo bazu podataka i podatke koji se nalaze u njoj. Želimo da: 

- otklonimo logičke nekonzistentnosti i greške 
- smanjimo/otklonimo redundansku (ponavljanje podataka)

Normale forme: 1NF, 2NF, 3NF, 4NF, 5NF, BCNF (Boyce-Codd-ova NF)

<hr>

**1. Normalna Forma - 1NF**

<hr>

**Relacija R ** je u prvoj normalnoj formi 1NF **akko** su vrijednosti svih njenih atributa **atomske/ atomarne**. Dakle, u jednom redu- za jedan atribut može biti samo jedna informacija. 

<u>npr.</u>

| STUDENT | GODINE |  PREDMET   |
| :-----: | :----: | :--------: |
| Mrijana |   20   |  MM3, PR3  |
|  Emin   |   21   |    PR2     |
|  Anela  |   22   | Statistika |

**TABELA NIJE U 1NF JER U JEDNOM REDU POSTOJE DVIJE INFORMACIJE, MM3 I PR3.**

**Normalicijom dobijemo**

| STUDENT | GODINE |  PREDMET   |
| :-----: | :----: | :--------: |
| Mrijana |   20   |    MM3     |
| Mirjana |   20   |    PR3     |
|  Emin   |   21   |    PR2     |
|  Anela  |   22   | Statistika |

**TABELA JESTE U 1NF**

<hr>

**2. Normalna forma - 2NF** 

<hr>

**Relacija R** je u drugoj normalnoj formi **akko** je u **1NF** i ako svi njeni neključni atributi u potpunosti funkcionalno zavise od primarnog ključa. Pomoću ove forme ćemo također riješiti problem redundanse koji se može pojaviti u 1NF. 

primarni ključ (student, predmet)

| STUDENT | GODINE |  PREDMET   |
| :-----: | :----: | :--------: |
| Mrijana |   20   |    MM3     |
| Mirjana |   20   |    PR3     |
|  Emin   |   21   |    PR2     |
|  Anela  |   22   | Statistika |

**TABELA NIJE U 2F JER POSTOJI NEKLJUČNI ATRIBUT (ATRIBUT GODINE) KOJI SAMO FUNKCIONALNO ZAVISE OD STUDENTA ALI NE I PREDMETA.  **

| STUDENT | GODINE |
| :-----: | :----: |
| Mrijana |   20   |
|  Emin   |   21   |
|  Anela  |   22   |

Sada smo dvije zasebne tabele. Napravili smo zasebnu tabelu STUDENT i GODINE gdje atribut GODINE u potpunosti funckionalno zavise od studenta. 

| STUDENT |  PREDMET   |
| :-----: | :--------: |
| Mirjana |    PR3     |
| Mrijana |    MM3     |
|  Emin   |    PR2     |
|  Anela  | Statistika |

Napravili smo zasebnu tabelu STUDENT i PREDMET gdje atribut PREDMET u potpunosti funkcionalno ovisi o primarnom ključu - STUDENT. 

**TABELA JESTE U 2NF**

<hr>

**3. Normalna forma - 3NF**

<hr>

**Relacija R** je u trećoj normalnoj formi 3NF **akko** je u **2NF** i ako su svi njeni neključni atributi **netranzitivno zavise** od primarnog ključa. 

| STUDENT ID# | IME STUDENTA# |   GRAD   | DATUM ROĐENJA | POŠTANSKI BROJ |
| :---------: | :-----------: | :------: | :-----------: | :------------: |
|   IB1616    |     Amar      |  Mostar  |  16.12.1999   |     88000      |
|   IB1818    |     Emma      | Sarajevo |  21.08.2000   |     71000      |

**TABELA NIJE 3NF JER POSTOJI NEKLJČNI ATRIBUT (GRAD) KOJI ZAVISI OD DRUGOG NEKLJUČNOG ATRIBUTA (POŠTANSKI BROJ)**

| STUDENT ID# | IME STUDENTA# | DATUM ROĐENJA | POŠTANSKI BROJ |
| :---------: | :-----------: | :-----------: | :------------: |
|   IB1616    |     Amar      |  16.12.1999   |     88000      |
|   IB1818    |     Emma      |  21.08.2000   |     71000      |

**Izostavili smo neključni atribut - Grad koji zavisi od drugog neključnog atributa - Poštanski broj**

| POŠTANSKI BROJ# |   GRAD   |
| :-------------: | :------: |
|      88000      |  Mostar  |
|      71000      | Sarajevo |

**Napravili smo još jednu tabelu s atributom grad gdje je sada atribut poštanski broj postao primarni ključ**

**TABELA JESTE U 3NF**

<hr>

**Boyce-Codd-ova normalna forma - BCNF**

<hr>

**Relacija R** je u **BCNF** ukoliko su sve **determinante** ujedino i **kandidati za ključ**. Relacija R je u BCNF ukoliko kada postoji netrivijalna zavisnost X -> X (Y nije podskup X), tada je X nadključ relacije R.

**Determinanta** je atribut u relaciji R, prost ili složen, od koga neki drugi atribut u relacij u potpunosti funkcionalno zavisi.

npr. 

R(A, B, C,D) , **FZ**(Funkcionalna zavisnost)

FZ: A-> B, C, D   --> jeste BCNF jer iz A proizilaze ostali atributi

FZ: BC-> AD --> jeste BCNF jer imamo sve atribute koji se nalaze u relaciji

FZ: D->B --> nije BCNF jer imamo atribute D i B ali nemamo atribute A i C.  NORMALIZACIJOM: 

Kreiramo dvije relacije, R2(D,B) -> iz funkcionalne zavisnosti, a R1 - prepisujemo ono što je s lijeve strane relacije koja nam "smeta" (gledamo D), s lijeve strane je A i C (B je s desne -iz funkcionalne zavisnosti) i prepisujemo D, pa slijedi R1(A, C, D).  --> Sada jeste BCNF 

























