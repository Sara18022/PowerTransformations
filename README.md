# Normalizacija podataka stepenim transformacijama: Box-Cox  i Yeo-Johnson 

### Sara Živković 1071/2023

U ovom projektu istražujemo tehnike normalizacije podataka kroz primenu stepenih transformacija, sa fokusom na Box-Cox i Yeo-Johnson metode. 

Normalizacija podataka je ključna za pripremu podataka za analizu i modelovanje, jer omogućava da se podaci prilagode pretpostavkama koje su neophodne za mnoge statističke metode i algoritme mašinskog učenja. Ovaj proces je naročito važan danas, kada tačnost i efikasnost analiza, baziranih na modelima masinskog ucenja, igraju ključnu ulogu u donošenju odluka.

Poseban naglasak stavljamo na primere primene Box-Cox i Yeo-Johnson transformacija. Pružićemo konkretne primere kako se ove transformacije primenjuju na različite skupove podataka i uporediti njihove efekte na distribuciju podataka. Diskutovaćemo prednosti i ograničenja svakog pristupa, kao i situacije u kojima su određene transformacije posebno korisne.

## Zašto je transformacija podataka neophodna?
Transformacije podataka predstavljaju ključne korake u pripremi podataka za analizu i modeliranje. One omogućavaju prilagođavanje podataka tako da bolje odgovaraju zahtevima modela, poboljšavajući time njihovu tačnost i pouzdanost. Ove transformacije ne samo da osiguravaju da podaci ispunjavaju potrebne pretpostavke, već i olakšavaju interpretaciju rezultata, smanjujući uticaj ekstremnih vrednosti. Kroz pažljivo oblikovanje podataka, transformacije omogućavaju izgradnju modela koji donose bolje odluke i pouzdanije uvide.


## Stepene transformacije i normalizacija podataka
Posebno mesto među transformacijama zauzimaju stepene transformacije (familija stepenih funkcija koje primenjujemo na uzorkovane podatke), kao što su Box-Cox i Yeo-Johnson. Ove transformacije su posebno važne kada se radi sa podacima koji su asimetrični (raspodela vrednosti nije simetrična), jer pomažu u stabilizaciji varijanse[^1], približavajući podatke normalnoj raspodeli. Pravilna primena ovih transformacija može značajno poboljšati performanse modela i omogućiti preciznije analize. Zašto?  

Pa, mašine uče iz obrazaca, a ekstremne vrednosti mogu poremetiti njihovo rasuđivanje. Želimo da model "vidi" celokupnu sliku, a ne samo njen deo. Zbog toga je potrebno prilagoditi podatke i pravilno ih predstaviti modelu za učenje.


Za statističke analize i modele mašinskog učenja, podaci koji su približno normalno raspodeljeni sa homogenom varijansom često daju pouzdanije rezultate. Normalna raspodela omogućava da se preciznije predvide budući ishodi, dok stabilizovana varijansa osigurava konzistentnost modela. Kada podaci odstupaju od normalne raspodele ili imaju različitu varijansu kroz opseg, može doći do problema kao što su nepravilna predviđanja, povećan rizik od grešaka u zaključivanju i smanjenje pouzdanosti modela. 

Normalization is the process of scaling in respect to the entire data range so that the data has a range from 0 to 1.

[^1]: Varijansa je statistička mera koja opisuje koliko su vrednosti u jednom skupu podataka rasprostranjene oko srednje vrednosti (aritmetičke sredine) tog skupa, odnosno pokazuje koliko su pojedinačne vrednosti u proseku udaljene od srednje vrednosti.

**Kako da znamo da naš uzorak nema normalnu raspodelu?** U [primeru](01_box-cox_exponential_beta.ipynb) se nalazi detaljniji opis ovog problema.


Kako je naš fokus upoznavanje sa Box-Cox i Yeo-Johnson  transformacijama, u nastavku ćemo se baviti njima, a u [folderu](./02_data_transformations/) možemo videti kako se gorepomenute stepene transformacije porede sa njima.

## Box-Cox transformacija
When λ=0, the transformation simplifies to the natural logarithm of y. The choice of λ is crucial, and it is typically determined through optimization techniques to maximize the goodness of fit or log-likelihood.

The Box-Cox transformation is a generalization that includes square root, logarithmic, and reciprocal transformations as special cases.

## Yeo-Johnson


# Literatura
- Osborne, Jason (2010). Improving your data transformations: Applying the Box-Cox transformation. Practical
Assessment, Research & Evaluation, 15(12)
- Osborne, J. W. (2002). Notes on the use of data transformations. Practical Assessment, Research, and Evaluation, 8
- https://medium.com/@vineet.pandya/test-of-normality-box-cox-transformation-in-details-c4bdfc2c352a