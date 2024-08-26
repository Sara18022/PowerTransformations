# Normalizacija podataka stepenim transformacijama: Box-Cox  i Yeo-Johnson 

### Sara Živković 1071/2023

U ovom projektu istražujemo tehnike normalizacije podataka kroz primenu stepenih transformacija, sa fokusom na Box-Cox i Yeo-Johnson metode. 

Normalizacija podataka je ključna za pripremu podataka za analizu i modelovanje, jer omogućava da se podaci prilagode pretpostavkama koje su neophodne za mnoge statističke metode i algoritme mašinskog učenja. Ovaj proces je naročito važan danas, kada tačnost i efikasnost analiza, baziranih na modelima masinskog ucenja, igraju ključnu ulogu u donošenju odluka.

Poseban naglasak stavljamo na primere primene Box-Cox i Yeo-Johnson transformacija. Pružićemo konkretne primere kako se ove transformacije primenjuju na različite skupove podataka i uporediti njihove efekte na distribuciju podataka. Diskutovaćemo prednosti i ograničenja svakog pristupa, kao i situacije u kojima su određene transformacije posebno korisne.

## Zašto je transformacija podataka neophodna?
Transformacije podataka predstavljaju ključne korake u pripremi podataka za analizu i modeliranje. One omogućavaju prilagođavanje podataka tako da bolje odgovaraju zahtevima modela, poboljšavajući time njihovu tačnost i pouzdanost. Ove transformacije ne samo da osiguravaju da podaci ispunjavaju potrebne pretpostavke, već i olakšavaju interpretaciju rezultata, smanjujući uticaj ekstremnih vrednosti. Kroz pažljivo oblikovanje podataka, transformacije omogućavaju izgradnju modela koji donose bolje odluke i pouzdanije uvide.


## Stepene transformacije i normalizacija podataka
Stepene transformacije su porodica funkcija koja se koristi za monotone transformacije podataka primenom stepenih funkcija - korenovanja, logaritam, inverzna funkcija... Transformacije, kao što su Box-Cox i Yeo-Johnson transformacije, su ključne tehnike u procesu normalizacije podataka, posebno kada se radi sa podacima koji su asimetrični (raspodela vrednosti nije simetrična), jer pomažu u stabilizaciji varijanse[^1], približavajući podatke normalnoj raspodeli - proces normalizacije podataka. Za statističke analize i modele mašinskog učenja, podaci koji su približno normalno raspodeljeni sa homogenom varijansom često daju pouzdanije rezultate i poboljšavaju performanse modela. Zašto?  

Pa, mašine uče iz obrazaca, a ekstremne vrednosti mogu poremetiti njihovo rasuđivanje. Mi želimo da model "vidi" celokupnu sliku, a ne samo njen deo. Zbog toga je potrebno prilagoditi podatke i pravilno ih predstaviti modelu za učenje.

[^1]: Varijansa je statistička mera koja opisuje koliko su vrednosti u jednom skupu podataka rasprostranjene oko srednje vrednosti (aritmetičke sredine) tog skupa, odnosno pokazuje koliko su pojedinačne vrednosti u proseku udaljene od srednje vrednosti.

**Kako da znamo da naš uzorak nema normalnu raspodelu?** U [primeru](01_normality_test.ipynb) se nalazi detaljniji opis ovog problema.

Kako je naš fokus upoznavanje sa Box-Cox i Yeo-Johnson  transformacijama, u nastavku ćemo se baviti njima, a u [primeru](04_data_transformations.ipynb) možemo videti kako se gorepomenute stepene transformacije porede sa njima.

## Box-Cox transformacija
When λ=0, the transformation simplifies to the natural logarithm of y. The choice of λ is crucial, and it is typically determined through optimization techniques to maximize the goodness of fit or log-likelihood.

The Box-Cox transformation is a generalization that includes square root, logarithmic, and reciprocal transformations as special cases.

Box-Cox transformacija je stepenasta transformacija koja koristi parametar lambda (λ) da prilagodi raspodelu podataka. Različite vrednosti lambda omogućavaju različite transformacije, što može pomoći u normalizaciji podataka. Evo nekoliko ključnih vrednosti lambda i njihovih efekata:

    λ = 1: Kada je lambda jednaka 1, transformacija se ne primenjuje i podaci ostaju nepromenjeni. Ova vrednost funkcioniše kao identitetna transformacija i koristi se kada podaci već zadovoljavaju pretpostavke normalne raspodele.

    λ = 0: Kada je lambda jednaka 0, koristi se logaritamska transformacija (log(x)). Ovo je korisno za smanjenje asimetrije kod podataka sa desno-skewed distribucijom i može pomoći u stabilizaciji varijanse.

    λ = 0.5: Ova vrednost odgovara kvadratnom korenu (sqrt(x)). Korenski transformacije često se koriste kada podaci pokazuju blagu skevnost, jer mogu pomoći u postizanju normalnijeg oblika raspodele.

    λ = -1: Inverzna transformacija (1/x) koristi se kada podaci imaju jako desno-skewed distribuciju. Ovo može biti korisno za drastično ispravljanje jakih asimetrija u podacima.

    λ = -0.5: Koristi se kvadratni koren recipročne vrednosti (1/sqrt(x)). Ova transformacija može biti korisna za modifikaciju podataka koji su izraženi u velikom opsegu vrednosti i imaju naglu asimetriju.

Izbor odgovarajuće vrednosti lambda zavisi od prirode podataka i ciljeva analize. Eksperimentisanjem sa različitim vrednostima lambda možemo postići bolje usklađivanje podataka sa pretpostavkama statističkih modela, što poboljšava tačnost i pouzdanost analiza.

## Yeo-Johnson


# Literatura
- Osborne, Jason (2010). Improving your data transformations: Applying the Box-Cox transformation. Practical
Assessment, Research & Evaluation, 15(12)
- Osborne, J. W. (2002). Notes on the use of data transformations. Practical Assessment, Research, and Evaluation, 8
- https://medium.com/@vineet.pandya/test-of-normality-box-cox-transformation-in-details-c4bdfc2c352a
- J. Rico (2021) Normality Tests, p-values, and data normalization with Python.
[Source code](https://github.com/jvirico/normality-tests-pvalues-boxcoxtransformations)
-  Li, Fengfei (April 11, 2005), Box–Cox Transformations: An Overview (PDF) (slide presentation), Sao Paulo, Brazil: University of Sao Paulo, Brazil, retrieved 2014-11-02