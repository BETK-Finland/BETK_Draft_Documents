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
1. [Dokumentin tarkoitus](#dokumentin-tarkoitus)<br>
1. 
---

## 1. Johdanto

Tämä dokumentti on BETK-työryhmän keskustelupaperi, jonka tavoitteena on jäsentää ja koota havaintoja, tunnistettuja ongelmia ja kehityssuuntia tapahtumatiedon jakamiseen liittyen ja toimii mahdollisen toimialakohtaisen soveltamisohjeen lähtökohtana. Dokumentti ei ole normi, standardi eikä valmis ohje, vaan tarkoitettu yhteisen ymmärryksen rakentamiseen ja jatkokehityksen tueksi. Se kytkeytyy Rakennusteollisuus RT:n käynnissä olevaan rakennustuotetiedon ja toimitusketjujen digitalisaatiotyöhön, jossa pyritään siirtymään manuaalisesta ja rakenteettomasta tiedonvaihdosta kohti rakenteellista ja koneluettavaa tiedonhallintaa.

Tämä keskustelupaperi jatkaa BETK-työryhmän aiempaa työtä rakennustuotteiden tuoteyksilöinnin ja -tunnistamisen parissa. Siinä missä julkaistu soveltamisohje keskittyy fyysisten tuotteiden yksilöintiin ja tunnistamiseen, tämän dokumentin painopiste on yksilöityihin tuotteisiin kytkeytyvän tapahtumatiedon muodostumisessa, jakamisessa ja hyödyntämisessä toimitusketjun eri vaiheissa.

2.1 Tuoteyksilöinnin ja -tunnistamisen soveltamisohje
BETK-työryhmä on laatinut ja julkaissut soveltamisohjeen betonielementtien tuoteyksilöintiin ja -tunnistamiseen, mikä toimii tapahtumatiedon jakamisen lähtökohtana. Laadittu soveltamisohje ... menetelmä GS1 standardien soveltamiseen ... (03) GTIN --> (242 MTO Variation number) --> (21) Serial)



## 1. Mitä on tapahtumatiedon jakaminen
Toimitusketjujen kehittämistyössä on tunnistettu merkittävä tarve tuottaa ja jakaa tapahtumatietoa, joka tukee rakennustuotteiden jäljitettävyyttä koko niiden elinkaaren ajan. Tapahtumatiedolla tarkoitetaan tässä yhteydessä rakenteellista tietoa tuotetta koskevista tapahtumista, kuten valmistuksesta, varastoinnista, kuljetuksesta, vastaanotosta, asennuksesta sekä mahdollisesti myös suunnittelun, ylläpidon ja käytön aikaisista toimenpiteistä.

Tapahtumatiedon systemaattinen tuottaminen ja jakaminen mahdollistaa siirtymisen dokumenttipohjaisesta ja jälkikäteisestä tiedonvaihdosta kohti reaaliaikaisempaa ja automaattisesti hyödynnettävää tiedonhallintaa. Erityisesti jäljitettävyyden näkökulmasta tapahtumatieto muodostaa keskeisen mekanismin, jonka avulla voidaan yhdistää tuotteen fyysinen sijainti, tila ja historia sitä koskevaan digitaaliseen tietoon toimitusketjun eri vaiheissa aina tuotevalmistuksesta asennukseen ja edelleen ylläpidon aikaisiin vaiheisiin.

Toimitusketjun kehittämisessä tunnistettuna kehittämistarpeena on todettu tarve tuottaa tapahtumatietoa tuotteen toimitusketjun aikaiseen jäljitettävyyttä tuotevalmistuksesta asennuksen ja ylläpidon aikaiseen vaiheeseen.



