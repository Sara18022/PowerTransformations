# Normalizacija podataka stepenim transformacijama: Box-Cox i Yeo-Johnson 

### Sara Živković 1071/2023

U ovom projektu istražujemo tehnike normalizacije podataka (zavisnih promenljivih[^2]) kroz primenu stepenih transformacija, sa fokusom na **Box-Cox i Yeo-Johnson metode**. 

Pre nego što pređemo na proučavanje normalizacije podataka, važno je da se upoznamo sa osnovnim pojmovima vezanim za normalnu raspodelu. [Link](00_normal_distribution.ipynb) do Jupyter sveske.

Normalizacija podataka je ključna za pripremu podataka za analizu i modelovanje, jer omogućava da se podaci prilagode pretpostavkama koje su neophodne za mnoge statističke metode i algoritme mašinskog učenja. Ona omogućava prilagođavanje podataka kako bi oni bolje odgovarali zahtevima modela, poboljšavajući time njihovu tačnost i pouzdanost.

Ovaj proces je naročito važan danas, kada tačnost i efikasnost analiza, baziranih na modelima masinskog ucenja, igraju ključnu ulogu u donošenju odluka.

Pokazaćemo kako se ove transformacije primenjuju na različite skupove podataka i uporediti njihove efekte na raspodelu podataka. Diskutovaćemo prednosti i ograničenja svakog pristupa, kao i situacije u kojima su ove transformacije posebno korisne.

## Stepene transformacije i normalizacija podataka
Stepene transformacije su porodica funkcija koje se koriste za monotone transformacije podataka primenom stepenih funkcija - korenovanje, logaritmovanje, inverzna funkcija... Transformacije, kao što su Box-Cox i Yeo-Johnson, su ključne tehnike u procesu normalizacije podataka, posebno kada se radi sa podacima koji su asimetrični (raspodela vrednosti nije simetrična), jer pomažu u stabilizaciji varijanse[^1], približavajući podatke normalnoj raspodeli - **proces normalizacije podataka**. Za statističke analize i modele mašinskog učenja podaci koji su približno normalno raspodeljeni često daju pouzdanije rezultate i poboljšavaju performanse modela. 

Mašine uče iz obrazaca, a ekstremne vrednosti mogu poremetiti njihovo rasuđivanje. Mi želimo da model "vidi" celokupnu sliku, a ne samo njen deo. Zbog toga je potrebno prilagoditi podatke i pravilno ih predstaviti modelu za učenje.

[^1]: Varijansa je statistička mera koja opisuje koliko su vrednosti u jednom skupu podataka rasprostranjene oko srednje vrednosti (aritmetičke sredine) tog skupa, odnosno pokazuje koliko su pojedinačne vrednosti u proseku udaljene od srednje vrednosti.

[^2]: Ciljna promenljiva ili zavisna promenljiva je promenljiva koju pokušavamo da predvidimo u analizi podataka ili modelu mašinskog učenja. Ciljna promenljiva je ključna za obuku modela jer se model trenira tako da minimizuje grešku u predviđanju ove promenljive.

**Kako da znamo da naš uzorak nema normalnu raspodelu?** U [primeru](01_normality_test.ipynb) se nalazi detaljniji opis ovog problema.

Kako je naš fokus upoznavanje sa Box-Cox i Yeo-Johnson transformacijama, u nastavku ćemo se baviti njima, a u [primeru](04_data_transformations.ipynb) možemo videti kako se gorepomenute stepene transformacije porede međusobno.

## Box-Cox transformacija
Transformacija se definiše kao:

$$
y(\lambda, x) = 
\begin{cases} 
\frac{x^\lambda - 1}{\lambda} & \text{ako } \lambda \neq 0, \\
\ln(x) & \text{ako } \lambda = 0.
\end{cases}
$$

Primena transformacije i dodatna svojstva: [link](02_box-cox.ipynb).

## Yeo-Johnson transformacija
Transformacija se definiše kao:

$$
y(\lambda, x) = 
\begin{cases} 
\frac{(x + 1)^\lambda - 1}{\lambda} & \text{ako } \lambda \neq 0 \text{ i } x \geq 0, \\
\frac{-(-x + 1)^{2 - \lambda} + 1}{2 - \lambda} & \text{ako } \lambda \neq 2 \text{ i } x < 0, \\
\ln(x + 1) & \text{ako } \lambda = 0 \text{ i } x \geq 0, \\
-\ln(-x + 1) & \text{ako } \lambda = 2 \text{ i } x < 0.
\end{cases}
$$

Za razliku od Box-Cox transformacije, Yeo-Johnson može da obrađuje i pozitivne i negativne vrednosti, što je čini univerzalnom za različite skupove podataka. 

Primena transformacije i dodatna svojstva: [link](02_yeo-johnson.ipynb).

_______________________________________________________________________________________________________________

Na kraju, na malom [primeru](05_big_example.ipynb) konstrukcije linearno regresionog modela nad transformisanim i originalnim podacima videćemo pravu moć ovih transformacija u poboljšanju rada modela mašinskog učenja.

## Korišćeni skupovi podataka
Korišćene skupove možete naći u folderu: [data/](data/)

U svakoj Jupyter svesci nalazi se opis korišćenog skupa podataka kao i analiza bitnih svojstava samog skupa.

## Literatura
- I.K. Yeo and R.A. Johnson, “A new family of power transformations to improve normality or symmetry.” Biometrika, 87(4), pp.954-959, (2000).
- G.E.P. Box and D.R. Cox, “An Analysis of Transformations”, Journal of the Royal Statistical Society B, 26, 211-252 (1964).
- Osborne, Jason (2010). Improving your data transformations: Applying the Box-Cox transformation. Practical
Assessment, Research & Evaluation, 15(12)
- Osborne, J. W. (2002). Notes on the use of data transformations. Practical Assessment, Research, and Evaluation, 8
- https://medium.com/@vineet.pandya/test-of-normality-box-cox-transformation-in-details-c4bdfc2c352a
- J. Rico (2021) Normality Tests, p-values, and data normalization with Python.
[Source code](https://github.com/jvirico/normality-tests-pvalues-boxcoxtransformations)
-  Li, Fengfei (April 11, 2005), Box–Cox Transformations: An Overview (PDF) (slide presentation), Sao Paulo, Brazil: University of Sao Paulo, Brazil, retrieved 2014-11-02
- https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PowerTransformer.html
- https://github.com/JoaquinAmatRodrigo/Estadistica-machine-learning-python/tree/master/data
- https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.yeojohnson.html
- https://www.kaggle.com/datasets/prathamtripathi/regression-with-neural-networking?resource=download