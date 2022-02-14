# *Prevođenje veze kardinaliteta*

**(1,1): (1,1)** ~ sve postaje jedna tabela, PK mi biramo **jedna tabela, jedan PK po izboru**

**(0,1): (1,1)** ~ samo tabele (za entitete), **prostiranje** ključa **iz (0,1)** u (1,1) **dvije tabele, prostiranje**

**(0,1): (0,1)** ~ poveznik postaje nova tabela, **PK** mi **biramo**, sta je relevantnije **tri tabele, jedan PK-izborno**

**(0,1): (1, N)** ~ poveznik postaje nova tabela, **PK** se uzima sa strane gdje je kardinalitatet **max 1** **tri tabele, PK iz 1**

**(1,1):(0,M) i (1,1):(1,M)** ~  poveznik ne postaje nova tabela, **PK** iz max **N** se prostire **u** tabelu gdje je max **1**,  **dvije tabele, prostiranje **

**(0,1):(0,M) i (0,1):(1,M)** ~ poveznik postaje nova tabela, PK je kompoznitni ključ **tri tabele, kompozitni PK**

**(0,M):(0,M), (1,M):(0,M) i (1,M):(1,M)** ~ poveznik postaje nova tabela, PK je kompozitni ključ **tri tabele, kompozitni PK**



<hr>

## *<u>**2.1. Veze kardinaliteta 1:1**</u>*

Veze kardinaliteta 1:1 po pravilu nemaju obilježja. Sva obilježja ksoja bi eventualno mogla  biti pripisana samoj vezi, zapravo su obilježja jednog od objekata koji učestvuju u toj vezi. Dakle, mogu biti pripisana tom objektu i time postati obilježja šeme relacije kojom  se taj tip objekta predstavlja. 

***2.1.1. Veza kardinaliteta (1,1):(1,1)*** i oba objekta koji u njoj učestvuju prevodimo u  jednu šemu relacije, čija su obilježja sva obilježja jednog i drugog objekta.  Kandidat za ključ u ovoj šemi relacije su identifikatori jednog i drugog objekta koji  su u vezi.

***2.1.2. Veza kardinaliteta (0,1):(1,1)*** i objekte u vezi prevodimo u dvije šeme relacije.  Svakom entitetu u vezi odgovara po jedna šema relacije (prema već definiranom  pravilu 1.1), s tim što identifikator jednog od objekta koji su u vezi postaje  obilježje i druge šeme relacije u ulozi eksternog ključa. Dakle, veza se predstavlja **spoljnim (eksternim) ključem.** Spoljni ključ je identifikator entiteta sa čije  strane kardinalitet (1,1) u relacionoj šemi koja odgovara entitetu sa čije strane  kardinalitet je (0,1).

Šema relacije u koju se uvrstiti spoljni (eksterni) ključ bira se tako da relacija  sadrži što manje null vrijednosti i da njeno korištenje bude što efikasnije.

*Pravilo za prevođenje veze sa kardinalnošću (0,1):(1,1) je njeno  predstavljanje spoljnim ključem u šemi relacije objekta sa strane gdje je kardinalitet  (1,1).*

***2.1.3. Za vezu kardinaliteta (0,1):(0,1)*** kreiraju se tri šeme relacije. Po jedna za svaki  objekt entitet (prema već definiranom pravilu 1.1) i jedna za vezu. Obilježja u  šemi relacije koja odgovaraju vezi su identifikatori objekata (entiteta) koji su u  vezi i oba su kandidati za ključ.

## **<u>*2.2. Veze kardinaliteta 1:N ili N:1*</u>**

***2.2.1. Veze kardinaliteta (1,1):(0,M) i (1,1):(1,M)*** ne postaju posebne šeme relacija.  Identifikator objekta sa strane za koju je gornja granica kardinaliteta  preslikavanja M postaje obilježje šeme relacije koja odgovara objektu sa čije  strane je maksimalni kardinalitet 1.

***2.2.2. Veza između nadređenog i slabog objekta kao i veza između nadtipa i podtipa*** ne  postaju posebne šeme relacija. One su već ostvarene pravilima 1.2, 1.3 i 1.4. 2.2.3. 

***2.2.3 Veze kardinaliteta (0,1):(0,M) i (0,1):(1,M)*** postaju posebne šeme relacija.  Obilježja ove šeme relacije su identifikatori objekata koji su u vezi, a ključ šeme  relacije je identifikator objekta sa čije strane maksimalni kardinalitet je 1.

## ***<u>2.3. Veze kardinaliteta N:M</u>***

***2.3.1. Veze kardinaliteta (0,M):(0,M), (1,M):(0,M) i (1,M):(1,M)*** postaju posebne šeme  relacija. Obilježja ove šeme relacije su identifikatori objekata koji su u vezi, a  ključ šeme relacije je složeni ili kompozitni ključ koji se sastoji od identifikatora  objekata koji su u vezi.

<hr>

***<u>2.4. Gerund ili agregirani objekt (mješoviti tip objekt-veza)</u>*** se posmatra na isti način kao  i odgovarajuća veza. Ukoliko veza posjeduje obilježja ona postaju obilježja šeme  relacije veze kada se veza prevodi u posebnu šemu relacije ili se uključuju u onu  šemu relacije u koju se upisuje spoljni ključ.

***<u>2.5. Prevođenje rekurzivnih ili unarnih veza (unarnom se naziva veza između dva objekta  istog tipa)</u>*** u relacioni model podataka zavisi od kardinalnaliteta tipa poveznika i izvodi se  kao i za druge tipove ranije opisanih binarnih veza. Kod unarne veze tipa (1:1)  parcijalnost samo na jednoj strani veze, odnosno totalnost samo na jednoj strani veze,  ne bi imalo smisla. 

Naime, time bi se istom tipu objekta istovremeno dopuštalo i poricalo  opcionalno učešće u vezi. Pri prevođenju unarnih veza s obzirom da bi spoljni ključ u šemi relacije imao isti naziv  kao i primarni ključ, potrebno je njegovo preimenovanje.