Rakenteellisten tilauksesta suunniteltavien runkotuotteiden osalta tapahtumatiedon merkitys korostuu erityisesti asennusvaiheessa, jossa yksilöity fyysinen tuote asennetaan osaksi rakennetta. Rajatuissa piloteissa on havaittu, että asennusvaiheessa tuotteita voidaan vaihtaa keskenään työmaan logististen reunaehtojen tai inhimillisten virheiden seurauksena, jolloin suunniteltu ja toteutunut asennussijainti eivät vastaa toisiaan. Mikäli yksittäisen elementin ominaisuuksissa havaitaan poikkeama, edellyttää tilanteen hallinta kykyä jäljittää kyseinen tuote ja sen todellinen asennussijainti yksiselitteisesti. Ilman rakenteellisesti määriteltyä ja jaettua tapahtumatietoa tuoteyksilöinnin ja toteutuneen asennuksen välinen yhteys voi katketa, mikä heikentää jäljitettävyyttä ja voi muodostaa rakenteellisen turvallisuusriskin. Tämän vuoksi asennussijaintiin kytkeytyvä tapahtumatieto on keskeinen edellytys tilauksesta suunniteltavien runkotuotteiden toimitusketjun luotettavuudelle, riskienhallinnalle ja elinkaaritiedon eheydelle.

### 1.1 GS1 EPCIS

EPC Information Services (EPCIS) -ratkaisu perustuu kahteen standardoituun rajapintaan: Capture ja Query. Capture-rajapinta tallentaa EPCIS-tapahtumat EPCIS-tietovarastoon (EPCIS Repository), joka on pysyvä tietokanta ja jota voidaan käyttää Query-rajapinnan kautta. Standardi ei määrittele, miten tietokanta on toteutettu, vaan ainoastaan rajapinnat tiedon syöttämistä ja hakemista varten. Rajapintoja tarvitaan yhteentoimivuuden varmistamiseksi, kun taas toteutustavat mahdollistavat kilpailun teknologiaa ja EPC Information Service -palveluja tarjoavien toimijoiden välillä. EPCIS-tapahtumat kuvaavat toimitusketjun aikana kertyviä liiketoimintavaiheita, joihin sisältyy tyypillisesti aikaleima, sijainti (GLN) ja tapahtuman tyyppi (esim. pakkaus, lähetys ja vastaanotto). Näihin tapahtumiin voidaan päästä käsiksi organisaation sisällä tai niitä voidaan jakaa kumppaneille todennetun internet-yhteyden kautta. (METROPOLIA LOPPURAPORTTI, 2012)

Capture-rajapinta sijaitsee EPCIS-tietovaraston ja EPCIS-tietoja keräävän sovelluksen (EPCIS Capturing Application) välissä. Keräävä sovellus valvoo alemman tason arkkitehtuurielementtien toimintaa ja tuo liiketoimintakontekstin koordinoimalla muita tietolähteitä, jotka liittyvät tietyn liiketoimintaprosessin vaiheen toteuttamiseen. RFID-tapahtumien lisäksi sovellukset voivat vastaanottaa tietoa myös muista lähteistä (esim. manuaalisesta syötöstä tai viivakoodin luvusta).

EPCIS Query -rajapinta tarjoaa kaksi vuorovaikutustapaa. “On-demand”- tai synkronisessa tilassa asiakas tekee pyynnön EPCIS Query Control Interface -rajapinnan kautta ja saa vastauksen välittömästi. “Standing request”- tai asynkronisessa tilassa asiakas luo tilauksen määräaikaiselle kyselylle. Joka kerta, kun tämä määräaikainen kysely suoritetaan, tulokset toimitetaan asynkronisesti (eli “työnnetään”) vastaanottajalle EPCIS Query Callback Interface -rajapinnan kautta. EPCIS Query Callback Interface -rajapintaa voidaan käyttää myös tiedon toimittamiseen välittömästi tapahtuman tallennuksen yhteydessä ohittaen tietovaraston. (METROPOLIA LOPPURAPORTTI, 2012)

Perinteinen tavaravirtoihin liittyvä EDI-sanomaliikenne perustuu yhdessä määriteltyihin skenaarioihin, jotka laukaisevat lähetys- ja vastaanottoilmoitusten (dispatch advice ja receive advice) lähettämisen. Näitä pisteitä on suhteellisen vähän verrattuna siihen kokonaismäärään käsittelytapahtumia, joita toimitusketjussa tehdään. Yksityiskohtaisemman näkyvyyden toteuttaminen toimitusketjuun ei ole EDI:n avulla kovin käytännöllistä. Suurin osa syntyvästä datasta on hyödyllistä vain erityistilanteissa, ja siihen tulisi päästä käsiksi vain tarvittaessa.

