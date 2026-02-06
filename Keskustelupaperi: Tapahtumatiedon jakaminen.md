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
|Antti Taskinen    | Fira                          |

</details>

<details>
<summary> Asiakirjan versio </summary>

| Versio  | Päivämäärä  | Tekijä  | Muutoskuvaus               |
|---------|-------------|---------|----------------------------|
| 0.0.1   | 6.2.2026    | TAla    | Luonnos vaihe              |

 </details>

 
## Sisällysluettelo



## Dokumentin tarkoitus

Tämän dokumentin tarkoituksena on koota ajatuksia tapahtumatiedonjakamisesta rakennusalan käyttötapauksissa ja toimia mahdollisesti toteutettavan soveltamisohjeen pohjana.

EPC Information Services (EPCIS)


EPC Information Services (EPCIS) 
An EPCIS solution is based on two standardized interfaces: Capture and Query. The 
Capture interface stores EPCIS events into an EPCIS Repository, which is a persistent 
database accessible through the Query Interface. Standard does not define how the 
database is implemented, only the interfaces for feeding and retrieving data. The 
interfaces are needed for interoperability, while the implementations allow for 
competition among those providing the technology and EPC Information Service. 
EPCIS events represent business steps accumulated through the supply chain that 
typically include a timestamp, location (GLN) and type of the event (e.g. packing, 
shipping and receiving). These events can be accessed internally or shared with partners 
through an authenticated Internet connection. (METROPOLIA LOPPURAPORTTI, 2012)


32 

The Capture Interface lies between the repository and an EPCIS Capturing Application. 
The Capturing Application supervises the operation of the lower-level architectural 
elements, and provides business context by coordinating with other sources of 
information involved in executing a particular step of a business process. In addition to 
RFID events, the applications can take input from other sources (e.g. manual input or 
barcode read). 
An EPCIS Query Interface provides two modes of interaction. In ―on-demand‖ or 
―synchronous‖ mode, a client makes a request through the EPCIS Query Control 
Interface and receives a response immediately. In ―standing request‖ or ―asynchronous‖ 
mode, a client establishes a subscription for a periodic query. Each time the periodic 
query is executed, the results are delivered asynchronously (or ―pushed‖) to a recipient 
via the EPCIS Query Callback Interface. The EPCIS Query Callback Interface may also 
be used to deliver information immediately upon capture bypassing the repository. (METROPOLIA LOPPURAPORTTI, 2012)


`#0969DA`



## Suunnitteluvaihe


<img height="400" alt="EPCIS_vaihe_kuva1" src="https://github.com/user-attachments/assets/76e8572e-8050-4993-acf6-d83ac73c5cab" />


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

