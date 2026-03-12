Tarkoituksena on tarkastella betonielementtiliiketoiminnan tyypillistä tarjousvaiheen tietosisältöä “tarjouspyyntö”- ja “tarjous”-asiakirjojen osalta ja tunnistaa tärkeimmät kentät, joiden kautta muodostaa vakioitu tietosisältö peppol-sanoman muodossa.

Peppol verkostossa välitettävää “Pre-award” dokumentaatiota on esitetty täällä: [Peppol Pre-Award \- April 2026 Release](https://test-docs.peppol.eu/logistics/pracc-dev/)

Tarkasteltavat sanomasisällöt ovat alustavasti:

#### [\- Peppol BIS \- Call for Tenders 1.3 (T004).](https://test-docs.peppol.eu/logistics/pracc-dev/transactions/T004/)

#### [\- Peppol BIS \- Tender 1.3 (T005).](https://test-docs.peppol.eu/logistics/pracc-dev/transactions/T005/)

**Tunnistettuja kenttiä tarjouspyynnössä T004:**

| Rakennusalan kenttä | Selitys | Peppol XML kenttä | Esimerkki |
| ----- | ----- | ----- | ----- |
| Tarjouspyynnön tunnus | tarjouspyynnön yksilöllinen ID | `cbc:ID` | RFQ-2026-001 |
| Projektin tunnus | työmaan tai hankkeen tunnus | `cbc:ContractFolderID` | TYO10015 |
| Tarjouspyynnön päivä | milloin tarjouspyyntö lähetettiin | `cbc:IssueDate` | 2026-03-12 |
| Tarjouspyynnön aika | lähetyksen kellonaika | `cbc:IssueTime` | 10:30 |
| Tarjouspyynnön versio | dokumentin versio | `cbc:VersionID` | 1 |
| Tilaajan Peppol osoite | tilaajan verkkolaskuosoite (peppol osoite) | `cbc:EndpointID` | 003712345678 |
| Tilaajan Y-tunnus | yrityksen tunnus | `cac:PartyIdentification/cbc:ID` | 1234567-8 |
| Tilaajan nimi | tilaajan yritys | `cac:PartyName/cbc:Name` | NN Oy |
| Tilaajan katuosoite | yrityksen osoite | `cac:PostalAddress/cbc:StreetName` | Rakentajantie 5 |
| Tilaajan kaupunki | yrityksen sijainti | `cac:PostalAddress/cbc:CityName` | Helsinki |
| Tilaajan postinumero | postinumero | `cac:PostalAddress/cbc:PostalZone` | 00100 |
| Tilaajan maa | maa ISO-koodina | `cac:PostalAddress/cac:Country/cbc:IdentificationCode` | FI |
| Tarjouksen jättöpäivä | viimeinen tarjouksen jättöpäivä | `cac:TenderSubmissionDeadlinePeriod/cbc:EndDate` | 2026-03-30 |
| Tarjouksen jättöaika | viimeinen jättöaika | `cac:TenderSubmissionDeadlinePeriod/cbc:EndTime` | 16:00 |
| Hankinnan nimi | projektin nimi | `cac:ProcurementProject/cbc:Name` | Kerrostalo A |
| Hankinnan kuvaus | mitä hankitaan | `cac:ProcurementProject/cbc:Description` | Betonielementtien toimitus |
| Hankinnan tyyppi | tavara / palvelu | `cbc:ProcurementTypeCode` | 2 |
| Tuoteluokka | hankinnan luokitus (CPV) | `cac:MainCommodityClassification/cbc:ItemClassificationCode` | 44114200 |
| Työmaan ID | rakennuskohteen tunnus | `cac:RealizedLocation/cbc:ID` | SITE-001 |
| Työmaan osoite | työmaan katuosoite | `cac:RealizedLocation/cac:Address/cbc:StreetName` | Työmaankatu 10 |
| Työmaan kaupunki | työmaan sijainti | `cac:RealizedLocation/cac:Address/cbc:CityName` | Espoo |
| Työmaan postinumero | työmaan postinumero | `cac:RealizedLocation/cac:Address/cbc:PostalZone` | 02100 |
| Tarjousehdot | toimitus- ja sopimusehdot | `cbc:AdditionalConditions` | Toimitusehto: DAP (Incoterms 2010), vapaasti työmaalla; TOP (Finnterms 2001), toimitettuna määräpaikkaan muu, mikä; Sopimusehdot: RYHT 2000 Takuuaika:24 kk kohteen luovutuksesta Vakuudet: Rakennusaikainen vakuus: 10 % Takuuaikainen vakuus: 2 % |
| Maksuehto | maksuaika | `cbc:PaymentTerms` | 21 pv; 30 pv; muu mikä |
| Tarjouksen vastaanottaja | minne tarjous lähetetään (peppol id) | `cac:TenderRecipientParty/cbc:EndpointID` | 003712345678 |
| Tuoterivin tunnus | tarjouspyynnön tuoterivin yksilöllinen tunnus | `cac:ProcurementProjectLot/cbc:ID` | 1 |
| Tuotenimi | elementin tai tuotteen nimi | `cac:ProcurementProjectLot/cac:Item/cbc:Name` | Ulkoseinäelementti |
| Tuotekuvaus | tuotteen tekninen kuvaus | `cac:ProcurementProjectLot/cac:Item/cbc:Description` | Sandwich-elementti, betoni C40/50 |
| Määrä | tilattava määrä | `cbc:EstimatedQuantity` | 120 |
| Yksikkö | määrän mittayksikkö | `EstimatedQuantity@unitCode` | PCE (kpl), MTK (m²) |
| Liitteen nimi | tarjouspyynnön liitedokumentti | `cac:AdditionalDocumentReference/cbc:ID` | Elementtipiirustukset |
| Dokumenttityyppi | liitteen tyyppi | `cbc:DocumentTypeCode` | DRAWING |
| Liitetiedoston sijainti | linkki tai tiedoston tunniste | `cac:Attachment/cac:ExternalReference/cbc:URI` | [https://project.example.fi/drawings/elementit.pdf](https://project.example.fi/drawings/elementit.pdf) |

**Tunnistettuja kenttiä tarjouksessa T005:**

| Rakennusalan kenttä | Selitys | Peppol XML kenttä | Esimerkki |
| ----- | ----- | ----- | ----- |
| Tarjouksen tunnus | tarjouksen yksilöllinen ID | `cbc:ID` | TENDER-2026-045 |
| Projektin tunnus | tarjouspyynnön / työmaan tunnus | `cbc:ContractFolderID` | TYO10015 |
| Tarjouksen päivä | milloin tarjous lähetettiin | `cbc:IssueDate` | 2026-03-28 |
| Tarjouksen aika | tarjouksen lähetysaika | `cbc:IssueTime` | 14:15 |
| UBL versio | käytetty UBL versio | `cbc:UBLVersionID` | 2.2 |
| Peppol sanomamalli | sanomatyyppi | `cbc:CustomizationID` | urn:fdc:peppol.eu:prac:trns:t005:1 |
| Peppol prosessi | Peppol prosessiprofiili | `cbc:ProfileID` | urn:fdc:peppol.eu:prac:bis:p003 |
| Tarjoajan Peppol osoite | tarjoajan Peppol tunniste | `cac:TendererParty/cbc:EndpointID` | 003701234567 |
| Tarjoajan Y-tunnus | yrityksen tunnus | `cac:TendererParty/cac:PartyIdentification/cbc:ID` | 0111296-8 |
| Tarjoajan nimi | yrityksen nimi | `cac:TendererParty/cac:PartyName/cbc:Name` | Consolis Parma Oy |
| Tarjoajan katuosoite | yrityksen osoite | `cac:TendererParty/cac:PostalAddress/cbc:StreetName` | Betonitie 1 |
| Tarjoajan kaupunki | yrityksen sijainti | `cac:TendererParty/cac:PostalAddress/cbc:CityName` | Kangasala |
| Tarjoajan postinumero | postinumero | `cac:TendererParty/cac:PostalAddress/cbc:PostalZone` | 36220 |
| Tarjoajan maa | maa ISO-koodina | `cac:TendererParty/cac:PostalAddress/cac:Country/cbc:IdentificationCode` | FI |
| Tilaajan Peppol osoite | tilaajan Peppol tunniste | `cac:ContractingParty/cac:Party/cbc:EndpointID` | 003712345678 |
| Tilaajan Y-tunnus | tilaajan yritystunnus | `cac:ContractingParty/cac:Party/cac:PartyIdentification/cbc:ID` | 1234567-8 |
| Tilaajan nimi | tilaajan nimi | `cac:ContractingParty/cac:Party/cac:PartyName/cbc:Name` | NN Oy |
| Tarjouspyynnön viite | viittaus tarjouspyyntöön | `cac:DocumentReference/cbc:ID` | RFQ-2026-001 |
| Dokumentin kuvaus | viittauksen selite | `cbc:DocumentDescription` | Tarjous betonielementtien toimituksesta |
| Tuoterivin tunnus | tarjouksen rivin ID | `cac:TenderedProject/cac:ProcurementProjectLot/cbc:ID` | 1 |
| Tuotenimi | tarjottava elementti | `cac:Item/cbc:Name` | Ulkoseinäelementti |
| Tuotekuvaus | tekninen kuvaus | `cac:Item/cbc:Description` | Sandwich-elementti, betoni C40/50 |
| Määrä | tarjottu määrä | `cbc:Quantity` | 120 |
| Yksikkö | määrän mittayksikkö | `Quantity@unitCode` | PCE (kpl) |
| Yksikköhinta (alv 0%) | hinta per yksikkö | `cbc:PriceAmount` | 890 € |
| Kokonaishinta | rivin kokonaishinta | `cbc:LineExtensionAmount` | 106800 € |
| Tuoterivin tunnus | tarjouksen rivin ID | `cac:TenderedProject/cac:ProcurementProjectLot/cbc:ID` | 2 |
| Tuotenimi | tarjottava elementti | `cac:Item/cbc:Name` | Ontelolaatta |
| Tuotekuvaus | tekninen kuvaus | `cac:Item/cbc:Description` | Ontelolaatta 265 mm |
| Määrä | tarjottu määrä | `cbc:Quantity` | 850 |
| Yksikkö | määrän mittayksikkö | `Quantity@unitCode` | MTK (m²) |
| Yksikköhinta (alv 0%) | hinta per yksikkö | `cbc:PriceAmount` | 48 € |
| Kokonaishinta | rivin kokonaishinta | `cbc:LineExtensionAmount` | 40800 € |
| Toimitusehto | toimitustapa | `cbc:AdditionalConditions` | DAP työmaalla (Incoterms 2020\) |
| Maksuehto | maksuaika | `cbc:PaymentTerms` | 30 pv netto |
| Tarjouksen voimassaolo | tarjouksen voimassaoloaika | `cbc:AdditionalConditions` | Tarjous voimassa 2 kk |
| Takuuaika | tuotteen takuu | `cbc:AdditionalConditions` | 24 kk kohteen luovutuksesta |
| Liitteen nimi | liitetiedosto | `cac:DocumentReference/cbc:ID` | elementtiluettelo |
| Liitteen tiedostonimi | tiedoston nimi | `cbc:FileName` | elementtiluettelo.xlsx |
| Liitetiedoston sijainti | tiedoston URI | `cac:Attachment/cac:ExternalReference/cbc:URI` | [https://project.example.fi/documents/elementtiluettelo.xlsx](https://project.example.fi/documents/elementtiluettelo.xlsx) |