EPC Information Service (EPCIS) on EPC Globalin (GS1:n tytäryhtiö) kehittämä rajapintastandardi. Se määrittelee kaksi yleistä rajapintaa: toisen tiedon keräämistä ja toisen tiedon jakamista varten. Kaikki EPCIS:n käsittelemä data koskee yksilöllisesti tunnistettavia fyysisiä objekteja ja niihin liittyviä fyysisiä tapahtumia. Ytimekkäästi ilmaistuna EPCIS-järjestelmä vastaa kysymyksiin kuka, mitä, missä ja milloin.

EPCIS Capture -rajapinta kerää tunnistetietoa eri lähteistä, kuten RFID-porttien tai viivakoodinlukujen kautta, ja tallentaa ne tietokantaan (EPCIS Repository) yhdessä liiketoimintakontekstin kanssa (esim. pakattu, lähetetty). Tietovaraston tarkka tietokantarakenne ei kuulu standardin määrittelyyn.

Kaikki data haetaan tietovarastosta EPCIS Query -rajapinnan kautta. Tiedonhankinta poikkeaa EDI-mallista siten, että se toimii ensisijaisesti pull-mallilla: dataa pyydetään tietovarastosta silloin, kun sitä tarvitaan, sen sijaan että sitä lähetettäisiin automaattisesti ennalta määritellyissä tilanteissa. EPCIS tukee kuitenkin myös standing request -toiminnallisuutta, joka mahdollistaa EDI:n kaltaisen push-mallin.

Jokainen yritys tai toimipaikka voi ylläpitää omaa EPCIS-tietovarastoaan tai käyttää kolmannen osapuolen tarjoamaa keskitettyä tietovarastoa. Kummassakin tapauksessa pääsy dataan on hallittu asianmukaisilla todennusmenetelmillä, eli kukin osapuoli näkee vain ne tapahtumat, jotka koskevat sitä itseään.

Tulevaisuuden suunnitelmat tiedonsiirron osalta

Asiakkaiden nykyiset sanomavälittäjät kutsuttiin työpajaan 10 esittämään näkemyksensä sanomaliikenteen toteuttamisesta. Sanomavälittäjille esiteltiin asiakkaiden tarpeet yhteisessä tilaisuudessa, jonka projektiryhmä järjesti kaksi viikkoa ennen työpajaa.

Kaksi operaattoria osallistui 17. lokakuuta pidettyyn työpajaan: Itella ja Tieto. Tieto esitteli mahdollisuutta käyttää EDI:tä ja EPCIS:iä rinnakkain mahdollisimman kattavan järjestelmän saavuttamiseksi. EPCIS:n hyödyt tunnistaen Itellan näkemys oli kuitenkin, ettei EPCIS:n käyttöönotto ollut välttämätöntä ja että asiakkaiden välittömät tarpeet voitaisiin täyttää EDI:n avulla.

Itellan näkemys EPCIS:stä sai yleisesti kannatusta osallistujien keskuudessa. Erityisesti vaatimus jokaisen käsiteltävän kollin yksilöllisestä tunnistamisesta nähtiin liian vaikeaksi ja kalliiksi toteuttaa lähitulevaisuudessa. Tämä haaste koskee myös viivakoodien käyttöä eikä ole RFID-teknologiaan sidottu.

Esille tuotiin ehdotus DESADV- ja RECADV-sanomien käytöstä GS1 EANCOM -standardien mukaisesti, mutta sanomien sisällöstä ei saavutettu yksimielisyyttä. Toinen ongelma oli se, etteivät yritykset tällä hetkellä käytä GLN-tunnuksia eri osapuolten tunnistamiseen sanomaliikenteessä, vaikka GS1-määritykset sitä edellyttävät. Sovittiin, että GS1 järjestää projektin jälkeen tapaamisen, jossa kiinnostuneet osapuolet voivat yhdessä määritellä sanomien vähimmäissisällön ja saada lisätietoa GLN-tunnusten käytöstä.
### 1.2 


