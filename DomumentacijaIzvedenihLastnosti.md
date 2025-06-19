# Dokumentacija izvedenih lastnosti

Ta dokument zajema podrobnosti o implementaciji posameznih funkcionalnosti (taskov), kot so bile opisane in vodene v sistemu JIRA, skupaj z načinom uporabe za končne uporabnike.

---

## ROCK-44 - Vključevanje orodij za strganje in pripravo zgradbe programa
**Namen**: 
* Pripraviti orodja za strgalnike

**Način implementacije**:
* Dodajanje odvisnosti v Gradle
* Naloženi ChromeDriverji, za odpiranje brskalnika v ozadju
* Pridobivanje html strani s pomočjo Selenium Web Driver
* Priprava JSoup za strganje iz tega html

**Način uporabe**:
* Posredno uporablja preko strgalnikov

---

## ROCK-45 - Strganje podatkov o športnih plezališčih iz plezanje.net (ROCK-46 enako le da drug link zgradba strani enaka (pac balvani namesto športnih poti))
**Namen**: 
* Pridobiti podatke o plezališčih in poteh v njih s plezanje.net

**Način implementacije**:
* Priprava razredov za plezališča in poti
* Strganje linkov do strani plezališč iz html-ja s pomočjo JSOUP
* Strganje še vseh strani in pridobitev podatkov o plezališču in poteh v njem
* Shranjevanje teh podatkov v prej omenjene razrede

**Način uporabe**: 
* Uporabnik posredno uporabi preko vmsenika.

---

## ROCK-47 - Strganje notranjih sten iz ksp.pzs.si/plezalisca
**Namen**: 
* Pridobiti podatke o notranjih plezalnih centrih iz ksp.pzs.si/plezalisca

**Način implementacije**:
* Priprava razredoa za plezalne centre
* Strganje plezalnih centrov s html-js s pomočjo JSOUP
* Shranjevanje teh podatkov v prej omenjene razrede

**Način uporabe**: 
* Uporabnik posredno uporabi preko vmsenika.

---

## ROCK-88 - Funkcije za spreminjanje stanja aplikacija, za administratorsko panelo.
**Namen**: 
* Pridobivanje in posodablanje podatkov iz spletne aplikacije.

**Način implementacije**:
* Priprava OkHttp odvisnosti
* Priprava db paketa:
    * config datoteka, ki vsebuje poti do api in različnih delov api
    * configEnv, vsebuje administratorkse avtentikacijske podatke
    * DbUtil pripravi OkHttpClient in pridobi podatke iz config datotek
* Priprava dao pakta
    * priprava vmesnikov za centre in plezališča
    * vsebujejo getAll, insert, update ,delete
    * paket api
        * Implementacija funkcij iz vmesnikov s pomočjo http zahtev

**Način uporabe**: 
* Uporabnik posredno uporabi preko vmsenika.

---

## ROCK-95 - Osnovna zgradba vmesnika (Meni, razdelitev na zunanje plezališča in notranje centre)
**Namen**: 
* Priprava osnovne zgradbe grafičnega uporabniškega vmesnika

**Način implementacije**:
* Priprava okna
* Priprava gumbov, ki razdelita aplikacijo na plezališča in centre
* Priprava gumbov, ki v vsakem od teh delov razdelijo aplikacijo na 4 dele (stanje baze, ročno dodajanje, dodajanje s strgalnikom, avtomatsko generiranje)
* Priprava stanj, ki jih gumbi spremenijajo
* Prikaz plravilnih stanj

**Način uporabe**: 
* Uporabnik se bo lahko navigiral med različnimi deli aplikacije


---

## ROCK-96 - Dodajanje in prikaz notranjih centrov (ROCK-99 isto le za plezališča)
**Namen**: 
* Dodajanje in prikaz notranjih centrov

**Način implementacije**:
* Prikaz podatkov pridobljenih z kljicem funkcije, ki podatk dobi iz baze
* Vsak center predstavlja gumb, ki nam omogoča da center potrem spreminjamo
* Uporabniku ponudimo tekstovne vnose in gumba prekliči in shrani.
* Stran za dodajanje podatkov s pomočjo tekstovnih vnosov in gumbov za izbire
* Klic funkcije za dodajanje v bazo

**Način uporabe**: 
* Uporabnik lahko vidi centre, ki so v bazi in lahko ročno dodaja nove.

---

## ROCK-97 - Dodajanje in prikaz notranjih centrov (ROCK-100 isto le da za plzališča)
**Namen**: 
* Dodajanje notranjih centrov preko strgalnika

**Način implementacije**:
* Prikaz osnovne strani le da zdaj ne kljičemo funkcije za poatke iz baze
* Kljičemo funkcijo, ki dobi podatke s strganjem

**Način uporabe**: 
* Uporabnik lahko doda centre preko strgalnika.

---

## ROCK-98 - Generiranje noranjih centrov
**Namen**: 
* Možnost generiranje naključnih notranjih centrov za testiranje spletne aplikacije

**Način implementacije**:
* Imamo sezname besed s katerimi se centri začnejo (Plezalni center, PC, OŠ ...)
* Potem imamo sezname mest
* In pa naključne podatke lastnosti
* Uporabnik je napisal koliko generiranih centrov ima in mu zdaj damo 
naključne centre, ki so iz vsakega od teh seznamov izbrali neke lastnosti
* Te centre nato ddamo v bazo

**Način uporabe**: 
* Uporabnik lahko doda nove naključno generirane centre.

---

## ROCK-205 - Povezava gumbov s funkcijami za ažuriranje podatkoven baze
**Namen**: 
* Spremenili smo način povezave z bazo, zato je potrbno narediti manjše spremembe

**Način implementacije**:
* Manjše spremembe gleda katere funkcije kljičemo

**Način uporabe:** 
* Nima vidnega vpliva

---

## ROCK-223 - Sprememba ikone in imena aplikacije
**Namen**: 
* Aplikacija izgleda lepše če ima lepo ikono in ime ni undefined

**Način implementacije**:
* Zamenjal sem ime na AdminPannel
* Nastavil sem ikon na sliko, ki predstavlja administratorja

**Način uporabe:** 
* Lepši in bolj profesionalen izgled aplikacije.