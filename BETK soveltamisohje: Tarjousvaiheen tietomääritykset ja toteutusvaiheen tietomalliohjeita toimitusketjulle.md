# BETK soveltamisohje: Tarjousvaiheen tietomääritykset ja toteutusvaiheen tietomalliohjeita toimitusketjulle

**Tilauksesta suunniteltavat rakennustuotteet**  
>Julkaisija: Rakennusteollisuus ry\
>Päivämäärä: 17.12.2025  
Versio: 1.0
Status: Luonnos



## Asiakirjan tiedot
<details> 
<Summary>Asiakirjan versio</Summary>
 
| **Versio **| **Päivämäärä    **| **Tekijä**      |**Muutoskuvaus     **                           |
|------------|-------------------|-----------------|------------------------------------------------|
| 0.1        | 2024-12-30        |AnPekk           | Luonnos vaihe                                  |
| 0.2        | 2025-02-25        |AnPekk           |Tekstiosuuksia täydennetty                      |
| 0.3        | 2025-05-30        |AnPekk           | Tekstiosuuksia täydennetty                     |
| 0.4        | 2025-07-02        |AnPekk           | YIT, NCC ja Consoliksen kommentit huomioitu    |
| 0.5        | 2025-09-12        |AnPekk           | Elementtityyppi-listausta päivitetty           |
| 0.6        | 2025-10-22        |AnPekk           | Propertyjen nimet tarkistettu excelin mukaiseksi|
| 0.7        | 2025-12-05        |AnPekk           | Pintakäsittely ja väribetonit-kentät muokattu  |
| 1.0        | 2025-12-17        |AnPekk           | Github julkaisu                                |
</details>

<details> 
<Summary>Asiakirjan laatijat</Summary>

| **Nimi**            | **Organisaatio**               |
|---------------------|--------------------------------|
| Antti Pekkala       | Fira Oy                        |
| Teemu Anttila       | Ramboll                        |
| Janne Kihula        | Rakennustuoteteollisuus RTT ry |
| Teemu Alaluusua     | Aalto-yliopisto                |
| Tom Partanen        | Consolis Parma Oy              |
| Eetu Lahtinen       | Consolis Parma Oy              |
| Satu Parikka        | Consolis Parma Oy              |
| Kari Turunen        | Lujabetoni Oy                  |
| Markku Räisänen     | Betset Oy                      |
| Jarkko Vitikainen   | Sitowise Oy                    |
| Antti Taskinen      | Fira Oy                        |
| Riku Laiho          | NCC Suomi Oy                   |
| Arto Nieminen       | NCC Suomi Oy                   |
| Paula Valkonen      | Suutarinen / SBS Betoni Oy     |
</details>