## 2. Kehittämisen lähtökohdat tapahtumatiedon jakamiselle tilauksesta suunniteltavien rakennustuotteiden toimitusketjussa

### 2.1 Tuoteyksilöinnin ja -tunnistamisen soveltamisohje
BETK-työryhmä on laatinut ja julkaissut soveltamisohjeen betonielementtien tuoteyksilöintiin ja -tunnistamiseen, mikä toimii tapahtumatiedon jakamisen lähtökohtana. Laadittu soveltamisohje ... menetelmä GS1 standardien soveltamiseen ... (03) GTIN --> (242 MTO Variation number) --> (21) Serial)

### 2.2 Toimintaympäristön tunnistetut tarpeet tapahtumatiedon jakamisen osalta

### 2.3 Toimintaympäristön tunnistetut haasteet tapahtumatiedon jakamisen osalta

Rakennus-ja rakennustuoteteollisuudessa yksi tunnistettu ongelmaToinen ongelma on se, etteivät yritykset tällä hetkellä käytä GLN-tunnuksia eri osapuolten tunnistamiseen toimitusprosesseissaan ja EDI-pohjainen tiedonvaihto ...vaikka GS1-määritykset sitä edellyttävät.


EPC Information Services (EPCIS)





`#0969DA`


## 3. EPCIS ja CBV-standardien soveltaminen rakennusalan toimintaympäristössä

### 3.1 Suunnitteluvaihe


<img height="400" alt="EPCIS_vaihe_kuva1" src="https://github.com/user-attachments/assets/76e8572e-8050-4993-acf6-d83ac73c5cab" />

<table>
 <td> </td>
  <td> </td>
  <td> </td>
  <td> </td>
  <td> </td>
  <td> </td>
  <td> </td>
 
</table>





<img height="400" alt="EPCIS_vaihe_kuva2" src="https://github.com/user-attachments/assets/bd2aa069-c152-45fe-842f-afe1f222a9ee" />


<img height="400" alt="EPCIS_vaihe_kuva3" src="https://github.com/user-attachments/assets/0b2bb02b-0ca7-4e92-b8f6-e9207cc142b5" />


<img height="400" alt="EPCIS_vaihe_kuva4" src="https://github.com/user-attachments/assets/df209a45-f4a6-497a-bf6b-3b62ba7d42c3" />


<img height="400" alt="EPCIS_vaihe_kuva5" src="https://github.com/user-attachments/assets/3d0f2429-6206-4e29-b700-1982857dcb58" />


<img height="400" alt="EPCIS_vaihe_kuva6" src="https://github.com/user-attachments/assets/7c1d495e-c1d5-4e96-9c73-1afefa449a05" />


<img height="400" alt="EPCIS_vaihe_kuva7" src="https://github.com/user-attachments/assets/45a3d722-37ab-4d05-a19b-5e4e0ec69194" />


<img height="400" alt="EPCIS_vaihe_kuva8" src="https://github.com/user-attachments/assets/ac006553-80e2-4625-8870-7223103eddc7" />


<img height="400" alt="EPCIS_vaihe_kuva9" src="https://github.com/user-attachments/assets/e8b47ac9-02c8-432b-847d-fe27ae0f16d0" />






## New CBV status proposals (construction industry specified)

