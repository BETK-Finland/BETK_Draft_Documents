# BETK keskustelupaperi: Huomioita sijaintitiedosta betonielementtien toimitusketjussa


**Sijaintitieto suunnittelijan tietomallista toimitukseen**  
>Julkaisija: Rakennusteollisuus ry\
>Luonnos: 23.12.2025

<details>
<summary>Asiakirjan tiedot </summary>

| Selite                | Arvo                                                                |
|-----------------------|---------------------------------------------------------------------|
| Asiakirjan nimi       | BETK soveltamisohje: Sijaintieto betonielementtien toimitusketjussa |
| Asiakirjan päivämäärä | 23.12.2025                                                          |
| Asiakirjan versio     | 1.0                                                                 |
| Asiakirjan status     | Luonnos                                                             |

</details>

<details>
<summary>Asiakirjan laatijat </summary>

| Nimi             | Organisaatio                  |
|------------------|-------------------------------|
| Antti Pekkala    | Fira Oy                       |
| Teemu Anttila    | Ramboll                       |
| Janne Kihula     | Rakennustuoteteollisuus RTT   |
| Teemu Alaluusua  | Aalto-yliopisto               |
| Tom Partanen     | Consolis Parma Oy             |
| Eetu Lahtinen    | Consolis Parma Oy             |
| Satu Parikka     | Consolis Parma Oy             |
| Markku Räisänen  | Betset Oy                     |
| Jarkko Vitikainen| Sitowise Oy                   |
| Arto Nieminen    | NCC Oy                        |
| Riku Laiho       | NCC Oy                        |
| Antti Taskinen   | Fira Oy                       |
| Paula Valkonen   | Suutarinen / SBS Betoni Oy    |
| Kari Turunen     | Lujabetoni Oy                 |

</details>

<details>
<summary> Asiakirjan versio </summary>

| Versio  | Päivämäärä  | Tekijä  | Muutoskuvaus               |
|---------|-------------|---------|----------------------------|
| 0.1     | 21.5.2025   | anpekk  | Luonnos vaihe              |
| 0.2     | 30.5.2025   | anpekk  | Tekstiosuuksia täydennetty |
| 0.3     | 3.7.2025    | anpekk  | Tekstiosuuksia täydennetty |
| 0.4     | 9.11.2025   | TeAla   | Tekstiosuuksia täydennetty |
| 1.0     | 23.12.2025  | TeAla   | Github-julkaisu			   |

 </details>

 
## Sisällysluettelo


