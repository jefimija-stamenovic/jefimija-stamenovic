# Uvod-u-nauku-o-podacima

Seminarski rad iz predmeta Uvod u nauku o podacima 

## Uvod
U seminarskom radu je izvršena analiza i obrada skupa podataka airbnb.csv čiji sadržaj čine podaci o smeštaju na platformi Airbnb. 
Cilj rada je da se predvidi cena smeštaja u Indiji. <br> 
Analiza i obrada, kao i predviđanje su rađeni u R programskom jeziku (fajl airbnb.rmd), dok za pregledanje rada pogledajte airbnb.html fajl. 

## Metodologija
### 1. Učitavanje podataka i biblioteka
   - **Biblioteke:** Korišćene su biblioteke: tidyverse, corrplot, leaps, randomForest, car i još mnogo drugih 
   - **Podaci:** Skup podataka je airbnb.csv koji možete preuzeti odavde, a možete i sa [linka na Kaggle sajtu](https://www.kaggle.com/datasets/ashishjangra27/airbnb-dataset)

### 2. Analiza i obrada nedostajućih vrednosti
   - **Utvrđivanje postojanja NA vrednosti :** Pregled i istraživanje u kojim kolonama se nalaze NA vrednosti 
   - **Obrada NA vrednosti:** U zavisnosti od njihovog broja, rađeno je brisanje/imputacija

### 3. Analiza i vizuelizacija postojećih prediktora
   - **Cilj vizelizacije**: Uočavanje trendova i neobičnih vrednosti za bitne prediktore kao što su kapacitet smeštaja, broj soba, kreveta i kupatila, da li je smeštaj studio ili ne
   - Utvrđivanje outlier-a i njihovo otklanjanje 

### 4. Feature engineering
   - Kreiranje novih prediktora sa ciljem provere da li donose poboljšanju predviđanja 

### 5. Pregled i analiza smeštaja koji se nalaze samo u Indiji
   - Kreiranje novih prediktora sa ciljem provere da li donose poboljšanju predviđanja 

### 6. Predikcije modela
   - **Linearna regresija**: korišćeni su različiti prediktori kako bi se našao podskup prediktora koji imaju najbolje mere na trening skupu, međutim, na testnom skupu su te performanse izuzetno male (oko 20% zavisno od izbora prediktora)
   - **Random Forest**: generisana su modeli sa različitim brojem stabala, kao i sa različitim brojem karakteristika koje se nasumično biraju pri svakom cepanju čvora. Ovaj model ima bolje znatno bolje mere (oko 36%). 
   - **KNN**: kreiran je sa samo tri prediktora (guests + beds  + region) zbog prokletstva dimenzionalnosti. Kao takav, uspešno opisuje oko 31% podataka. 

## Rezultati
Analizom je utvrđeno da najbolje performanse predviđanja ima model RF sa 36% na testnom skupu, a za njim ide KNN sa 31%. Dakle, bolje mere performansi daju neparametarske metode (RF i KNN) od parametarskih (LR).  

## Zaključak
Nažalost, skup nije pogodan za predikcije što je i doprinelo lošim predikcijama modela na testnom skupu. Potrebno je dalje istraživanje kako bi se modeli unapredili, ali treba izvršiti i dodatne analize na skupu podataka kako bi se otkrilo šta je razlog ovako loših mera. 