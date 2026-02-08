# BETK keskustelupaperi: Tapahtumatiedon jakaminen toimitusketjussa


>Julkaisija: Rakennusteollisuus ry\
>Luonnos: 06.02.2026

<details>
<summary>Asiakirjan tiedot </summary>

| Selite                | Arvo                                                                |
|-----------------------|---------------------------------------------------------------------|
| Asiakirjan nimi       | BETK keskustelupaperi: Tapahtumatiedon jakaminen toimitusketjussa |
| Asiakirjan päivämäärä | 06.02.2026                                                         |
| Asiakirjan versio     | 0.0.1                                                                 |
| Asiakirjan status     | Luonnos                                                             |

</details>

<details>
<summary>Asiakirjan laatijat </summary>

| Nimi             | Organisaatio                  |
|------------------|-------------------------------|
| Teemu Alaluusua  | Aalto-yliopisto               |
| Tom Partanen     | Consolis Parma Oy             |
| Antti Taskinen   | Fira                          |

</details>

<details>
<summary> Asiakirjan versio </summary>

| Versio  | Päivämäärä  | Tekijä  | Muutoskuvaus               |
|---------|-------------|---------|----------------------------|
| 0.0.1   | 6.2.2026    | TAla    | Luonnos vaihe              |

 </details>

## Sisällysluettelo