| Business step | Definition                                                                                                                                                                                                                   |Example of use                                                                                                                                                                                     |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|*designing*    |Business-process of designing a product |An item instance is defined by initial data. Design process takes place before selecting or producing the produt                                                                     |An item instance is defined by initial data. Design process takes place before selecting or producing the produt                                                                                   |
|*design_change*|Denotes a specific activity within business process where a change in an already completed and published design/plan is in the making                                                                                         |In the producing process it is noticed that the original design/plan needs to be updated, so a request for update is made and and the update is in the making                                      |
|*producing*    |Denotes a specific activity within business process where a product is produced. Either from raw materials or other products. Can not be afterwards disassembled to identifiable products as in the business step: assembled  |In excample concrete elements                                                                                                                                                                      |
|*error*        |Denotes a business process where error takes place and actions are made to solve it. Could happen in any stage of the supplychain                                                                                             |The surface of the concrete element does not match the quality requirements. The main process flow continues and the element is installed in place. The repair is scheduled and will be done later |
|*casting*      |A group of products is attached to each other. The attached products do not form a new item instance                                                                                                                          |Eg. Casting of concrete elements                                                                                                                                                                   |
|*maintenance*  |Denotes a business process where the maintenance or repair takes place either via scheduling or observing a faulty                                                                                                            |                                                                                                                                                                                                   |
|*recycling*    |Denotes a specific activity where a product is collected to recycling not destroying                                                                                                                                          |Concrete element is disassembled from a building and it is recycled either as a material or reused as a whole                                                                                      |
|*communication*|Denotes a phase in between/on top of business processes where information related to product is exchanged between parties                                                                                                     |Faulty product is due to repair, but is waiting guide/plan                                                                                                                                         |


| Disposition          | Definition                                                                                                                                                                                                            |Example of use                                                                                                                                                                                     |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|*awating_information* |The business step/process can not proceed until more information is provided.                                                                                                                                          |The produce line has not yet got the design plans for production.                                                                                                                                  |
|*information_received*|The business step/process can not proceed until more information is provided.                                                                                                                                          |The produce line has not yet got the design plans for production|                                                                                                                                  |
|*information_received*|	The information needed to proceed in the business step/process is received but the no actions has been made yet. 	                                                                                                   |The factory has received the plans for the product, but has not inspected them yet nor started the production.                                                                                     |
|*information_rejected*|The information received is not applicable, can not proceed.	                                                                                                                                                         |The factory has received the plans for the product and noted that the plan is not feasible. The plan is returned for the designer for updates                                                      |  
|*completed*           |Another "business step completed" value in addition to "available" in case there are phases in the same business process.                                                                                              |                                                                                                                                                                                                   |	
|*rejected*	           |Product or information related to product is rejected after receiving	                                                                                                                                                 |                                                                                                                                                                                                   |
|*requested*           |	The business step in case is requested to be done. 	                                                                                                                                                                 |The repair or shipping of the product is requested                                                                                                                                                 |
|*scheduled*           |	The business step in case is scheduled. 	                                                                                                                                                                           |The repair or shipping of the product is scheduled                                                                                                                                                 |
|*recycled*            |	The product is recycled as part of the business step collecting (if the new biz step is introduced recycling)	                                                                                                       |The concrete element is disassembled from a building and destroyed to pieces, then transported to waste center.                                                                                    |
|*re_used*             |	The product is reused as part of the business step collecting (if the new biz step is introduced recycling)	                                                                                                         |The concrete element is disassembled from a building as a whole and re used in another building.                                                                                                   |
|*error*               | critical	Critical error related to product is detected. The process cannot proceed until further action is taken.	                                                                                                   | The concrete element has damaged so badly that it cannot be lifted safely. Repair or change is needed before installation can proceed.                                                            |
|*error_in_progress*   |	Error is being handled.                                                                                                                                                                                              |	Actions are made to solve the error. For example repair is scheduled.                                                                                                                            |















# 🇫🇮 Tapahtumatiedon jakaminen GS1 EPCIS toimitusketjuhallinta standardin mukaan 
:building_construction::articulated_lorry:
Lähdeaineistot:
1. [EPCIS Sandbox](https://epcis-sandbox.gs1.org/)
2. [EPCIS Standard](https://ref.gs1.org/standards/epcis/)
3. [EPCIS and CBV Implementation Guideline](https://www.gs1.org/docs/epc/EPCIS_Guideline.pdf)
4. [Core Business Vocabulary (CBV) Standard](https://ref.gs1.org/standards/cbv/)
5. [Launch](https://www.gs1.org/docs/epcis/epcis_2-0_launch.pdf)

