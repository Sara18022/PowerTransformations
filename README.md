# Normalizacija podataka stepenim transformacijama: Box-Cox  i Yeo-Johnson 

### Sara Živković 1071/2023

U ovom projektu istražujemo tehnike normalizacije podataka (zavisnih promenljivih[^2]) kroz primenu stepenih transformacija, sa fokusom na Box-Cox i Yeo-Johnson metode. 

Normalizacija podataka je ključna za pripremu podataka za analizu i modelovanje, jer omogućava da se podaci prilagode pretpostavkama koje su neophodne za mnoge statističke metode i algoritme mašinskog učenja. Ovaj proces je naročito važan danas, kada tačnost i efikasnost analiza, baziranih na modelima masinskog ucenja, igraju ključnu ulogu u donošenju odluka.

Poseban naglasak stavljamo na primere primene Box-Cox i Yeo-Johnson transformacija. Pružićemo konkretne primere kako se ove transformacije primenjuju na različite skupove podataka i uporediti njihove efekte na distribuciju podataka. Diskutovaćemo prednosti i ograničenja svakog pristupa, kao i situacije u kojima su određene transformacije posebno korisne.

Pre nego što pređemo na proučavanje normalizacije podataka, važno je da se upoznamo sa osnovnim pojmovima vezanim za normalnu raspodelu. [Link](00_normal_distribution.ipynb) do Jupyter sveske.

## Zašto je transformacija podataka neophodna?
Transformacije podataka predstavljaju ključne korake u pripremi podataka za analizu i modeliranje. One omogućavaju prilagođavanje podataka tako da bolje odgovaraju zahtevima modela, poboljšavajući time njihovu tačnost i pouzdanost. Ove transformacije ne samo da osiguravaju da podaci ispunjavaju potrebne pretpostavke, već i olakšavaju interpretaciju rezultata, smanjujući uticaj ekstremnih vrednosti. Kroz pažljivo oblikovanje podataka, transformacije omogućavaju izgradnju modela koji donose bolje odluke i pouzdanije uvide.


## Stepene transformacije i normalizacija podataka
Stepene transformacije su porodica funkcija koja se koristi za monotone transformacije podataka primenom stepenih funkcija - korenovanja, logaritam, inverzna funkcija... Transformacije, kao što su Box-Cox i Yeo-Johnson transformacije, su ključne tehnike u procesu normalizacije podataka, posebno kada se radi sa podacima koji su asimetrični (raspodela vrednosti nije simetrična), jer pomažu u stabilizaciji varijanse[^1], približavajući podatke normalnoj raspodeli - proces normalizacije podataka. Za statističke analize i modele mašinskog učenja, podaci koji su približno normalno raspodeljeni sa homogenom varijansom često daju pouzdanije rezultate i poboljšavaju performanse modela. Zašto?  

Pa, mašine uče iz obrazaca, a ekstremne vrednosti mogu poremetiti njihovo rasuđivanje. Mi želimo da model "vidi" celokupnu sliku, a ne samo njen deo. Zbog toga je potrebno prilagoditi podatke i pravilno ih predstaviti modelu za učenje.

[^1]: Varijansa je statistička mera koja opisuje koliko su vrednosti u jednom skupu podataka rasprostranjene oko srednje vrednosti (aritmetičke sredine) tog skupa, odnosno pokazuje koliko su pojedinačne vrednosti u proseku udaljene od srednje vrednosti.

[^2]: Ciljna promenljiva ili zavisna promenljiva je promenljiva koju pokušavamo da predvidimo ili objasnite u analizi podataka ili modelu mašinskog učenja. Ciljna promenljiva je ključna za obuku modela jer se model trenira tako da minimizuje grešku u predviđanju ove promenljive. 

**Kako da znamo da naš uzorak nema normalnu raspodelu?** U [primeru](01_normality_test.ipynb) se nalazi detaljniji opis ovog problema.

Kako je naš fokus upoznavanje sa Box-Cox i Yeo-Johnson  transformacijama, u nastavku ćemo se baviti njima, a u [primeru](04_data_transformations.ipynb) možemo videti kako se gorepomenute stepene transformacije porede.

## Box-Cox transformacija
Transformacija se definiše kao:

$$
y'(\lambda) = 
\begin{cases} 
\frac{y^\lambda - 1}{\lambda} & \text{ako } \lambda \neq 0, \\
\ln(y) & \text{ako } \lambda = 0.
\end{cases}
$$

Primena transformacije i dodatna svojstva: [link](02_box-cox.ipynb).

## Yeo-Johnson
 TO BE DONE

# Literatura
- Osborne, Jason (2010). Improving your data transformations: Applying the Box-Cox transformation. Practical
Assessment, Research & Evaluation, 15(12)
- Osborne, J. W. (2002). Notes on the use of data transformations. Practical Assessment, Research, and Evaluation, 8
- https://medium.com/@vineet.pandya/test-of-normality-box-cox-transformation-in-details-c4bdfc2c352a
- J. Rico (2021) Normality Tests, p-values, and data normalization with Python.
[Source code](https://github.com/jvirico/normality-tests-pvalues-boxcoxtransformations)
-  Li, Fengfei (April 11, 2005), Box–Cox Transformations: An Overview (PDF) (slide presentation), Sao Paulo, Brazil: University of Sao Paulo, Brazil, retrieved 2014-11-02
- https://github.com/JoaquinAmatRodrigo/Estadistica-machine-learning-python/tree/master/data