1. [Tausta](#1-tausta)
2. [Soveltamisohjeen tarkoitus ja rajaukset](#2-soveltamisohjeen-tarkoitus-ja-rajaukset)
3. [Rakentamiskohteen tietomallin tietosisällöt tarjousvaiheessa](#3-rakentamiskohteen-tietomallin-tietosisällöt-tarjousvaiheessa)<br>
   3.1. [Elementin tuotetiedot tarjousvaiheessa](#31-elementin-tuotetiedot-tarjousvaiheessa)<br>
      3.1.1. [Kokoonpanon tyyppi](#311-kokoonpanon-tyyppi)<br>
      3.1.2. [Elementtityyppi](#312-elementtityyppi)<br>
      3.1.3. [Raudoitus](#313-raudoitus)<br>
      3.1.4. [Pintakäsittely](#314-pintakäsittely)<br>
      3.1.5. [Vähähiilinen](#315-vähähiilinen)<br>
      3.1.6. [Tyyppielementti](#316-tyyppielementti)<br>
      3.1.7. [Työmaalla käännettävä elementti](#317-työmaalla-käännettävä-elementti)<br>
4. [Toimintaohjeita hankkeisiin](#4toimintaohjeita-hankkeisiin)
5. [Lyhenteet ja terminologia](#lyhenteet-ja-terminologia)
6. [Viittaukset](#viittaukset)
7. [Liite 1: Esimerkkejä raudoitustiedosta betonielementti tehtaan tarjouslaskennassa](#liite-1-esimerkkejä-raudoitustiedosta-betonielementti-tehtaan-tarjouslaskennassa)
---

## 1 Tausta
Tällä hetkellä rakennushankkeen tietomallit ovat yleinen osa hankkeen tarjouspyyntöjä ja niiden määrä- ja kustannuslaskentaa. Suunnittelijoiden tekemiä tietomalleja käyttävät ra-kennusliikkeet ja elementtitoimittajat mm. määrä- ja tarjouslaskennassa, hankkeen toteu-tuksen suunnittelussa ja aikatauluttamisessa jne. BEC2012-hankkeessa luodut vakioidut tietokentät, mallinnusohje ja mallinnustyökalut ovat alalla yleisesti käytössä.  BEC-ohjeistus ei kuitenkaan mahdollista koneluettavaa tiedonsiirtoa koska usea asia on BEC-ohjeistuksessa määritetty hankekohtaisesti sovittavaksi eikä tietokentille ole ohjeistettu sallittuja arvoja. Tiedot ovat saatavissa tietomalleista mutta edellyttää ihmisen taitoa lukea tietomallia ja samalla myös muita hankkeen suunnitelmadokumentteja. Esimerkkinä täl-laisesta käyttötapauksesta on esim. kuinka tunnistetaan tiililaattapintaiset SW-elementit hankkeen tietomallista ja muista elementeistä. Tällä hetkellä tunnistaminen ei onnistu au-tomaattisesti. Soveltamisohjeessa kuvattu ratkaisu elementtityyppien tunnistamiseen pohjautuu alalla yleisesti käytettyihin elementtityyppitunnuksiin, esim. V, R ja S jne.  Usein hankkeissa käytetään hankekohtaisesti sovittuna elementtityyppitunnuksessa myös pintakäsittelyä tai sijaintia tarkentavia numero- tai kirjainyhdistelyitä, kuten esim. V1-A. Nämä johtavat siihen, että elementtityyppejä ei voida tunnistaa koneluettavasti hankkeesta toiseen. 

IFC-tietomallistandardissa rakenneosien tunnistamiseksi objekteille voidaan määrittää IFC-luokkia, kuten esimerkiksi ifcwall. Useilla IFC-luokilla on lisäksi PredefinedType-ominaisuus, joka tarkentaa luokan tyyppiä. Esimerkiksi ifcwall-luokka voi sisältää Predefi-nedType-arvoja, kuten "standard" tai "movable". Standardissa määriteltyjen luokittelui-den tarkkuustaso riittää karkeaan luokitteluun, mutta ei mahdollista riittävän tarkkaa tunnistamista määrä- ja kustannuslaskentaa varten. Tämän vuoksi tarvitaan lisäattribuutteja, jotta tietomallin avulla saavutetaan vaadittava tarkkuustaso. Ohjeessa kuvattu rat-kaisusta on tehty myös esimerkki malli Tekla Structures-ohjelmassa ja mallista IFC-tiedosto, eli ratkaisu on myös toteuttamiskelpoinen nykyisillä ohjelmistoilla.

Tämä soveltamisohje on tehty osana Rakennusteollisuus RT:n tuotetiedon ja toimitusketjun digitalisoinnin kehityshanketta, BETK-työryhmän toimesta. Kehityshankkeen ensisijainen tavoite on edistää rakennusalan tuotteiden toimitusketjun hallinnan menetelmien siirtymistä manuaalisesta ja rakenteettomasta tiedonvaihdosta täysin rakenteelliseen ja koneluettavaan tiedonvaihtoon. Asiakirja on jatkuvasti päivittyvä ja sitä kehitetään edelleen Rakennusteollisuus RT:n kehityshankkeen havaintojen perusteella. Tätä ohjetta täydentävät muut BETK-hankkeen julkaisut:

•	BETK Soveltamisohje_Tuoteyksilöinti ja -tunnistaminen[1]

•	Excel-taulukko muuttujista [2]

•	Soveltamisohje GS1 EPCIS (tapahtumatieto) käytöstä [syksyllä tehdään] [3]

•	Keskustelupaperi sijaintitiedoista rakennushankkeessa. [4]


## 2 Soveltamisohjeen tarkoitus ja rajaukset
Soveltamisohje keskittyy suunnittelijan tuottaman tietomallin sisällön vakiointiin tarjousvaiheessa. Samalla BEC2012-tietokenttien nimeämistä on tarkennettu ja IFC-malliin kirjoitettavia ominaisuuksia määritetty elementtityyppikohtaiseksi tiedonsiirron laadun parantamiseksi ja samalla on tietokenttien nimeämisessä pyritty huomioimaan mahdollisesti tulevaisuudessa kehitettävää muiden rakenneosien ja materiaalien tunnistamista ja vakiointia. Tiedonsiirron vakiointia on myös kehitetty lisäämällä sallittujen arvojen listauksia tietokenttiin joissa se mahdollista tehdä. Tietokentissä on huomioitu myös tietomallin rikastamista toteutusvaiheessa toimitusketjulta tulevilla tiedoilla.  Soveltamisohjetta täydentävät erillinen taulukko tietokentistä joissa mm. elementtien mittatiedot ja esimerkkitietomalli. Tätä soveltamisohjetta täydentää myös erillinen ohje elementtien yksilöinnistä toimitusketjussa  [1] ja esimerkki malli IFC-muodossa. Tätä soveltamisohjetta voidaan päivittää myöhemmin standardoinnin edetessä. Tämä soveltamisohje ei ota kantaa muuhun tarjouspyyntö aineistoon. 

## 3 Rakentamiskohteen tietomallin tietosisällöt tarjousvaiheessa
Tarjousvaiheessa tietomallissa käytettävät tietokentät elementtityyppien tunnistamiseen on kuvattu alla olevissa taulukoissa. Taulukoiden arvojen lisäksi hankintavaiheessa tarvittavat mitta- ja pinta-alojen tietokentät kuvattu erillisessä excel-taulukossa [2]. Excel-taulukossa on myös muita toteu-tusvaiheessa tarvittavia tietokenttiä sallittuine arvoineen

### 3.1 Elementin tuotetiedot tarjousvaiheessa

#### 3.1.1 Kokoonpanon tyyppi
Betonielementtien erottamiseen tietomallin muista objekteista voi käyttää Kokoonpanon-tyyppi kenttää. 


###### Taulukko 1.

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td>KOKOONPANON TYYPPI</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td>–</td>
      </tr>
      <tr>
        <th scope="row">PropertySet</th>
        <td>BETK</td>
      </tr>
      <tr>
        <th scope="row">Property<br>Attribute</th>
        <td>Tyyppielementti</td>
      </tr>
          <th rowspan="5">Sallitut arvot</th>
      <td>BETONIELEMENTTI</td>
     </tr>
    <tr>
      <td>PAIKALLAVALU</td>
     <tr>
      <td>PUUKOKOONPANO</td>
      </tr>
      <tr>
      <td>TERÄSKOKOONPANO</td>
       </tr>
      <tr>
      <td>EI ASETETTU</td>
    </tr>
    </tbody>
  </table>
</body>
</html>

#### 3.1.2 Elementtityyppi
Elementtityyppi-tietokenttä tunnistaa mallin eri elementit. Tiedot syötetään tarjouksen yhteydessä ja päivitetään tarvittaessa toteutuksessa, jotta loppuselvityksessä voidaan tehdä tarvittaessa määrälaskenta.

###### Taulukko 2. 

<html>
<table>
    <thead>
        <tr>             
         <th colspan="3">IFC tietokentät</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>Tietosisältötarve</b></td>
            <td colspan="2"><b>Elementtityyppi</b></td>
        </tr>
          <tr>
            <td>Rajaukset</td>
            <td colspan="2">-</td>
        </tr>
        <tr>
            <td>Propertyset</td>
            <td colspan="2">BETK-hankinta</td>
        </tr>
         <tr>
            <td>Property Attribute</td>
            <td colspan="2">Sallitut arvot jaetaan kahteen ominaisuuskenttään:  
Elementin tyyppi, koodi ( AK jne)
Elementin tyyppi, kuvaus (Sokkelipalkki jne)
</td>
        </tr>
        <tr>
            <td rowspan="67">Sallitut arvot<br>(Enumerated options)</td>
            <td><code>A</code></td>
            <td>Anturaelementti</td>
        </tr>
        <tr>
            <td>PH</td>
            <td>Pilariholkkielementti</td>
        </tr>
      <tr>
            <td>AN</td>
            <td>Sokkelielementti (ei-kantava)</td>
        </tr>
     <tr>
            <td>AS</td>
            <td>Sokkelielementti (kantava)</td>
        </tr>
      <tr>
            <td>AS</td>
            <td>Sokkelielementti (kantava)</td>
        </tr>
      <tr>
       <td>AK</td>
       <td>Sokkelipalkki</td>
      </tr>
    <tr>
     <td>AR</td>
     <td>Sokkeliruutuelementti (maanpaine)</td>
    </tr>
    <tr>
     <td>AV</td>
     <td>Sokkelielementti (yksi kuori)</td>
    </tr>
    <tr>
     <td>MP</td>
     <td>Maanpaineseinäelementti</td>
    </tr>
    <tr>
     <td>TKE</td>
     <td>Tukimuurielementti</td>
    </tr>
    <tr>
     <td>MUU</td>
     <td>Muu perustuselementti</td>
    </tr>
    <tr>
     <td>P</td>
     <td>Pilari</td>
    </tr>
    <tr>
     <td>MUU</td>
     <td>Muu pilarielementti</td>
    </tr>
    <tr>
     <td>V</td>
     <td>Väliseinä</td>
    </tr>
    <tr>
     <td>VSP</td>
     <td>Väliseinä (seinämäinen palkki)</td>
    </tr>
    <tr>
     <td>S</td>
     <td>Ruutuelementti (kantava)</td>
    </tr>
    <tr>
     <td>R</td>
     <td>Ruutuelementti (ei-kantava)</td>
    </tr>
    <tr>
     <td>SK</td>
     <td>Sisäkuorielementti (kantava)</td>
    </tr>
    <tr>
     <td>RK</td>
     <td>Sisäkuorielementti (ei-kantava)</td>
    </tr>
    <tr>
     <td>SKE</td>
     <td>Sisäkuorielementti (kantava, tehdaseriste)</td>
    </tr>
    <tr>
     <td>RKE</td>
     <td>Sisäkuorielementti (ei kantava, tehdaseriste)</td>
    </tr>
    <tr>
     <td>SKRO</td>
     <td>Ohutrapattu elementti (kantava)</td>
    </tr>
    <tr>
     <td>RKRO</td>
     <td>Ohutrapattu elementti (ei-kantava)</td>
    </tr>
    <tr>
     <td>SKRP</td>
     <td>Paksurapattu elementti (kantava)</td>
    </tr>
    <tr>
     <td>RKRP</td><td>Paksurapattu elementti (ei-kantava)</td>
    </tr>
    <tr>
     <td>NK</td>
     <td>Nauhaelementti (kantava)</td>
    </tr>
    <tr>
     <td>N</td>
     <td>Nauhaelementti (ei-kantava)</td>
    </tr>
    <tr>
     <td>KE</td>
     <td>Kuorielementti</td>
    </tr>
    <tr>
     <td>MUU</td>
     <td>Muu seinäelementti</td>
    </tr>
    <tr>
     <td>K</td>
     <td>Palkkielementti (teräsbetoni)</td>
    </tr>
    <tr>
     <td>I</td>
     <td>Jännebetonipalkki (I-profiili)</td>
    </tr>
    <tr>
     <td>HI</td>
     <td>Jännebetonipalkki (HI-profiili)</td>
    </tr>
    <tr>
     <td>JK</td>
     <td>Jännebetonipalkki (muut profiilit)</td>
    </tr>
    <tr>
     <td>JR</td>
     <td>Jäykistesauva</td>
    </tr>
    <tr>
     <td>MUU</td>
     <td>Muu palkkielementti</td>
    </tr>
    <tr>
     <td>L</td>
     <td>Laattaelementti (massiivilaatta, välipohja)</td>
    </tr>
    <tr>
     <td>EL</td>
     <td>Alapohjalaatta (massivilaatta, eristetty)</td>
    </tr>
    <tr>
     <td>JL</td>
     <td>Jännitetty laattaelementti</td>
    </tr>
    <tr>
     <td>O</td>
     <td>Ontelolaatta</td>
    </tr>
    <tr>
     <td>KL</td>
     <td>Kuorilaatta</td>
    </tr>
    <tr>
     <td>SL</td>
     <td>Luja-Superlaatta</td>
    </tr>
    <tr>
     <td>TT</td>
     <td>TT-laatta</td>
    </tr>
    <tr>
     <td>TEK</td>
     <td>TEK-laatta</td>
    </tr>
    <tr>
     <td>STT</td>
     <td>SuperTT-laatta</td>
    </tr>
    <tr>
     <td>HTT</td>
     <td>HTT-laatta</td>
    </tr>
    <tr>
     <td>RL</td>
     <td>Ripalaatta</td>
    </tr>
    <tr>
     <td>MUU</td>
     <td>Muu laattaelementti</td>
    </tr>
    <tr>
     <td>C</td>
     <td>Parveke-elementti</td>
    </tr>
    <tr>
     <td>CL</td>
     <td>Parvekelaatta-elementti</td>
    </tr>
    <tr>
     <td>CP</td>
     <td>Parvekepilari</td>
    </tr>
    <tr>
     <td>JCL</td>
     <td>Jännitetty parvekelaattaelementti</td>
    </tr>
    <tr>
     <td>UCL</td>
     <td>Ulokeparvekelaatta</td>
    </tr>
    <tr>
     <td>M</td>
     <td>Parvekepieli-elementti</td>
    </tr>
    <tr>
     <td>Z</td>
     <td>Parvekekaide-elementti</td>
    </tr>
    <tr>
     <td>CX</td>
     <td>Parvekekattoelementti</td>
    </tr>
    <tr>
     <td>JCX</td>
     <td>Jännitetty parvekkeen kattoelementti</td>
    </tr>
    <tr>
     <td>MUU</td>
     <td>Muu parveke-elementti</td>
    </tr>
    <tr>
     <td>T</td>
     <td>Porraselementti</td>
    </tr>
    <tr>
     <td>MUU</td>
     <td>Muu porraselementti</td>
    </tr>
    <tr>
     <td>HK</td>
     <td>Hissikuiluelementti</td>
    </tr>
    <tr>
     <td>HKA</td>
     <td>Hissikuilun pohjaelementti</td>
    </tr>
    <tr>
     <td>HKL</td>
     <td>Hissikuilun kattolaatta</td>
    </tr>
    <tr>
     <td>HKY</td>
     <td>Hissikuilun yläpään elementti</td>
    </tr>
    <tr>
     <td>MUU</td>
     <td>Muu hissikuilun elementti</td>
    </tr>
    <tr>
     <td>H</td>
     <td>Hormielementti</td>
    </tr>
    <tr>
     <td>MUU</td>
     <td>Muu erikoiselementti</td>
    </tr>
    <tr><td>Ei asetettu</td><td>Ei  asetettu</td></tr>
    </tbody>
</table>
</html>

#### 3.1.3 Raudoitus
Raudoitustietokentästä valitaan elementtityypin raudoitustyyppitieto. Description-kentässä tarkempi kuvaus. Esim R1 ja 2T10 ymp tai R2 ja 2T10 ymp , #10-200 mp. Tarvittaessa hankkeessa käytetyt raudoituskoodit voi tarkentaa erillisessä mallin mukana toimitettavassa dokumentissa. Esimerkkitaulukot raudoitustiedosta tarjousvaiheessa ohjeen lopussa. 

###### Taulukko 3. 

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">RAUDOITUS</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">PropertySet</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Property</th>
        <td colspan="2"><b>Raudoitus 1, koodi<br>Raudoitus 1, kuvaus<br>Raudoitus 2, koodi<br>Raudoitus 2, kuvaus</b></td>
      </tr>
          <th rowspan="11">Sallitut arvot<br>(Option list/String UDA)</th>
      <td>R1</td>
      <td>Description</td>
     </tr>
    <tr>
        <td>R1</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R2</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R3</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R4</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R5</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R6</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R7</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R8</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R9</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>Ei asetettu</td>
        <td></td>
     </tr>
    </tbody>
  </table>
</body>
</html>

#### 3.1.4 Pintakäsittely
Pintakäsittely-tietokenttään merkitään tarjousvaiheessa elementin ulkokuoren pintakäsit-tely. Jos samassa elementissä useampaa pintakäsittelyä käytetään tarvittaessa arvoja PK2, PK3 tarkentamaan tyypitystä. Toteutusvaiheessa käytetään BY40 mukaista koodausta, ks. kohta 4. 

###### Taulukko 4.

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">PINTAKÄSITTELY</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">PropertySet</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Property</th>
        <td colspan="2">Pintakäsittely</td>
      </tr>
          <th rowspan="30">Sallitut arvot<br>(Option list)</th>
      <td colspan="2">PK1</td>
     </tr>
    <tr>
      <td rowspan="9">(Enumerated options if selected)</td>
      <td>01 Muottia vasten valettu pinta, harmaa</td>
    </tr>
       <tr>
         <td>02 Valkoinen väribetonipinta</td>
         </tr>
      <tr>
         <td>03 Tiililaattapinta (poltetut tiilet)</td>
         </tr>
      <tr>
         <td>04 Hienopesty pinta</td>
         </tr>
      <tr>
         <td>05 Valukalvon päälle valettu pesubetonipinta</td>
         </tr>
      <tr>
         <td>06 Musta väribetonipinta</td>
         </tr>
      <tr>
         <td>07 Punainen väribetonipinta</td>
         </tr>
      <tr>
         <td>08 Uritettu pinta</td>
         </tr>
      <tr>
         <td>09 Muu pinta</td>
         </tr>
      <tr>
      <td colspan="2">PK2</td>
      </tr>
          <td rowspan="9">(Enumerated options if selected)</td>
      <td>01 Muottia vasten valettu pinta, harmaa</td>
    </tr>
       <tr>
         <td>02 Valkoinen väribetonipinta</td>
         </tr>
      <tr>
         <td>03 Tiililaattapinta (poltetut tiilet)</td>
         </tr>
      <tr>
         <td>04 Hienopesty pinta</td>
         </tr>
      <tr>
         <td>05 Valukalvon päälle valettu pesubetonipinta</td>
         </tr>
      <tr>
         <td>06 Musta väribetonipinta</td>
         </tr>
      <tr>
         <td>07 Punainen väribetonipinta</td>
         </tr>
      <tr>
         <td>08 Uritettu pinta</td>
         </tr>
      <tr>
         <td>09 Muu pinta</td>
         </tr>
       <tr>
      <td colspan="2">PK3 - 9 (jos tarvetta)</td>
      </tr>
          <td rowspan="9">(Enumerated options if selected)</td>
      <td>01 Muottia vasten valettu pinta, harmaa</td>
    </tr>
       <tr>
         <td>02 Valkoinen väribetonipinta</td>
         </tr>
      <tr>
         <td>03 Tiililaattapinta (poltetut tiilet)</td>
         </tr>
      <tr>
         <td>04 Hienopesty pinta</td>
         </tr>
      <tr>
         <td>05 Valukalvon päälle valettu pesubetonipinta</td>
         </tr>
      <tr>
         <td>06 Musta väribetonipinta</td>
         </tr>
      <tr>
         <td>07 Punainen väribetonipinta</td>
         </tr>
      <tr>
         <td>08 Uritettu pinta</td>
         </tr>
      <tr>
         <td>09 Muu pinta</td>
         </tr>
    </tbody>
  </table>
</body>
</html>

#### 3.1.5 Vähähiilinen
Vähähiilinen-tiedon avulla mahdollista erotella tarjousvaiheessa vähähiiliseksi ajattelut tuotteet Kyllä/Ei-valinnalla.

###### Taulukko 5. 

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">VÄHÄHIILINEN</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">PropertySet</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Property</th>
        <td colspan="2">Vähähiilinen</td>
      </tr>
          <th rowspan="2">Sallitut arvot<br>(String)</th>
      <td colspan="2">Ei</td>
     </tr>
    <tr>
      <td>Kyllä</td>
      <td>Description </td>
    </tr>
    </tbody>
  </table>
</body>
</html>

#### 3.1.6 Tyyppielementti
Kyllä/-Ei-tieto elementistä, joka on varusteltu tietomallissa toteutusta vastaavaksi tyyp-pielementiksi.

###### Taulukko 6. 

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">TYYPPIELEMENTTI</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">PropertySet</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Property</th>
        <td colspan="2">Tyyppielementti</td>
      </tr>
          <th rowspan="2">Sallitut arvot<br>(Boolean)</th>
      <td colspan="2">Ei</td>
     </tr>
    <tr>
      <td>Kyllä</td>
      <td>Description (piirustustiedosto)</td>
    </tr>
    </tbody>
  </table>
</body>
</html>
      
#### 3.1.7	Työmaalla käännettävä elementti
Tieto työmaalla käännettävästä elementistä. Asennustyön hinnoittelua varten tarvittava tieto. Jos ei ole tietoa asennustavasta niin kenttä jätetään tyhjäksi.

###### Taulukko 7. 

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">KÄÄNTÖKIVI</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">PropertySet</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Property</th>
        <td colspan="2">Kääntökivi</td>
      </tr>
          <th rowspan="2">Sallitut arvot<br>(Boolean)</th>
      <td colspan="2">Ei</td>
     </tr>
    <tr>
      <td>Kyllä</td>
      <td>Description</td>
    </tr>
    </tbody>
  </table>
</body>
</html>

## 4	Toimintaohjeita hankkeisiin  
**Numerointi**   
Tässä ohjeessa kuvattu elementtityyppien yksilöinti ja tunnistaminen ei vaikuta hankkeis-sa käytettyyn toteutusvaiheen elementtien numerointiin ja piirustusten nimeämiseen. Numerointi voidaan sopia hankekohtaisesti huomioiden mm. Tekla Strucrures-ohjelman numeroinnin ominaisuudet. Jos toteutusvaiheessa käytetään Tuoteyksilöinti ja -tunnistaminen ohjeessa [1] kuvattua tapaa elementtien yksilöintii ei ACN-numeron käytölle ole tarvetta.  

**Sijaintieto**  
Lohko- ja kerrostiedosta erillinen ohje  

**Revisiointi käytännöt**  

**Toimintaohje elementtien revisiointiin**  


## Lyhenteet ja terminologia

<html>
<table>
    <tbody>
        <tr>            
          <td>Alkuperäisformaatti</td>
          <td>Mallinnusohjelman oma tallennusformaatti. Alan julkaisuissa käytetään tälle synonyyminä käsitteitä natiivimalli tai natiiviformaatti.</td>
        </tr>
        <tr>
           <td>BIM</td>
          <td>Rakennuskohteen tietomalli tai tietomallinnus, lyhenne englanninkielisestä käsitteestä Building Information Modeling <sup>[1]</sup></td>
        </tr>
        <tr>
          <td>IFC</td>
          <td>Rakennusten mallinnuksessa käytetty tuotetietojen siirron kansainvälinen standardi, lyhenne englanninkielisestä käsitteestä Industry Foundation Classes. </td>
        </tr>
         <tr>
          <td>UDA</td>
          <td>Suunnitteluohjelmistoissa mallin objekteille talletettavaa liitännäistietoa (metatieto), lyhenne englanninkielisestä käsitteestä User Defined Attribute.</td>
        </tr>
        <tr>
          <td>PropertySet</td>
          <td>Rakentamisalalla on yleisesti käytössä ”Property Set” -termi. Tässä dokumentissa käytetään termiä ”Ominaisuusryhmä”, jotta termi on helpommin ymmärrettävissä ja päästään eroon vieraskielisestä termistä. Ominaisuusryhmien tarkka määrittäminen mahdollistaa ominaisuuksien ryhmittelyn ihmiselle sopiviin kokonaisuuksiin. Usealla ominaisuusryhmällä vältetään myös ominaisuuksien pitkä listaus yhdessä ”kaiken kattavassa” ominaisuusryhmässä. </td>
        </tr>
           <tr>
          <td>Property</td>
          <td>Rakentamisalalle on vakiintunut ”Property” -termin käyttö. Tässä dokumentissa käytetään termiä ”Ominaisuus”, jotta termi on helpommin ymmärrettävissä ja päästään eroon vieraskielisestä termistä. Ominaisuuksien tarkka määrittäminen mahdollistaa vakioidun tietorakenteen. </td>
        </tr>
    </tbody>
</table>
</html>


## Viittaukset
**[1]** GS1 (2022), Recommendation for the use of EPC and ISO RFID symbols   

**[2]** ISO/IEC 29160:2020, Information technology — Radio frequency identification. Available: https://www.iso.org  



## Liite 1: Esimerkkejä raudoitustiedosta betonielementti tehtaan tarjouslaskennassa