1. [Johdanto](#1-johdanto)<br>
2. [Miksi edistää tapahtumatiedon jakamisen käyttöönottoa?](#2-miksi-edistää-tapahtumatiedon-jakamisen-käyttöönottoa)<br>
   2.1. [GS1 EPCIS](#21-gs1-epcis)<br>
   2.2. [Toimintaympäristön tunnistetut haasteet tapahtumatiedon jakamisen osalta](#22-toimintaympäristön-tunnistetut-haasteet-tapahtumatiedon-jakamisen-osalta)<br>
3. [Pohdintaa CBV-standardin soveltamisesta tilauksesta suunniteltavien rakennustuotteiden toimitusketjussa](#3-pohdintaa-cbv-standardin-soveltamisesta-tilauksesta-suunniteltavien-rakennustuotteiden-toimitusketjussa)<br>
  3.1. [Suunnitteluvaihe](#31-suunnitteluvaihe)<br>
  3.2. [Tuotevalmistus](#32-tuotevalmistus)<br>
  3.3. [Tiedonkantaja](#33-tiedonkantaja)<br>
  3.4. [Kuljetus](#34-kuljetus)<br>
  3.5. [Työmaa](#35-työmaa)<br>
  3.6. [Poikkeama](#36-poikkeama)<br>
  3.7. [Ylläpito ja elinkaari](#37-ylläpito--elinkaari)<br>
4. [Rakennusalan erityistarpeisiin kohdistuvat CBV-statuslisäykset](#4-rakennusalan-erityistarpeisiin-kohdistuvat-cbv-statuslisäykset)<br>

---

## 1. Johdanto

Tämän keskustelupaperin tavoitteena on jäsentää ja koota havaintoja, tunnistettuja ongelmia ja kehityssuuntia tapahtumatiedon jakamiseen liittyen ja toimia mahdollisen toimialakohtaisen soveltamisohjeen lähtökohtana. Dokumentti ei ole normi, standardi eikä valmis ohje, vaan tarkoitettu yhteisen ymmärryksen rakentamiseen ja jatkokehityksen tueksi. Dokumentti kytkeytyy Rakennusteollisuus RT:n käynnissä olevaan toimitusketjujen digitaalisen hallinnan kehitystyöhön, jossa pyritään siirtymään manuaalisesta ja rakenteettomasta tiedonvaihdosta kohti rakenteellista ja koneluettavaa tiedonhallintaa.

Tämä keskustelupaperi kytkeytyy BETK-työryhmän aiemmin julkaisemaan tilauksesta suunniteltavien rakennustuotteiden tuoteyksilöinnin ja -tunnistamisen [soveltamisohjeeseen](https://github.com/BETK-Finland/BETK_Documents_FI/blob/main/02_soveltamisohjeet/Tuoteyksil%C3%B6innin%20ja%20-tunnistamisen%20yhteentoimivuuden%20soveltamisohje.md), mikä toimii tapahtumatiedon jakamisen lähtökohtana (soveltamisohjeen sisältöä on havainnollistettu alla olevassa kuvassa).

<img width="2343" height="3541" alt="2025-10-13_Kuva1(fi)" src="https://github.com/user-attachments/assets/8b3d332d-0bfd-411d-b3ab-7927fceb5e97" /><br> Kuva 1

Rakenteellisten tilauksesta suunniteltavien runkotuotteiden osalta tapahtumatiedon merkitys korostuu erityisesti asennusvaiheessa, jossa yksilöity fyysinen tuote asennetaan osaksi rakennettavaa kohdetta. Rajatuissa piloteissa on havaittu, että asennusvaiheessa tuotteiden suunniteltu ja toteutunut asennussijainti eivät välttämättä vastaa toisiaan. Mikäli yksittäisen elementin ominaisuuksissa havaitaan poikkeama, edellyttää tilanteen hallinta kykyä jäljittää kyseinen tuote ja sen todellinen asennussijainti yksiselitteisesti. Ilman rakenteellisesti määriteltyä ja jaettua tapahtumatietoa tuoteyksilöinnin ja toteutuneen asennuksen välinen yhteys voi katketa, mikä heikentää jäljitettävyyttä ja voi muodostaa rakenteellisen turvallisuusriskin. Tämän vuoksi asennussijaintiin kytkeytyvä tapahtumatieto on keskeinen edellytys tilauksesta suunniteltavien runkotuotteiden toimitusketjun luotettavuudelle, riskienhallinnalle ja elinkaaritiedon eheydelle.

## 2. Miksi edistää tapahtumatiedon jakamisen käyttöönottoa?
Toimitusketjujen kehittämistyössä on tunnistettu merkittävä tarve tuottaa ja jakaa tapahtumatietoa, joka tukee rakennustuotteiden jäljitettävyyttä koko niiden elinkaaren ajan. Tapahtumatiedolla tarkoitetaan tässä yhteydessä rakenteellista tietoa tuotetta koskevista tapahtumista, kuten valmistuksesta, varastoinnista, kuljetuksesta, vastaanotosta, asennuksesta sekä mahdollisesti myös suunnittelun, ylläpidon ja käytön aikaisista toimenpiteistä.

Tapahtumatiedon systemaattinen tuottaminen ja jakaminen mahdollistaa siirtymisen dokumenttipohjaisesta ja jälkikäteisestä tiedonvaihdosta kohti reaaliaikaista ja automaattisesti hyödynnettävää tiedonhallintaa. Jäljitettävyyden näkökulmasta tapahtumatieto muodostaa mekanismin, jonka avulla tuotteen fyysinen sijainti, tila ja historia voidaan kytkeä sitä koskevaan digitaaliseen tietoon toimitusketjun eri vaiheissa tuotevalmistuksesta asennukseen ja edelleen ylläpidon aikaisiin toimintoihin.

Tapahtumatiedon kehittämispotentiaali perustuu sen kykyyn tehdä prosessien todellinen toteutuminen systemaattisesti analysoitavaksi. Prosessien ohjaus ja kehittäminen nojaavat usein oletettuihin toimintamalleihin ja aggregoituihin suorituskykymittareihin, jotka eivät vastaa sitä, miten toiminta tosiasiallisesti etenee käytännössä. Tutkimuksessa on osoitettu, että toimijat sekoittavat usein suunnitellun prosessin sen todelliseen toteutumiseen, mikä heikentää kehittämistoimenpiteiden kohdentumista (van der Aalst, 2022).

Nykyiset tietojärjestelmät, kuten ERP-, toimitusketju-, EPCIS-, RFID- ja IoT-järjestelmät, tuottavat laajoja määriä aikaleimattua tapahtumatietoa, joka kuvaa prosessien toteutuneita vaiheita ja niiden välisiä riippuvuuksia. Prosessilouhinta hyödyntää tätä tapahtumatietoa rekonstruoimalla prosessit sellaisina kuin ne ovat toteutuneet, jolloin analyysi perustuu havaittuun toimintaan eikä yksittäisiin oletuksiin tai tunnuslukuihin. Tapahtumatietoon perustuva analyysi mahdollistaa sekä tyypillisen prosessikäyttäytymisen että harvinaisten, mutta usein suhteettoman paljon resursseja kuluttavien prosessivarianttien tunnistamisen (van der Aalst, 2022).

Rakennetun ympäristön kontekstissa tapahtumatiedon merkitys korostuu prosessien moniulotteisuuden vuoksi. Yksittäiset tapahtumat liittyvät samanaikaisesti useisiin objekteihin, kuten tuotteisiin, resursseihin ja sijainteihin, jolloin prosessit muodostuvat useiden toisiinsa kytkeytyvien elinkaarien vuorovaikutuksesta. Prosessianalyysi, joka nojaa yhteen prosessia kuvaavaan tunnisteeseen, ei kykene kuvaamaan tällaista kokonaisuutta riittävällä tarkkuudella. Objektikeskeinen prosessilouhinta mahdollistaa prosessien mallintamisen näiden objektien välisten suhteiden kautta ja tuottaa realistisemman perustan juurisyyanalyysille ja prosessien kehittämiselle (van der Aalst, 2022).

Tapahtumatiedon hyödyntäminen edellyttää kuitenkin riittävää tiedon laatua ja johdonmukaisuutta. Puutteellinen tai epäyhtenäisesti määritelty tapahtumatieto heikentää analyysin luotettavuutta ja rajoittaa sen hyödynnettävyyttä, mikä korostaa systemaattisen tapahtumatiedon tuottamisen ja standardoitujen tietokäytäntöjen merkitystä. Kokonaisuutena tapahtumatieto muodostaa perustan dataohjautuvalle ja systeemiselle toimitusketjujen ja tuotantoprosessien kehittämiselle (van der Aalst, 2022).

### 2.1 GS1 EPCIS

Tapahtumatiedon rakenteellinen ja semanttinen yhteentoimivuus edellyttää laajasti hyväksyttyjen standardien hyödyntämistä yksittäisten, tapauskohtaisten tiedostomallien sijaan. Tässä kontekstissa GS1:n EPCIS-standardi muodostaa keskeisen viitekehyksen fyysisiin tuotteisiin ja niihin liittyviin tapahtumiin kytkeytyvän tiedon yhtenäiseen esittämiseen ja jakamiseen organisaatio- ja järjestelmärajojen yli. EPCIS on ISO-standardoitu ja sovellusriippumaton standardi, joka määrittelee tapahtumatiedon rakenteen ja rajapinnat, mutta ei sido toteutusta tiettyyn teknologiaan tai tietovarastoratkaisuun.

EPCIS on luonteeltaan tapahtumatietomalli, joka täydentää perinteisiä liiketoimintasanomia. Eurooppalaisessa kontekstissa keskeinen esimerkki tästä on Peppol-verkosto ja sen taustalla oleva UBL-pohjainen sanomamalli, jota hyödynnetään tilauksissa, toimitusilmoituksissa ja verkkolaskuissa. UBL-sanomat on suunniteltu ensisijaisesti liiketoimintatransaktioiden välittämiseen, eivätkä ne sellaisenaan kata toimitusketjun yksityiskohtaista tapahtumatietoa, tuoteyksilöintiä tai käsittelyvaiheita. EPCIS ei korvaa Peppolia tai UBL:ää, vaan täydentää niitä tarjoamalla erillisen ja tarkoituksenmukaisen mallin tapahtuma- ja jäljitettävyystiedolle, jota voidaan hyödyntää joko UBL-sanomien liitteenä tai täysin itsenäisesti järjestelmien välisessä tiedonvaihdossa.

Teknisesti EPCIS mahdollistaa tapahtumatiedon esittämisen useissa yleisesti käytetyissä rakenteellisissa formaateissa. Perinteisesti EPCIS-tapahtumat on kuvattu XML-muodossa, mikä tukee olemassa olevia sanomavälitysjärjestelmiä ja Peppol-ympäristöä. Uudemmissa toteutuksissa EPCIS tukee myös JSON-muotoista esitystä, joka soveltuu kevyempiin integraatioihin ja rajapintapohjaiseen tiedonvaihtoon. Lisäksi EPCIS-tapahtumatietoa voidaan esittää JSON-LD-muodossa, jolloin tapahtumatiedolle voidaan liittää eksplisiittinen semanttinen konteksti ja linkittää se muihin tietomalleihin ja tietolähteisiin. Tämä mahdollistaa tapahtumatiedon hyödyntämisen osana linkitettyä dataa, digitaalisia tuotepasseja ja laajempia semanttisia tietoverkkoja.

EPCIS määrittelee tapahtumatiedon hallintaan kaksi standardoitua rajapintaa. Capture-rajapinta kuvaa, miten tapahtumat tallennetaan EPCIS-tietovarastoon eri tietolähteistä, kuten RFID-lukijoista, viivakoodinluennasta tai muista tietojärjestelmistä, samalla kun tapahtumat rikastetaan liiketoimintakontekstilla. Query-rajapinta puolestaan määrittelee, miten tallennettua tapahtumatietoa voidaan hakea joko kysyntäperusteisesti tai jatkuvien tilausten avulla. Tämä lähestymistapa poikkeaa perinteisestä EDI-mallista, jossa tiedonvälitys perustuu ennalta määriteltyihin sanomiin ja rajalliseen määrään prosessipisteitä, ja mahdollistaa yksityiskohtaisemman tapahtumatiedon keräämisen ilman, että kaikkea tietoa tarvitsee jakaa jatkuvasti kaikille osapuolille.

EPCIS-tapahtumien yhteentoimivuus ei perustu ainoastaan tiedon rakenteeseen, vaan myös yhteisesti sovittuun käsitteistöön. Tätä varten GS1 on määritellyt Core Business Vocabularyn, joka yhdenmukaistaa tapahtumien tyypit, liiketoimintavaiheet, sijaintikäsitteet ja muut keskeiset attribuutit. CBV varmistaa, että eri toimijat tulkitsevat EPCIS-tapahtumat samalla tavalla riippumatta siitä, missä järjestelmässä tai missä teknisessä formaatissa tieto esitetään. Ilman yhteistä sanastoa rakenteellinen yhdenmukaisuus ei yksin riittäisi takaamaan tapahtumatiedon semanttista yhteentoimivuutta.

Kokonaisuutena EPCIS ja Core Business Vocabulary muodostavat yhdessä Peppol- ja UBL-pohjaisten sanomaratkaisujen kanssa perustan tapahtumatiedon yhteentoimivalle hallinnalle toimitusketjuissa. Lähestymistapa erottaa liiketoimintatransaktiot ja niihin liittyvän tapahtumatiedon toisistaan, mutta mahdollistaa niiden teknisen yhdistämisen standardoitujen rajapintojen ja tietomallien kautta. Tämä on keskeinen edellytys toimitusketjujen läpinäkyvyydelle ja analysoitavuudelle erityisesti ympäristöissä, joissa tuotteiden elinkaaret ovat pitkiä ja toimijaverkostot monimutkaisia.

### 2.2 Toimintaympäristön tunnistetut haasteet tapahtumatiedon jakamisen osalta

Rakennus- ja rakennustuoteteollisuudessa on tunnistettu, että GLN-tunnusten systemaattinen käyttö toimitusprosessien eri osapuolten yksiselitteiseen tunnistamiseen ei ole vakiintunut. Tämä korostuu erityisesti EDI-pohjaisessa tiedonvaihdossa, jossa osapuolitiedot esitetään usein epäyhtenäisillä tai tapauskohtaisilla tunnisteilla, vaikka GS1-määritykset edellyttävät GLN-tunnusten käyttöä osapuolten standardoidussa tunnistamisessa. GLN-tunnusten puutteellinen hyödyntäminen heikentää suoraan EPCIS-tapahtumatiedon yhteentoimivuutta, sillä EPCIS-mallissa tapahtumat kytkeytyvät toimijoihin ja sijainteihin nimenomaan standardoitujen tunnisteiden kautta. Ilman GLN-pohjaista osapuolitunnistusta EPCIS-tapahtumien luotettava yhdistäminen toimitusketjun eri toimijoiden välillä vaikeutuu, mikä rajoittaa tapahtumatiedon jäljitettävyyttä, analysoitavuutta ja uudelleenkäytettävyyttä toimitusketjun yli.


## 3. Pohdintaa CBV-standardin soveltamisesta tilauksesta suunniteltavien rakennustuotteiden toimitusketjussa

Rakennusteollisuuden alla toimivassa BETK-työryhmässä on tutkittu CBV-tietokenttiä ja pyrkinyt tunnistamaan sekä mäppäämään olemassa olevia CBV Business step ja disposition tietosisältöjä tilauksesta suunniteltavien rakennustuotteiden (mm. betonielementtit) toimitusketjun tarpeita varten. Rakennus- ja rakennustuoteteollisuuden prosesseissa hyödynnetään jonkin verran vakioimattomia statustieto sisältöjä, mm suunnittelu- ja tuotantovaiheessa kuvaamaan prosessin vaiheita tuotekeskeisestä näkökulmasta. 

<img height="400" alt="EPCIS_vaihe_kuva1" src="https://github.com/user-attachments/assets/76e8572e-8050-4993-acf6-d83ac73c5cab" />
<img height="400" alt="EPCIS_vaihe_kuva2" src="https://github.com/user-attachments/assets/bd2aa069-c152-45fe-842f-afe1f222a9ee" />
<img height="400" alt="EPCIS_vaihe_kuva3" src="https://github.com/user-attachments/assets/0b2bb02b-0ca7-4e92-b8f6-e9207cc142b5" />
<img height="400" alt="EPCIS_vaihe_kuva4" src="https://github.com/user-attachments/assets/df209a45-f4a6-497a-bf6b-3b62ba7d42c3" />
<img height="400" alt="EPCIS_vaihe_kuva5" src="https://github.com/user-attachments/assets/3d0f2429-6206-4e29-b700-1982857dcb58" />
<img height="400" alt="EPCIS_vaihe_kuva6" src="https://github.com/user-attachments/assets/7c1d495e-c1d5-4e96-9c73-1afefa449a05" />
<img height="400" alt="EPCIS_vaihe_kuva7" src="https://github.com/user-attachments/assets/45a3d722-37ab-4d05-a19b-5e4e0ec69194" />
<img height="400" alt="EPCIS_vaihe_kuva8" src="https://github.com/user-attachments/assets/ac006553-80e2-4625-8870-7223103eddc7" />
<img height="400" alt="EPCIS_vaihe_kuva9" src="https://github.com/user-attachments/assets/e8b47ac9-02c8-432b-847d-fe27ae0f16d0" />

### 3.1 Suunnitteluvaihe

GS1 CBV standardi ei nykyhetkellä sisällä vakioitua tietosisältöä suunnitteluvaiheen tapahtumista (statustieto), mitä hyödynnetään ja välitetään rakennusalalla tuotannonohjauksessa. Tunnistettuja vakiointi tarpeita CBV tietokenttien osalta on tunnistettu alla olevassa taulukossa.

<html>
<table>
    <tr>
        <th></th>
        <th></th>
        <th></th>
        <th COLSPAN ="2">EHDOTUS YHDISTELMÄKSI</th>
        <th COLSPAN ="2">OLEMASSA OLEVAT MAHDOLLISET</th>
        <th COLSPAN ="2">MAHDOLLISET LISÄYKSET EPCIS</th>
    </tr>
    <tr>
        <td>Liiketoimintavaihe</td>
        <td>Tapahtuma</td>
        <td>Käyttötarkoitus</td>
        <td>Business Step</td>
        <td>Dispositio</td>
        <td>CBV-Business Step</td>
        <td>CBV-Disposition</td>
        <td>Business</td>
        <td>Disposition</td>
        <td>Kommentti</td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Suunnittelu</td>
        <td>Odottaa lähtötietoja</td>
        <td>Pääurakoitsijalle tieto, että suunnittelijalta puuttuu jotain. </td>
        <td>designing</td>
        <td>awaiting_information</td>
        <td></td>
        <td>0</td>
        <td>communication, designing</td>
        <td>awaiting_information</td>
        <td></td>
    </tr>
    <tr>
        <td>Suunnittelu</td>
        <td>Lähtötiedot vastaanotettu</td>
        <td>Pääurakoitsijalle tieto, että suunnittelijalla kaikki ok.</td>
        <td>designing</td>
        <td>information_received</td>
        <td>0</td>
        <td>0</td>
        <td>communication, designing</td>
        <td>information_received</td>
        <td></td>
    </tr>
    <tr>
        <td>Suunnittelu</td>
        <td>Suunnittelu käynnissä</td>
        <td>Tilannekuva.</td>
        <td>designing</td>
        <td>in_progress</td>
        <td>0</td>
        <td>in_progress</td>
        <td>designing</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Suunnittelu</td>
        <td>Suunnitteluvaihe valmis </td>
        <td>Tieto muille suunnittelualoille, että työn voi aloittaa. Tilannekuva. </td>
        <td>designing</td>
        <td>available</td>
        <td>0</td>
        <td></td>
        <td>designing</td>
        <td>approved</td>
        <td></td>
    </tr>
    <tr>
        <td>Suunnittelu</td>
        <td>Suunnitelma valmis</td>
        <td>Tilannekuva. </td>
        <td>designing</td>
        <td>completed</td>
        <td>staging_outbound</td>
        <td>active,available</td>
        <td>designing</td>
        <td>completed</td>
        <td></td>
    </tr>
    <tr>
        <td>Suunnittelu</td>
        <td>Suunnitelma tarkastettu ja julkaistu</td>
        <td>Tilannekuva. </td>
        <td>designing</td>
        <td>conformant</td>
        <td>departing</td>
        <td>available</td>
        <td>designing</td>
        <td>completed</td>
        <td></td>
    </tr>
    <tr>
        <td>Suunnittelu</td>
        <td>Suunnitelma muutos käsittelyssä</td>
        <td>Tilannekuva. </td>
        <td>design_change</td>
        <td>in_progress</td>
        <td>holding</td>
        <td>in_progress</td>
        <td>designing_change</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Suunnittelu</td>
        <td>Suunnitelma muutos valmis</td>
        <td>Tilannekuva. </td>
        <td>design_change</td>
        <td>completed</td>
        <td>0</td>
        <td>conformant</td>
        <td>designing_change</td>
        <td>completed</td>
        <td></td>
    </tr>
    <tr>
        <td>Suunnittelu/Tuotevalmistus</td>
        <td>Elementin GUID tai SGTIN poistetaan</td>
        <td>Oleellinen tieto järjestelmien toiminnalle. Tieto, että täytyy luoda uusi ja välittää se. </td>
        <td>decommissioning</td>
        <td>inactive</td>
        <td>decommissioning</td>
        <td>inactive</td>
        <td></td>
        <td></td>
        <td>Ei välttämättä pakollinen</td>
    </tr>
</table>
</html>



---


### 3.2 Tuotevalmistus


<html>
<table>
    <tr>
        <th></th>
        <th></th>
        <th></th>
        <th COLSPAN ="2">EHDOTUS YHDISTELMÄKSI</th>
        <th COLSPAN ="2">OLEMASSA OLEVAT MAHDOLLISET</th>
        <th COLSPAN ="2">MAHDOLLISET LISÄYKSET EPCIS</th>
    </tr>
    <tr>
        <td>Liiketoimintavaihe</td>
        <td>Tapahtuma</td>
        <td>Käyttötarkoitus</td>
        <td>Business Step</td>
        <td>Dispositio</td>
        <td>CBV-Business Step</td>
        <td>CBV-Disposition</td>
        <td>Business</td>
        <td>Disposition</td>
        <td>Kommentti</td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Odottaa suunnitelmia (lähtötietoja)</td>
        <td>Tieto suunnittelijalle, että suunnitelmat eivät ole saapuneet. Tilannekuva. </td>
        <td>producing</td>
        <td>awaiting_information</td>
        <td></td>
        <td>0</td>
        <td>communication</td>
        <td>awaiting_information</td>
        <td>Yhdistelmät katsottava järkevästi, tietty biz-step toimii vain tietyn disposition kanssa.</td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Suunnitelmat vastaanotettu</td>
        <td>Tilannekuva. Suunnittelijan aikataulussa pysyminen. </td>
        <td>producing</td>
        <td>information_received</td>
        <td>arriving, (receiving)</td>
        <td>available</td>
        <td>communication</td>
        <td>information_received</td>
        <td>Yhdistelmät katsottava järkevästi, tietty biz-step toimii vain tietyn disposition kanssa.</td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Suunnitelmat hylätty</td>
        <td>Tieto suunnittelijalle ja pääurakoitsijalle, että muutoksia tarvitaan. </td>
        <td> producing</td>
        <td>information_rejected</td>
        <td>arriving</td>
        <td>returned</td>
        <td></td>
        <td>rejected</td>
        <td>Yhdistelmät katsottava järkevästi, tietty biz-step toimii vain tietyn disposition kanssa.</td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Suunnitelma lukittu, elementti ohjelmoitu valuun.</td>
        <td>Tieto pääurakoitsijalle, että toimituspäivä vahvistettu. </td>
        <td>accepting</td>
        <td>information_received</td>
        <td>accepting, (receiving)</td>
        <td>conformant</td>
        <td></td>
        <td></td>
        <td>Yhdistelmät katsottava järkevästi, tietty biz-step toimii vain tietyn disposition kanssa.</td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Elementti saanut SGTINin yksilöivän tunnuksen</td>
        <td>Tilannekuva.</td>
        <td>commissioning</td>
        <td>active</td>
        <td>commissioning, (creating_class_instance)</td>
        <td>active</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Valmistuskiellossa</td>
        <td>Tilannekuva. Häiriötieto.</td>
        <td>holding, error</td>
        <td>unavailable</td>
        <td>holding</td>
        <td>unavailable, (recalled)</td>
        <td></td>
        <td></td>
        <td>Tämä erikseen vai poikkeama eristyksen  kautta?</td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Valmistus aloitettu</td>
        <td>Tieto pääurakoitsijalle, että työ etenee.</td>
        <td>producing</td>
        <td>in_progress</td>
        <td>0</td>
        <td>in_progress</td>
        <td>producing</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Valmistettu</td>
        <td>Tilannekuva. Valmistajan laskutusperuste. </td>
        <td>producing</td>
        <td>available</td>
        <td>0</td>
        <td>available</td>
        <td>producing</td>
        <td>completed</td>
        <td></td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Laatutarkastettu ja hyväksytty (tehtaan laatutarkastus)</td>
        <td>Tilannekuva. </td>
        <td>inspecting</td>
        <td>conformant</td>
        <td>inspecting</td>
        <td>conformant, (available, active)</td>
        <td></td>
        <td>under_quality_control</td>
        <td></td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Valmis toimitettavaksi</td>
        <td></td>
        <td>staging_outbound</td>
        <td>available</td>
        <td>dispensing, staging_outbound, stocking</td>
        <td>available</td>
        <td></td>
        <td>ready_for shipping</td>
        <td></td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Kotiinkutsuttu työmaalle</td>
        <td></td>
        <td>shipping</td>
        <td>requested</td>
        <td>other</td>
        <td>0</td>
        <td>ordering, scheduling</td>
        <td>requested</td>
        <td></td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Kuormatunnus (SSCC) luotu</td>
        <td></td>
        <td>creating_class_instance</td>
        <td>active</td>
        <td>creating_class_instance</td>
        <td>active</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Toimituspäivä vahvistettu</td>
        <td></td>
        <td>shipping</td>
        <td>scheduled</td>
        <td>schedule, other</td>
        <td>0</td>
        <td>ordering, scheduling</td>
        <td>confirmed</td>
        <td></td>
    </tr>
    <tr>
        <td>Tuotevalmistus</td>
        <td>Lähetetty</td>
        <td></td>
        <td></td>
        <td></td>
        <td>departing</td>
        <td>in_transit</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
</table>

---


### 3.3 Tiedonkantaja

<html>
<table>
    <tr>
        <th></th>
        <th></th>
        <th></th>
        <th COLSPAN ="2">EHDOTUS YHDISTELMÄKSI</th>
        <th COLSPAN ="2">OLEMASSA OLEVAT MAHDOLLISET</th>
        <th COLSPAN ="2">MAHDOLLISET LISÄYKSET EPCIS</th>
    </tr>
    <tr>
        <td>Liiketoimintavaihe</td>
        <td>Tapahtuma</td>
        <td>Käyttötarkoitus</td>
        <td>Business Step</td>
        <td>Dispositio</td>
        <td>CBV-Business Step</td>
        <td>CBV-Disposition</td>
        <td>Business</td>
        <td>Disposition</td>
        <td>Kommentti</td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Data Carrier</td>
        <td>Odottaa tietoja tunnisteen ohjelmointia varten.</td>
        <td></td>
        <td>encoding</td>
        <td>in_progress</td>
        <td>encoding</td>
        <td></td>
        <td></td>
        <td>awaiting_information</td>
        <td>Ei välttämättä pakollinen</td>
    </tr>
    <tr>
        <td>Data Carrier</td>
        <td>Tunniste on ohjelmoitu tagille.</td>
        <td>Tilannetta varten, jossa tunniste koodataan tagille ennen tagin liittämistä tuotteeseen. Mahdollisesti kolmas osapuoli tekee. </td>
        <td>encoding</td>
        <td>encoded</td>
        <td>encoding</td>
        <td>encoded</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Data Carrier</td>
        <td>Tunniste on toiminnassa ja liitetty tuotteeseen.</td>
        <td></td>
        <td>encoding</td>
        <td>active</td>
        <td>encoding</td>
        <td>active</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Data Carrier</td>
        <td>Tunniste on deaktivoitu (kill-komento suoritettu).</td>
        <td></td>
        <td>killing</td>
        <td>deactivated</td>
        <td>killing</td>
        <td>deactivated</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Data Carrier</td>
        <td>Tunniste on pysyvästi poistettu käytöstä.</td>
        <td></td>
        <td>killing</td>
        <td>destroyed</td>
        <td>killing</td>
        <td>destroyed</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
</table>
</html>

---


### 3.4 Kuljetus

<html>
<table>
    <tr>
        <th></th>
        <th></th>
        <th></th>
        <th COLSPAN ="2">EHDOTUS YHDISTELMÄKSI</th>
        <th COLSPAN ="2">OLEMASSA OLEVAT MAHDOLLISET</th>
        <th COLSPAN ="2">MAHDOLLISET LISÄYKSET EPCIS</th>
    </tr>
    <tr>
        <td>Liiketoimintavaihe</td>
        <td>Tapahtuma</td>
        <td>Käyttötarkoitus</td>
        <td>Business Step</td>
        <td>Dispositio</td>
        <td>CBV-Business Step</td>
        <td>CBV-Disposition</td>
        <td>Business</td>
        <td>Disposition</td>
        <td>Kommentti</td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr
        <tr>
        <td>Kuljetus</td>
        <td>Kuormattu</td>
        <td></td>
        <td>loading</td>
        <td>available </td>
        <td>loading</td>
        <td>available, in_transit, container_closed</td>
        <td></td>
        <td></td>
        <td>Liitetään SSCC:hen</td>
    </tr>
    <tr>
        <td>Kuljetus</td>
        <td>Lähtenyt työmaalle</td>
        <td></td>
        <td>departing</td>
        <td>in_transit</td>
        <td>departing, shipping,trasnporting</td>
        <td>in_transit</td>
        <td></td>
        <td></td>
        <td>Liitetään SSCC:hen</td>
    </tr>
    <tr>
        <td>Kuljetus</td>
        <td>Saapunut työmaalle</td>
        <td>Kuorman saapumisaika. Voidaan verrata tilattuun. </td>
        <td>arriving</td>
        <td>available </td>
        <td>arriving, receiving*, accepting,transporting</td>
        <td></td>
        <td></td>
        <td></td>
        <td>Liitetään SSCC:hen</td>
    </tr>
    <tr>
        <td>Kuljetus</td>
        <td>Purku aloitettu</td>
        <td>Purun aloitus. Nähdään onko myöhää, ja kirjauksilla käsiksi venttojen syihin. </td>
        <td>unloading</td>
        <td>in_progress</td>
        <td>unloading</td>
        <td>in_progress</td>
        <td></td>
        <td></td>
        <td>Liitetään SSCC:hen</td>
    </tr>
    <tr>
        <td>Kuljetus</td>
        <td>Purku lopetettu</td>
        <td>Purun kesto. </td>
        <td>unloading</td>
        <td>available</td>
        <td>unloading</td>
        <td>available</td>
        <td></td>
        <td>completed</td>
        <td>Liitetään SSCC:hen</td>
    </tr>
</table>
</html>

 ---


### 3.5 Työmaa

<html>
<table>
    <tr>
        <th></th>
        <th></th>
        <th></th>
        <th COLSPAN ="2">EHDOTUS YHDISTELMÄKSI</th>
        <th COLSPAN ="2">OLEMASSA OLEVAT MAHDOLLISET</th>
        <th COLSPAN ="2">MAHDOLLISET LISÄYKSET EPCIS</th>
    </tr>
    <tr>
        <td>Liiketoimintavaihe</td>
        <td>Tapahtuma</td>
        <td>Käyttötarkoitus</td>
        <td>Business Step</td>
        <td>Dispositio</td>
        <td>CBV-Business Step</td>
        <td>CBV-Disposition</td>
        <td>Business</td>
        <td>Disposition</td>
        <td>Kommentti</td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr
<tr>
        <td>Työmaa</td>
        <td>Kuorma puutteellinen</td>
        <td></td>
        <td>void_shipping</td>
        <td>mismatch_instance</td>
        <td>void_shipping</td>
        <td>mismatch_instance</td>
        <td></td>
        <td></td>
        <td>Onko tarpeellinen, vai poikkeaman kautta. </td>
    </tr>
    <tr>
        <td>Työmaa</td>
        <td>Kuorma täydellinen</td>
        <td></td>
        <td>inspecting</td>
        <td>completeness_verified</td>
        <td>inspecting</td>
        <td>completeness_verified</td>
        <td></td>
        <td></td>
        <td>Onko tarpeellinen, vai vastanottotarkastuksesta. </td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Työmaa</td>
        <td>Vastaanotettu (vastaanottotarkastus)</td>
        <td>Valmistajan laskutusperuste. </td>
        <td>accepting</td>
        <td>conformant</td>
        <td>receiving, accepting</td>
        <td>available</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Työmaa</td>
        <td>Varastoitu ei käytettävissä</td>
        <td>Seuraavan lohkon asennusedellytykset. </td>
        <td>storing</td>
        <td>unavailable</td>
        <td>storing, stocking</td>
        <td>unavailable, (sellable_not_accessible)</td>
        <td></td>
        <td></td>
        <td>Tarvitseeko erikseen? Poikkeaman alalaji.</td>
    </tr>
    <tr>
        <td>Työmaa</td>
        <td>Varastoitu käytettävissä</td>
        <td></td>
        <td>storing </td>
        <td>available</td>
        <td>storing, stocking</td>
        <td>available, sellable_accessible</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Työmaa</td>
        <td>Asennus aloitettu</td>
        <td>Asennuksen kesto.</td>
        <td>installing</td>
        <td>in_progress</td>
        <td>installing</td>
        <td>in_progress</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Työmaa</td>
        <td>Asennus lopetettu</td>
        <td>Asennuksen kesto.</td>
        <td>installing</td>
        <td>available</td>
        <td>installing</td>
        <td>available</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Työmaa</td>
        <td>Betonielementti valettu</td>
        <td>Tieto suunnitteluun. Tönäreiden poisto ja muottien purku. </td>
        <td>casting</td>
        <td>available</td>
        <td>(assembling)</td>
        <td>available</td>
        <td>casting</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Työmaa</td>
        <td>Laatutarkastettu ja hyväksytty (työmaan asennustarkastus)</td>
        <td></td>
        <td>inspecting</td>
        <td>conformant</td>
        <td>inspecting</td>
        <td>conformant</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
</table>
</html>

  ---


### 3.6 Poikkeama

<html>
<table>
    <tr>
        <th></th>
        <th></th>
        <th></th>
        <th COLSPAN ="2">EHDOTUS YHDISTELMÄKSI</th>
        <th COLSPAN ="2">OLEMASSA OLEVAT MAHDOLLISET</th>
        <th COLSPAN ="2">MAHDOLLISET LISÄYKSET EPCIS</th>
    </tr>
    <tr>
        <td>Liiketoimintavaihe</td>
        <td>Tapahtuma</td>
        <td>Käyttötarkoitus</td>
        <td>Business Step</td>
        <td>Dispositio</td>
        <td>CBV-Business Step</td>
        <td>CBV-Disposition</td>
        <td>Business</td>
        <td>Disposition</td>
        <td>Kommentti</td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>POIKKEAMA</td>
        <td>Poikkeama havaittu</td>
        <td></td>
        <td>inspecting, error</td>
        <td>non_conformant</td>
        <td>inspecting</td>
        <td>non_conformant</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>POIKKEAMA</td>
        <td>Poikkeama käsittelyssä</td>
        <td>Toimenpiteitä vaaditaan. </td>
        <td>error</td>
        <td>in_progress</td>
        <td></td>
        <td>in_progress//non_conformant, unavailable</td>
        <td>error</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>POIKKEAMA</td>
        <td>Poikkeama valmis</td>
        <td></td>
        <td>error, inspecting</td>
        <td>completed, available,conformant</td>
        <td>0</td>
        <td>available//conformant</td>
        <td>error</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>POIKKEAMA</td>
        <td>Eristetty jatkokäsittelyyn</td>
        <td></td>
        <td>error, holding</td>
        <td>unavailable</td>
        <td>holding</td>
        <td>unavailable</td>
        <td>error</td>
        <td></td>
        <td>onko tarve tälle erikseen</td>
    </tr>
    <tr>
        <td>POIKKEAMA</td>
        <td>Hylätty, poistettu käytöstä.</td>
        <td></td>
        <td>error, removing</td>
        <td>disposed</td>
        <td>0</td>
        <td>need_replacement, disposed</td>
        <td>error</td>
        <td>scrapped</td>
        <td>onko tarve erikseen. Nyt tuplana myös huolto. </td>
    </tr>
    <tr>
        <td>POIKKEAMA</td>
        <td>Vaurioitunut</td>
        <td></td>
        <td>error</td>
        <td>damaged</td>
        <td>inspecting</td>
        <td>damaged</td>
        <td></td>
        <td></td>
        <td>onko tälle tarve erikseen, vain yksi poikkeaman alalaji. Kuitenkin täytyy olla jokin toinen keino jakaa muu poikkeamatieto. </td>
    </tr>
    <tr>
        <td>POIKKEAMA</td>
        <td>Palautettu</td>
        <td></td>
        <td>error, receiving</td>
        <td>returned</td>
        <td>departing,receiving, shipping</td>
        <td>returned</td>
        <td>returned</td>
        <td></td>
        <td>onko tälle tarve erikseen, vain yksi poikkeaman alalaji. Kuitenkin täytyy olla jokin toinen keino jakaa muu poikkeamatieto.</td>
    </tr>
</table>
</html>

 ---


### 3.7 Ylläpito & elinkaari

<html>
<table>
    <tr>
        <th></th>
        <th></th>
        <th></th>
        <th COLSPAN ="2">EHDOTUS YHDISTELMÄKSI</th>
        <th COLSPAN ="2">OLEMASSA OLEVAT MAHDOLLISET</th>
        <th COLSPAN ="2">MAHDOLLISET LISÄYKSET EPCIS</th>
    </tr>
    <tr>
        <td>Liiketoimintavaihe</td>
        <td>Tapahtuma</td>
        <td>Käyttötarkoitus</td>
        <td>Business Step</td>
        <td>Dispositio</td>
        <td>CBV-Business Step</td>
        <td>CBV-Disposition</td>
        <td>Business</td>
        <td>Disposition</td>
        <td>Kommentti</td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr
  <tr>
        <td>Käytönaikaiset</td>
        <td>Odottaa lähtötietoja ennen huoltotoimenpiteitä.</td>
        <td></td>
        <td>repairing</td>
        <td>awaiting_information</td>
        <td>holding</td>
        <td>in_progress</td>
        <td>maintenance, communication</td>
        <td>awaiting_information</td>
        <td></td>
    </tr>
    <tr>
        <td>Käytönaikaiset</td>
        <td>Huoltoaikataulutettu.</td>
        <td></td>
        <td>repairing</td>
        <td>scheduled</td>
        <td>0</td>
        <td>0</td>
        <td>maintenance, scheduling</td>
        <td>scheduled</td>
        <td></td>
    </tr>
    <tr>
        <td>Käytönaikaiset</td>
        <td>Huolto käynnissä</td>
        <td></td>
        <td>repairing</td>
        <td>in_progress</td>
        <td>repairing</td>
        <td>unavailable</td>
        <td>maintenance</td>
        <td>in_progress</td>
        <td></td>
    </tr>
    <tr>
        <td>Käytönaikaiset</td>
        <td>Tuote korjattu</td>
        <td></td>
        <td>repairing</td>
        <td>conformant</td>
        <td>0</td>
        <td>available, conformant</td>
        <td>maintenance</td>
        <td>operational</td>
        <td></td>
    </tr>
    <tr>
        <td>Käytönaikaiset</td>
        <td>Tuote vaatii korjausta</td>
        <td></td>
        <td>repairing, inspecting</td>
        <td>non_conformant</td>
        <td>repairing</td>
        <td>non_conformant</td>
        <td>maintenance</td>
        <td>requires_repair</td>
        <td>Olisiko poikkeaman kautta?</td>
    </tr>
    <tr>
        <td>Elinkaaren loppu</td>
        <td>Poistetaan käytöstä.</td>
        <td></td>
        <td>removing</td>
        <td>disposed</td>
        <td>removing</td>
        <td>disposed</td>
        <td></td>
        <td>end_of_life</td>
        <td></td>
    </tr>
    <tr>
        <td>Elinkaaren loppu</td>
        <td>Purettu kokonaisena</td>
        <td></td>
        <td>removing, disassembling</td>
        <td>available</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Elinkaaren loppu</td>
        <td>Kierrätetty uudelleenkäyttöön. </td>
        <td></td>
        <td>collecting</td>
        <td>re_used</td>
        <td></td>
        <td>conformant</td>
        <td></td>
        <td>re_used</td>
        <td></td>
    </tr>
    <tr>
        <td>Elinkaaren loppu</td>
        <td>Kierrätetty materiaalina. </td>
        <td></td>
        <td>collecting</td>
        <td>recycled</td>
        <td></td>
        <td></td>
        <td></td>
        <td>recycled</td>
        <td></td>
    </tr>
    <tr>
        <td>Elinkaaren loppu</td>
        <td>Hävitetty</td>
        <td></td>
        <td>destroying</td>
        <td>destroyed</td>
        <td>destroying</td>
        <td>destroyed</td>
        <td></td>
        <td>disposed</td>
        <td></td>
    </tr>
</table>
</html>

---

## 4. Rakennusalan erityistarpeisiin kohdistuvat CBV-statuslisäykset

<table>
    <tr>
        <td><b>Business step</b></td>
        <td><b>Definition</b></td>
        <td><b>Example of use</b></td>
        <td><b>Comment</b></td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>designing</td>
        <td>Business-process of designing a product. </td>
        <td>An item instance is defined by initial data. Design process takes place before selecting or producing the produt. </td>
        <td></td>
    </tr>
    <tr>
        <td>design_change</td>
        <td>Denotes a specific activity within business process where a change in an already completed and published design/plan is in the making. </td>
        <td>In the producing process it is noticed that the original design/plan needs to be updated, so a request for update is made and and the update is in the making. </td>
        <td></td>
    </tr>
    <tr>
        <td>producing</td>
        <td>Denotes a specific activity within business process where a product is produced. Either from raw materials or other products. Can not be afterwards disassembled to identifiable products as in the business step: assembled. </td>
        <td>In excample concrete elements. </td>
        <td></td>
    </tr>
    <tr>
        <td>error</td>
        <td>Denotes a business process where error takes place and actions are made to solve it. Could happen in any stage of the supplychain.</td>
        <td>The surface of the concrete element does not match the quality requirements. The main process flow continues and the element is installed in place. The repair is scheduled and will be done later. <br></td>
        <td>Product can have an error that needs to be addressed and thus informed to other parties, but the type of the error can be such that it doesn&#39;t interfere the current business process flow. For that reason a minor error that will be addressed later cannot be expressed through disposition, because disposition is needed to express the completeness of particular biz step. Other option is that only major flow-interfering errors are expressed via dispositions.  If the expression of error is done in business step. The phase where error took place should be identifiable via the previous EPCIS information. </td>
    </tr>
    <tr>
        <td>casting</td>
        <td>A group of products is attached to each other. The attached products do not form a new item instance. </td>
        <td>Eg. Casting of concrete elements. </td>
        <td>Optional existing business step: assembling. Note: the disassembling is not so straightforward as in other cases.</td>
    </tr>
    <tr>
        <td>maintenance</td>
        <td>Denotes a business process where the maintenance or repair takes place either via scheduling or observing a faulty. </td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td></td>
        <td>The maintenance describes a larger set of operations than other business steps. But it might be hard to express unambiguously with the existing biz steps and dispositions. Check the list related to maintenance phase, made in BETK-project. </td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>recycling</td>
        <td>Denotes a specific activity where a product is collected to recycling not destroying. </td>
        <td>Concrete element is disassembled from a building and it is recycled either as a material or reused as a whole.</td>
        <td>Optional existing business step: collecting. IF collecting is used then there is a need for new disposition(s). Expressing through dispositions preferred way. </td>
    </tr>
    <tr>
        <td>communication</td>
        <td>Denotes a phase in between/on top of business processes where information related to product is exchanged between parties. </td>
        <td>Faulty product is due to repair, but is waiting guide/plan.</td>
        <td>Optional also expressable via new CBV dispositions (dispositions being the preferred way). </td>
    </tr>
 </table>

 <table>
   <tr>
        <td><b>Disposition</b></td>
        <td><b>Definition</b></td>
        <td><b>Example of use</b></td>
        <td><b>Comment</b></td>
    </tr>
     <tr>
        <td><b></b></td>
        <td><b></b></td>
        <td><b></b></td>
        <td><b></b></td>
    </tr>
    <tr>
        <td>awaiting_information</td>
        <td>The business step/process can not proceed until more information is provided. </td>
        <td>The produce line has not yet got the design plans for production.</td>
        <td></td>
    </tr>
    <tr>
        <td>information_received</td>
        <td>The information needed to proceed in the business step/process is received but the no actions has been made yet. </td>
        <td>The factory has received the plans for the product, but has not inspected them yet nor started the production. </td>
        <td></td>
    </tr>
    <tr>
        <td>information_rejected</td>
        <td>The information received is not applicable, can not proceed.</td>
        <td>The factory has received the plans for the product and noted that the plan is not feasible. The plan is returned for the designer for updates.</td>
        <td></td>
    </tr>
    <tr>
        <td>completed</td>
        <td>Another &quot;business step completed&quot; value in addition to &quot;available&quot; in case there are phases in the same business process. </td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>rejected</td>
        <td>Product or information related to product is rejected after receiving</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>requested</td>
        <td>The business step in case is requested to be done. </td>
        <td>The repair or shipping of the product is requested.</td>
        <td></td>
    </tr>
    <tr>
        <td>scheduled</td>
        <td>The business step in case is scheduled. </td>
        <td>The repair or shipping of the product is scheduled.</td>
        <td></td>
    </tr>
    <tr>
        <td>recycled</td>
        <td>The product is recycled as part of the business step collecting (if the new biz step is introduced recycling)</td>
        <td>The concrete element is disassembled from a building and destroyed to pieces, then transported to waste center.</td>
        <td></td>
    </tr>
    <tr>
        <td>re_used</td>
        <td>The product is reused as part of the business step collecting (if the new biz step is introduced recycling)</td>
        <td>The concrete element is disassembled from a building as a whole and re used in another building. </td>
        <td></td>
    </tr>
    <tr>
        <td>error critical</td>
        <td>Critical error related to product is detected. The process cannot proceed until further action is taken.</td>
        <td>The concrete element has damaged so badly that it cannot be lifted safely. Repair or change is needed before installation can proceed.  </td>
        <td></td>
    </tr>
    <tr>
        <td>error_in_progress</td>
        <td>Error is being handled. </td>
        <td>Actions are made to solve the error. For example repair is scheduled.</td>
        <td></td>
    </tr>
</table>










# 🇫🇮 Tapahtumatiedon jakaminen GS1 EPCIS toimitusketjuhallinta standardin mukaan 
:building_construction::articulated_lorry:
Lähdeaineistot:
1. [EPCIS Sandbox](https://epcis-sandbox.gs1.org/)
2. [EPCIS Standard](https://ref.gs1.org/standards/epcis/)
3. [EPCIS and CBV Implementation Guideline](https://www.gs1.org/docs/epc/EPCIS_Guideline.pdf)
4. [Core Business Vocabulary (CBV) Standard](https://ref.gs1.org/standards/cbv/)
5. [Launch](https://www.gs1.org/docs/epcis/epcis_2-0_launch.pdf)