1. [Tausta](#1-tausta)<br>
2. [Keskustelupaperin tarkoitus ja rajaukset](#2Keskustelupaperin-tarkoitus-ja-rajaukset)<br>
3. [Sijaintieto tietomallissa](#3sijaintieto-tietomallissa)<br>
 3.1 [Koordinaatistot](#31koordinaatistot)<br>
  3.1.1 [Asiakkaan koordinaatisto](#311asiakkaan-koordinaatisto)<br>
  3.1.2 [Projektin koordinaatisto](#312projektin-koordinaatisto)<br>
  3.1.3 [Suunnittelijan koordinaatisto](#313suunnittelijan-koordinaatisto)<br>
 3.2 [Sijaintitiedot tietomallissa](#32sijaintitiedot-tietomallissa)<br> 
  3.2.1 [Kerrostiedot IFC-mallissa](#321kerrostiedot-ifc-mallissa)<br>
  3.2.2 [Lohkotiedot IFC-mallissa](#322lohkotiedot-ifc-mallissa)<br>
5. [Sijaintitietojen esittäminen tietomalleissa](#4sijaintitietojen-esittäminen-tietomalleissa)<br>
6. [Toimitusketjun näkökulma: BEAst Label -esimerkki Ruotsista](#5sijaintitiedot-toimituksissa-case-ruotsi)<br>
   [Lyhenteet ja terminologia](#lyhenteet-ja-terminologia)<br>
   [Viittaukset](#viittaukset)<br>

---
​ 
## 1 Tausta

Rakennushankkeiden tietomallit ovat vakiintuneet osaksi hankkeiden tarjouspyyntöjä, määrä- ja kustannuslaskentaa sekä toteutuksen suunnittelua. Suunnittelijoiden laatimia tietomalleja hyödyntävät rakennusliikkeet ja tuoteosatoimittajat laajasti hankinnan, tuotannon, logistiikan ja asennuksen suunnittelussa. Betonielementtirakentamisessa tietomallien merkitys korostuu erityisesti elementtien määrityksessä, jaottelussa ja ajoituksessa.

Alalla yleisesti käytössä olevat mallinnusohjeet ja vakioidut tietokentät, kuten BEC2012-hankkeessa luodut käytännöt, ovat parantaneet tietomallien yhteentoimivuutta. Tästä huolimatta betonielementtien sijaintitietoon liittyvät tiedot, erityisesti lohko- ja kerrostiedot, ovat edelleen epäyhtenäisiä, puutteellisia tai tulkinnanvaraisia. Suunnittelumalleista saatava sijaintitieto ei sellaisenaan vastaa toimitusketjun eri vaiheiden tarpeita, eikä tieto siirry luotettavasti suunnittelusta tilaus-, toimitus- ja asennusprosessiin.

Käytännössä tämä tarkoittaa, että asennuslohkojaot, aikataulut ja toimitusten kohdistaminen muodostuvat usein työmaakohtaisesti erillisissä järjestelmissä tai manuaalisina tulkintoina. Toimitusketjun osapuolten välillä on käytössä monenlaisia ratkaisuja, mutta yhteisiä digitaalisia ja vakioituja käytäntöjä sijaintitiedon välittämiseen ei ole muodostunut. Tämä lisää tiedon päällekkäistä käsittelyä, virheriskiä ja heikentää toimitusketjun kokonaisohjattavuutta.

Sijaintitiedon haaste ei rajoitu pelkästään tietomallien sisäiseen rakenteeseen, vaan se korostuu erityisesti tilanteissa, joissa tieto tulisi yhdistää fyysisiin tuotteisiin ja toimituksiin. Kun betonielementti siirtyy suunnittelusta tuotantoon, kuljetukseen ja asennukseen, sen sijainti muuttuu käsitteellisestä tilasijainnista fyysiseksi kohdistustiedoksi, jonka tulee olla ymmärrettävä sekä ihmiselle että tietojärjestelmille.

Tämän vuoksi sijaintitiedon tarkastelussa on huomioitava sekä fyysinen, ihmisluettava ulottuvuus että digitaalinen, koneluettava ulottuvuus. Tiedon tulee olla tulkittavissa työmaalla esimerkiksi kollietiketeissä ja asennusohjeissa, mutta samalla sen on oltava rakenteellisessa muodossa, jotta se voidaan siirtää sähköisesti järjestelmien välillä ilman manuaalista uudelleenkirjausta. Tässä kokonaisuudessa betonielementtien sijaintitieto tunnistetaan keskeiseksi kehityskohteeksi, joka yhdistää tietomallit, tuoteyksilöinnin, toimitukset ja asennusprosessit toisiinsa.

<img width="2602" height="1945" alt="Kerrosten nimeäminen" src="https://github.com/user-attachments/assets/6a8460de-d368-4afd-932e-bee9b8927ab5" /><br> Kuva 1. Esimerkki yhdistelmämallin kerrostiedoista


 ---

## 2	Keskustelupaperin tarkoitus ja rajaukset
Tämä dokumentti on BETK-työryhmän keskustelupaperi, jonka tarkoituksena on jäsentää betonielementtien toimitusketjun kannalta keskeisiä sijaintitietoon liittyviä havaintoja, ongelmia ja kehityssuuntia. Paperi ei ole normi, standardi tai valmis ohje, vaan lähtökohta yhteiselle ymmärrykselle ja jatkokehitykselle.

Keskustelupaperi kytkeytyy Rakennusteollisuus RT:n käynnissä olevaan tuotetiedon ja toimitusketjujen digitalisaatiotyöhön, jossa tavoitteena on siirtyä manuaalisesta ja rakenteettomasta tiedonvaihdosta kohti rakenteellista, koneluettavaa ja toimitusketjun eri osapuolia palvelevaa tiedonhallintaa. Tässä kokonaisuudessa sijaintitieto muodostaa kriittisen rajapinnan tietomallien, fyysisten tuotteiden tunnistamisen sekä toimitus- ja tapahtumatiedon välillä.

Koska rakennettavien kohteiden sijaintitiedolla on eri käyttäjäryhmille erilaisia merkityksiä, käyttötarkoituksia ja tarkkuusvaatimuksia, tässä dokumentissa keskitytään rajatusti betonielementtien toimitusketjun näkökulmaan. Tarkastelun painopiste on suunnittelumalleissa esiintyvissä kerros- ja lohkotiedoissa, niiden tulkittavuudessa sekä mahdollisuuksissa liittää nämä tiedot fyysisiin toimituksiin ja digitaalisiin sanomiin. Laajempi sijaintitiedon standardointi, esimerkiksi koordinaattipohjaisessa tai monialaisessa kontekstissa, tunnistetaan tärkeäksi jatkotyön aiheeksi, mutta se ei ole tämän keskustelupaperin varsinainen tavoite.

Esimerkiksi rakennesuunnittelijalle lohkoa usein rajaavat rakenteelliset liikuntasaumat ja samaan aikaan elementtiasentajalle tärkeä tieto on mm. betonielementin asennuslohko. LVI-suunnittelija usein jakaa rakennuksen TATE-järjestelmien mukaisiin palvelu-alueisiin ja esim. TATE-toimitusketjun kannalta yksittäisen tilan yksilöinti on tärkeä sijaintitieto. Tämän takia tämä kirjoitus on ns. keskustelupaperi, jossa ei pyritä ratkaisemaan sijaintitietoa täydellisesti vaan keskittyen betonielementtien toimituksen kannalta tärkeisiin tietoihin ja niissä havaittuihin ongelmiin ja myös ehdotuksia näiden ratkaisemiseksi pohjoismaisella tasolla.

---

## 3	Sijaintieto tietomallissa
### 3.1	Koordinaatistot
Rakennushankkeissa käytettävistä koordinaatistoista käydään keskustelua käytännössä jokaisessa hankkeessa. Koordinaatistojen määrittely on tarpeen, koska hankkeen eri osapuolilla ja eri käyttötapauksilla on toisistaan poikkeavia vaatimuksia sijaintitiedolle. Tietomallien näkökulmasta keskeistä on, että projektin koordinaatisto on sovittu ja dokumentoitu, usein arkkitehdin toimesta, jotta aineistoa voidaan siirtää ja yhdistää luotettavasti hankkeen aikana.

Rakennushankkeissa on tyypillisesti käytössä kolme toisiaan täydentävää koordinaatistotyyppiä: asiakkaan koordinaatisto, projektin koordinaatisto ja suunnittelijan koordinaatisto.

#### 3.1.1 Asiakkaan koordinaatisto

Asiakkaan koordinaatisto perustuu tyypillisesti kaupungin tai kunnan käyttämään koordinaatistojärjestelmään. Asiakkaan koordinaatisto palvelee asiakkaan tarpeita ja mahdollistaa esimerkiksi suunnitelmien liittämisen laajempaan virtuaaliseen malliin. Projektin aikana rakennusvalvonta tai muu viranomainen voi edellyttää asiakkaan koordinaatiston käyttämistä.


<img width="416" height="335" alt="Asiakkaan koordinaatisto" src="https://github.com/user-attachments/assets/57adfd92-120f-4033-b764-86a7b755fa25" /> <br> Kuva 2. Asiakkaan koordinaatisto

#### 3.1.2 Projektin koordinaatisto

Projektin koordinaatisto on hankkeen osapuolten kesken sovittu koordinaatisto, jossa aineistoa siirretään projektin aikana. Projektin koordinaatisto palvelee tiedonsiirtoa eri suunnittelualojen ja eri suunnitteluvaiheiden välillä. Sen avulla eri suunnitteluajojen mallit voidaan yhdistää toisiinsa esimerkiksi suunnitelmien ristiriidattomuuden tarkastelua varten.

 <img width="530" height="335" alt="Projektin koordinaatisto" src="https://github.com/user-attachments/assets/204114d4-ebea-410f-a53f-c6dc935941b8" /><br> Kuva 3.Projektin koordinaatisto
 
#### 3.1.3 Suunnittelijan koordinaatisto

Suunnittelijan koordinaatisto on suunnittelijan omassa suunnittelutyössä käyttämä koordinaatisto. Se palvelee ensisijaisesti suunnittelijan työn sujuvuutta. Käytännössä suunnittelijan voi olla tarpeen asettaa origo tiettyyn pisteeseen tai kääntää kohdetta, jotta mallinnus ja näkymien käsittely on tarkoituksenmukaista.

Mikäli suunnittelijan ohjelmistossa ei ole mahdollista toteuttaa näitä ratkaisuja esimerkiksi näkymien avulla, voi suunnittelija käyttää projektin koordinaatistosta poikkeavaa koordinaatistoa omassa työssään.


<img width="384" height="335" alt="Suunnittelijan koordinaatisto" src="https://github.com/user-attachments/assets/acc2c361-8c3e-411d-bea7-6158deb8d653" /><br> Kuva 4.Suunnittelijan koordinaatisto<br>

### 3.2	Sijaintitiedot tietomallissa
#### 3.2.1	Kerrostiedot IFC-mallissa
IFC-mallissa rakenneosat kuuluvat tiettyyn rakennukseen (IfcBuilding), lohkoon (osittainen IfcBuilding) ja kerrokseen (IfcBuildingStorey). Rakennuksen lohko ei ole IFC-formaatissa vastaava käsite kuin rakennus ja kerros. IFC-formaatti mahdollistaa hierarkisuuden siten että, rakennus voi koostua useasta rakennuksesta, jotka voivat sisältää osittaisia rakennuksia, jotka ovat on tarkoitettu raken-nuksen lohkojen määrittelyyn. Useat eri suunnittelualojen mallinnusohjelmat perustuvat siihen, että mallia tehdään rakennuksittain ja kerroksittain. Nämä sijaintitiedot ovat tärkeitä asennusta ja valmistusta suunniteltaessa ja toteutuksessa. Ja usein myös jo tarjouslaskentavaiheessa kustannusten jaot-telua varten on tietomallien lohkojako tarpeellinen. 
Kerrostiedossa on havaittu haasteeksi mm. kerrostiedon puuttuminen, väärin syötetty kerrostiedot ja monenlaiset kirjoitustavat ja -virheet. 

<img width="197" height="246" alt="Kuva5" src="https://github.com/user-attachments/assets/4b8df90e-22ef-445d-ba3f-3e6135d2d7e0" /><br> Kuva 6. Esimerkki kuinka välilyönnit lisäävät kerroksia hankkeen tietomalliin

Ohjeita tietojen lisäämiseen hankkeissa:
•	Rakennesuunnittelija lisää sovitun lohko- ja kerrosjaon tietomalliin. 
•	Lohko- ja kerrostiedot tarkistetaan ennen tietomallitoimituksia.
•	Kerrostieto kirjoitetaan ilman ”.krs” tai muita tiedonsiirtoa sotkevia selitetekstejä, vain nu-meroita. Kerrostieto on IFC-mallissa kerrostietonimisessä tietokentässä (IfcBuildingStorey) jo-ten arvo ei tarvitse selittävää tekstiä siitä, että tiedolla tarkoitetaan kerrosta.
•	Kerroksen muodostavat kantavat ja ei-kantavat seinät ja pilarit niiden yläpuolinen välipohja. Usean kerrosten läpi menevät rakenteet (esim. pilarit) alimpaan kerrokseen, jossa ne asenne-taan.
•	Rakennemallissa kerroksina myös ”POHJARAKENTEET, PERUSTUKSET, ALAPOHJA, KELLARI”. Eli paalut ja anturarakenteet, sokkelit ja alapohjan rakenteet. 
•	Kerrokset nimet aina isolla kirjaimella, jotta ei tule eri tavalla kirjoitettuna. Esim. Kellari vs KELLARI. 
•	Rakenteellinen pintalaatta nimetään saman kerrokseen kuin sen alapuoliset rakenteet. 
•	Yläpohjassa esim. ylimmän ontelolaattatason yläpuoliset vesikattorakenteet nimetään erik-seen omaksi kerrokseksi, esim. YLÄPOHJA. 
 
<img width="385" height="159" alt="Kuva6" src="https://github.com/user-attachments/assets/7d6217e4-ef5a-44cf-adb9-c6b1322c298c" /><br>Kuva 7. Esimerkki kerrosten nimeämisestä
	
#### 3.2.2	Lohkotiedot IFC-mallissa
Rakennuksen lohkojakoon vaikuttavat mm. palo-osastointi, toiminnot, runkojärjestelmä, tekniikka, maapinnan olosuhteen ja perustukset, työvaiheiden limitys, tontin koko ja muoto ja jne jne. Eli vai-kuttavia asioita on paljon ja lohkotietojen käyttötapaukset vaihtelevat hankkeen aikana. Alla muu-tamia esimerkkejä erityyppisistä rakennuksista.
Logistiikka-halli, joka jaettu lohkoihin A ja B ja niiden alla useampi asennuslohko A1, A2, B1 ja  B2 jne. 

<img width="642" height="289" alt="Kuva7" src="https://github.com/user-attachments/assets/01b3ef00-47f5-41a8-ac34-afaf78d2c2e6" /><br> Kuva 8. Logistiikka-halli lohkojako esimerkki


Asuinkerrostalo jossa liikuntasaumajaon kohdalta jaottelu lohkoihin A ja B ja niiden sisällä rappujen mukainen jaottelu. 

<img width="583" height="260" alt="Kuva8" src="https://github.com/user-attachments/assets/13bfacc9-db06-435f-9720-62275f2f1c8f" /><br> Kuva 9. Asuinkerrostalon lohkojako esimerkki

Pistetalo jossa ei ole tarpeen lohkojakoa tehdä. Rappu-tiedon lisäksi asennuslohkon muodostaa yksittäinen huoneisto ja sen sisältämät elementit.

<img width="421" height="381" alt="Kuva9" src="https://github.com/user-attachments/assets/c1822aeb-8444-499b-a0b8-5cc13a73ec1d" /><br> Kuva 10. Pistetalo esimerkki


Ohjeita tietojen lisäämiseen hankkeissa:
•	Rakennesuunnittelija lisää tietomalliin sovitun lohko- ja kerrosjaon. 
•	Lohko- ja kerrostiedot tarkistetaan ennen tietomallitoimituksia.

Lohkojakotieto oltava aina vaikka vain yksi rappu talossa?

Peppol
Asennuslohkotieto tietomallista
Asennuslohkotieto tietomalliin
Asennussijainnit Peppol

```yaml
Sijaintitiedot Peppol sanomissa:
<Rakennus>
<RAK-lohko>
<Kerros>
<Asennuslohko 1>
<Asennuslohko 2>
<Asennuslohko 3>
<Rappu>
<Tila>
<Tehtaan valupäivä>
<Toimituspäivä>
<Toimitusaika>
<Vaihtoehtoiset toimitusajat>

```
Koodi 1. 

---

## 4	Sijaintitietojen esittäminen tietomalleissa
Rakennettujen kohteiden tietomalleissa sijaintitieto muodostaa keskeisen osan tuotetiedon ja prosessitiedon yhteentoimivuutta. IFC-standardin (Industry Foundation Classes) rakenteessa sijainti ja tilallinen organisointi määritellään kahden toisiaan täydentävän periaatteen kautta: placement (sijoittaminen) ja spatial organization (tilallinen rakenne).<br>

**Placement** kuvaa kohteen paikan suhteessa koordinaattijärjestelmään, toiseen objektiin tai paikalliseen referenssiin. IFC:n määritelmissä tämä toteutetaan luokan IfcObjectPlacement kautta, joka voi olla absoluuttinen (maailmankoordinatisto), suhteellinen (toiseen tuotteeseen) tai rajoitettu (esimerkiksi verkkoon tai lineaariseen kohteeseen sidottu). Paikallinen sijoitus määritellään IfcLocalPlacement-luokalla, ja suuremmassa mittakaavassa georeferointi yhdistää mallin maantieteelliseen sijaintiin. Koordinaattiverkot (IfcGrid) mahdollistavat kohteiden sijoittamisen eri geometristen asetelmien mukaan, kuten suorakulmaisina, radiaalisina tai kolmiomaisina rakenteina.<br>

<img width="4163" height="1220" alt="2025-11-08_Kuva1" src="https://github.com/user-attachments/assets/887316e8-9821-4e62-9425-d89a754edb6c" /> Kuva x. Koordinaattiverkot (Domer & Bernadello, 2023)


**Spatial organization** puolestaan määrittää, miten rakennuksen tai muun rakenteen osat järjestyvät hierarkkisesti ja tilallisesti. Tämä voidaan esittää kahdella tavalla:<br>

Spatial containment – hierarkkinen tilarakenne ilman omaa geometriaa (esimerkiksi Site – Building – Storey – Space), jota kuvataan luokalla IfcSpatialStructureElement.<br>

Spatial composition – geometrisesti kuvattu tilallinen koostumus, kuten IfcSpatialZone, joka kokoaa yhteen samankaltaisia tiloja tai toiminnallisia alueita.<br>

<img width="4450" height="2223" alt="2025-11-07_Kuva1" src="https://github.com/user-attachments/assets/ce41cd97-a614-42a7-a3a7-2a58f3e410b6" /><br> Kuva x. Rakennuksen tilayksiköt (Domer & Bernadello, 2023)[^1]

Rakennuksen tilahierarkia seuraa tyypillisesti rakennuksen suunnittelun ja rakentamisen logiikkaa: IfcProject toimii ylimpänä kontekstina, jonka alla sijaitsevat IfcSite, IfcBuilding, IfcBuildingStorey ja IfcSpace. Näin muodostetaan yhtenäinen tietorakenne rakentamiskohteen informaatiomalliin (BIM), jonka avulla eri suunnittelualojen ja toimitusketjun toimijat voivat viitata samoihin tilallisiin ja paikallisiin konteksteihin mallissa (BIM).<br>

Lisäksi IFC tukee koostettuja elementtejä (assemblies), joiden avulla voidaan yhdistää useita rakennusosia (esim. palkki- ja runkorakenteita) yhdeksi loogiseksi kokonaisuudeksi IfcElementAssembly-luokan kautta. Sijainti- ja tilatietojen yhteys varmistetaan relaatioiden, kuten IfcRelContainedInSpatialStructure ja IfcRelAggregates, avulla, jolloin kohteiden keskinäiset suhteet säilyvät yksiselitteisinä tietomallissa.<br>

Sijaintitiedon standardoitu rakenne on keskeinen edellytys digitaalisten toimitusketjujen hallinnalle, koska se mahdollistaa sekä fyysisten tuotteiden että niihin liittyvien tapahtumien (esim. toimitukset, asennukset) liittämisen samaan kontekstiin. Yhtenäinen sijaintimäärittely tukee myös linkitetyn datan sovelluksia, joissa rakennustuotteiden yksilöivä tunniste voidaan yhdistää rakennuksen tilalliseen ja koordinaattipohjaiseen rakenteeseen.<br>



---

## Toimialan näkökulmia sijaintitietojen vakioinnista...

Rava3Pro-hankkeessa on ollut esillä vaatimuksia hankkeen tietomallien koordinaatti-tiedolle, mutta tätä ohjetta kirjotettaessa selkeitä vaatimuksia ei vielä ole tiedossa. BETK-hankkeessa on käyty keskustelua koordinaattitiedon mahdollisuuksista ja haasteista.  BETK-hankkeessa luotu ja soveltamisohjeessa **[1]** kuvattu tapa yksilöidä elementti käyttäen GS1 GTIN-standardia mahdollistaa elementin tunnistamisen käyttäen RFID-teknologiaa. RFID-lukutapahtumissa on mahdollista saada mm. lukutapahtumista sijaintitietoa ja tietoa on mahdollista välittää toimitusketjun välillä Peppol-sanomilla. Koordinaattitiedon välittäminen tarjoaa erilaisia mahdollisuuksia mutta edellyttää alalta laajempaa vakiointia. BETK-hankkeessa tietomallin tietokenttiin lisättiin betonielementin  painopisteen koordinaatit. Tämän toteuttaminen ei edellytä laajempaa vakiointia ja on esimerkkinä tulevaisuuden ratkaisuille ja käyttötapauksille. 

<img width="642" height="211" alt="Kuva4" src="https://github.com/user-attachments/assets/a6dacf51-5744-4673-9c8b-0c5f8f0d53d5" /><br>Kuva 5. Kuorielementin painopisteen koordinaatit

## 5 Toimitusketjun näkökulma: BEAst Label -esimerkki Ruotsista

Ruotsalaisen rakennusteollisuuden tarpeisiin kehitetty BEAst Label on rakennusalan toimitusketjujen tueksi laadittu kollietikettistandardi, jonka tarkoituksena on yhdenmukaistaa tavaroiden ja materiaalien merkintä ja tunnistettavuus toimitusprosessin eri vaiheissa. Standardin tekninen tehtävä on mahdollistaa rakennusmateriaalien yksiselitteinen tunnistus, paikannus ja ohjattu käsittely työmaalla sekä tukea sähköistä tiedonvaihtoa toimitusketjun osapuolten välillä. BEAst Label perustuu GS1-järjestelmään ja sen SSCC-tunnuksiin (Serial Shipping Container Code) sekä hyödyntää GS1-128-, DataMatrix- ja QR-viivakoodeja, joita käytetään muun muassa kolli-ID:n, GPS-koordinaattien ja yhteystietojen koneelliseen lukuun.<br>

Standardin ydinperiaate on, että fyysinen etiketti ja sähköinen tiedonvaihto muodostavat yhdenmukaisen tietorakenteen. Etikettien tiedot tuotetaan automaattisesti BEAst Supply Material -standardin mukaisesta sähköisestä tilausviestistä (EDI), jossa määritellään toimituksen kohdetiedot kuten rakennus, porrashuone, kerros, huone ja purkupaikka. Tämän rakenteen ansiosta toimittajat voivat tulostaa kollikohtaiset etiketit samansisältöisinä eri toimituksissa ilman manuaalista tietojen syöttöä.<br>

BEAst Labelista on neljä eri versiota, jotka on suunniteltu erilaisiin käyttötarkoituksiin. Label A soveltuu lavatavaralle ja sisältää suurikokoiset kohdekentät, jotka helpottavat etäluettavuutta esimerkiksi trukin käytön yhteydessä. Label B on tarkoitettu muille pakkauksille ja alikolleille, ja se sisältää tarkemmat tiedot kollin sisällöstä. Label C toimii lisäluettelona tilanteissa, joissa tarvitaan enemmän tietokenttiä kuin Label B tarjoaa. Label D on tuote- tai artikkelikohtainen etiketti, joka täydentää valmistajan omaa merkintää ja mukautetaan tuotekohtaisesti.<br>

Etiketti sisältää sekä tekstimuotoisia tietoja että viivakoodeja, joita voidaan esittää yksiulotteisina (1D) tai kaksiulotteisina (2D) koodeina, kuten DataMatrix tai QR. Näin voidaan välittää suuri määrä tietoa kompaktissa muodossa ja varmistaa tiedon koneellinen luettavuus koko toimitusketjun läpi. BEAst Label tukee myös GPS-pohjaisten purkupaikkakoordinaattien ja yhteystietojen liittämistä etikettiin.<br>

Standardi käyttää applikointitunnistetta (AI) 90 erotuksena STE/STILL-kuljetusetiketin tunnisteesta (AI) 00, mikä mahdollistaa järjestelmien rinnakkaisen käytön samalla SSCC-tunnisteella. BEAst Labelia sovelletaan toimitusketjun eri vaiheissa materiaalien tunnistamiseen, sähköisten sanomien tietosisällön yhdistämiseen ja toimitusten kohdistamiseen työmaan sisäisiin loppukohteisiin.<br>

BEAst Label muodostaa teknisen rajapinnan fyysisen etiketin ja sähköisen tiedonhallinnan välillä. Sen avulla toimitusketjun tiedot voidaan esittää yhteismitallisesti eri järjestelmissä ja varmistaa, että tunnistetiedot säilyvät yhdenmukaisina koko materiaalivirran läpi rakennuslogistiikassa.

<img width="500" alt="Kuva10" src="https://github.com/user-attachments/assets/66236156-7eb4-4c99-8b3b-fd0acc05e628" />

<img width="500" alt="Kuva11" src="https://github.com/user-attachments/assets/4c3906e6-dd32-40a7-bd5a-80f446fd814f" />





(BEAst Label)[https://beast.se/standarder/beast-label/#]
(BEAst Label-manual)[https://beast.se/wp-content/uploads/2018/10/BEAst-Label_Manual_v1-03.pdf]
	
	
## Lyhenteet ja terminologia

| Lyhenne / Käsite | Selite |
|------------------|---------|
| **Alkuperäisformaatti** | Mallinnusohjelman oma tallennusformaatti. Alan julkaisuissa käytetään tälle synonyyminä käsitteitä *natiivimalli* tai *natiiviformaatti*. |
| **BIM** | Tietomalli tai tietomallinnus, lyhenne englanninkielisestä käsitteestä *Building Information Modeling*. |
| **IFC** | Rakennusten mallinnuksessa käytetty tuotetietojen siirron kansainvälinen standardi, lyhenne englanninkielisestä käsitteestä *Industry Foundation Classes*. |
| **RFID** | *(Radio Frequency Identification)* – Tunnistus- ja tiedonkeruumenetelmä, jolla kohteet tunnistetaan automaattisesti, kerätään niitä koskevia tietoja ja syötetään ne suoraan tietojärjestelmiin (esim. viivakoodien tai RFID:n avulla). |
| **UDA** | Suunnitteluohjelmistoissa mallin objekteille talletettavaa liitännäistietoa (*metatietoa*), lyhenne englanninkielisestä käsitteestä *User Defined Attribute*. |
| **PropertySet** | Rakentamisalalla yleisesti käytetty termi ”Property Set”. Tässä dokumentissa käytetään termiä *Ominaisuusryhmä*, jotta se on helpommin ymmärrettävissä. Ominaisuusryhmien tarkka määrittäminen mahdollistaa ominaisuuksien ryhmittelyn ja selkeyttää tietorakennetta. |
| **Property** | Rakentamisalalla vakiintunut termi ”Property”. Tässä dokumentissa käytetään termiä *Ominaisuus*, jolla viitataan yksittäiseen määriteltyyn tietokenttään tai ominaisuuteen vakioidussa tietorakenteessa. |

	
	
	
	


## Viittaukset

​ 
[^1]:Domer & Bernadello, 2023, Interoperability: An introduction to IFC and buildingSmart standards integrating infrastructure modeling
​ 

​ 

​ 

​​ 
 
