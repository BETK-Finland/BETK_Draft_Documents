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







`#0969DA`



## Suunnitteluvaihe

![20250515_Kuva1](https://github.com/user-attachments/assets/b700cd01-b8bd-4143-9abc-ecefd0af2573)



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

