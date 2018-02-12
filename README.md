![Grapevineworld Logo](http://www.mascanc.net/gpvlogo.png)

Welcome to the [Grapevineworld](http://www.grapevineworldtoken.io) repository. This repository is about the Grapevine Orchestration Engine (GOE). If you are looking for the other components (the Grapevine APP, the User Dashboard, and the Vendor Façade, please visit the [main Github page](http://github.com/grapevineworld).

# Introduction

Grapevine World is a decentralized, borderless ecosystem for the seamless, standardized exchange of healthcare data. At the core of the healthcare exchange there is the Integrating the Healthcare Enterprise, [IHE](http://www.ihe.net) model, which consists on a set of free and open standards where anyone can contribute. IHE selects technologies following a well-defined methodology based on a set of architectural approaches which are compatible with the well known [TOGAF](https://it.wikipedia.org/wiki/The_Open_Group_Architecture_Framework) and the European Interoperability Framework, [EIF](https://ec.europa.eu/isa2/eif_en).

Interoperability is a crucial aspect of IT Security and Patient Safety. The ISO 27000 family of standards has three building blocks to identify security measures: the CIA triad, Confidentiality, Integrity, and Availability. If a patient is having emergency treatment and the doctor need to access her Electronic Health Record (EHR), if such EHR is not encoded and transmitted in a format which the First Aid department is able to evaluate due to a lack of interoperability, the EHR is not available thus not secure according to the CIA triad. Often confusion arises amongst the effect named "Vendor Lock-In". In the early stage of the EIF, Interoperability has been foreseen by creating technologically disconnected islands following a specific standard (e.g., [HL7](http://hl7.org)) or a specific Vendor. The [Free Software Foundation](http://www.fsfe.org) debated this point and [welcomed](https://ec.europa.eu/isa2/sites/isa/files/consultations/position-papers/germany/free-software-foundation-europe_en.pdf) a new revision of the EU strategy, while stressing the idea of _openness of solutions, technical specifications, and implementations is a prerequisite not only for interoperability but is crucial for the idea of technoligical neutrality, user-centricity, and reusability_. In this regards we believe that the IHE process dramaticaly helps the vision of 
both the regulators and the free software community to achieve the common goal of secure and interoperable healthcare exchange.

Grapevine World aims at exploiting the IHE process to reach global interoperability. It builds its root on existing initiatives such as:

* [epSOS](http://www.epsos.eu) the first large scale pilot (connecting almost all the EU member states) that provided the first interoperability specifications based on IHE for Patient Summary and e-Prescriptions cross-border exchange
* [e-SENS](http://www.esens.eu) cross-vertical pilot project that used the IHE process to further enhance and secure the cross-border healthcare exchange
* [eHealth Digital Service Infrastructure](https://ec.europa.eu/cefdigital/wiki/display/EHOPERATIONS/eHealth+DSI+Operations+Home) the body of the EU commission which is operating under the "New EIF" the Cross-Border e-Health Information Services (CBeHIS)
* [The Trillium Bridge](http://trilliumbride.eu) the EU-US initiative for the trans-Atlantic healthcare exchange
* [NwHIN](http://sequoiaproject.org/resources/exchange-specifications/) the backbone of the interoperability in the United States of America

The Grapevine backbone interconnects all the healthcare enterprises by using IHE standards (and providing a SDK for those who are not yet using IHE) enabling a healthcare data exchange at a global scale.
It is worth noticing that IHE is not limited to the projects above, but it is available worldwide (see the [IHE Worldwide](http://www.ihe.net/IHE_Worldwide/) page), thus the technology and the standards are available and active all over the world. The above initiatives are the ones in which the Grapevine World team actively participated and contributed. 

# The GOE
The Grapevine World initiative exploits the Blockchain technology as a facilitating infrastrcuture for the data exchange network, and in providing incentives to participate in the network. At the core of the Grapevine World interoperability we have the *orchestration engine*. Following the [Reactive Manifesto](https://www.reactivemanifesto.org), the GOE ecosystem is shown in the following picture (Source: the Grapevine World Token whitepaper).

![The GVW ecosystem](http://www.mascanc.net/ecos1.png)

Each patient has data to share, of two kind: *clinical* and *fitness*. Electronic Health Records, patient summaries, ePrescriptions, they all fall in the clinical category, while vital signs, lifestyle, sport activities, etc, fall in the fitness category. 

Initial foreseen stakeholders of the health data are Charities and NGOs, Teaching institutes, Insurance companies, Pharmaceutical companies, Service providers, application developers (who can access to a set of evolving patient test data) and analytics providers who can in turn offer their services. 

## Handling clinical data
Clinical data is usually stored in the datacenters of healthcare providers (HCP) or healthcare organizations (HPO) in either proprietary format (Electronic Medical Record, EMR), or ready to be shared (EHR), or even in paper-format. EMRs are system-internal representation of clinical data, and they are not usually interoperable. When a record needs to cross the border of a Healthcare Information System (HIS) becomes an EHR and typical formats are Clinical Document Architecture ([CDA](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=7),  or [FHIR Resources](http://hl7.org/fhir)). Depending on the granularity of the semantics chosen to represent the data, clinical documents vary from scanned documents, to normal text in prosa (CDA L1), or fully coded in a vocabulary/ontology (CDA L2, L3). Such data flows following such IHE standards as [XDS](https://wiki.ihe.net/index.php/Cross-Enterprise_Document_Sharing), or [XCA](https://wiki.ihe.net/index.php/Cross-Community_Access), or FHIR across the boundaries of the organizations. The access to clinical data is made using those IHE transactions seamlessly entering in the domain of the hospital and keeping and enhancing the existing security procedures. For those HCPs and HPOs who do not have yet a IHE-based infrastructure, the Grapevine World Façade will perform the EMR-to-EHR translation. The façade has its roots in the national connector of the National Contact Point for eHealth ([NCPeH](https://openncp.atlassian.net/wiki/spaces/ncp/pages/74317847/National+Connector+Specifications)) , the SDK based on Web-Service and RESTFul APIs that connects clinics and hospitals across the European Union. For more information see the [Façade repo](http://github.com/grapevineworld).

## Handling fitness data
Wereable devices, Body Area Networks, and IoT components defines data streams that the patient could potentially share with research institutes, pharmaceutical companies, or insurance companies (in those countries where this aspect is legal). Those devices connect themselves using major frameworks such, e.g., [HealthKit](https://developer.apple.com/healthkit/). By leveraging those frameworks, patient could allow those fitness data streams into the GOE using the Grapevine World App and make them available for further analysis by the various stakeholders. 


## Privacy
Notably, clinical and fitness data fall in two different security and legal context. A pillar of the GOE is that *nor clinical nor fitness data is stored*, and the *data processing is completely anonymous*. The GOE goal is only to connect various stakeholders by effectively and securely sharing the data streams, while collecting payment and rewards in Grapes and distributing across the various actors. We try to make the user completely unlinked to his data. For more information on user handling and registration, please see the [User Dashboard repo](http://github.com/grapevineworld).

## Overarching architecture

The architecture of the Grapevine World is shown in the next picture. 
![The GVW GOE](http://www.mascanc.net/goe.png)

In relations to the patterns highlighted in [Software Architecture in Practice](https://www.amazon.com/Software-Architecture-Practice-3rd-Engineering/dp/0321815734), in the [P of EAA](https://www.amazon.it/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420), and in the [EIP](https://www.amazon.it/Enterprise-Integration-Patterns-Designing-Deploying/dp/8131725081/ref=pd_lpo_sbs_14_t_1?_encoding=UTF8&psc=1&refRID=SH2CY9BMM4DQ3ADTW1GV), we employ a SOA architectural pattern, with a PubSub system. 
The data broker is is composed by:

* The GOE, that handles the back-end mechanics of the system. That is when a request arrive at the Data Broker, the GOE is employed to execute the orchestration workflow
* The Grapevine APP, the primary way patients interact with the data broker
* The portals, User Dashboard and the HPO Dashboard. The former shares the same functionalities as the Grapevine App, the latter is how HPOs interact with the Grapevine Data Broker

The GOE implements orchestrations following the [Actor Model](https://dspace.mit.edu/handle/1721.1/6952). As each component of the system may fail at anytime, we always try to recover the status of the application using the [Event Sourcing](https://martinfowler.com/eaaDev/EventSourcing.html) pattern. In fact, given the asynchronous behavior of the Ethereum blockchain (interaction with [Web3j](https://github.com/web3j/)), and having potential failures from both the HPOs and the App, we aim at implementing the GOE as a set of actors handling [Kafka](http://kafka.apache.org) streams, integrated with [Akka](https://doc.akka.io/docs/akka-stream-kafka/current/home.html). A sketch of the Actors would be as per the following tree. 

![A sketch of the actors](http://www.mascanc.net/goesup.png)

A manager would be assigned to each of the domains in which the GOE interacts (requests from pharmaceutical companies, HPOs, applications, dashboards, etc). Then a set of actors are created
on request to evaluate the logic behind each request. 

By using such model we allow to have a resilient system which should resist to traffic peaks, totally asynchronous. When a actor fails, thanks to the Event Sourcing pattern, it is restored to its state before the failure by loading all the events. 

However the architectural details are yet TBD. The target language is Java. 

## A Typical use case 

Before looking in the details of the possible events, let recap the typical use case shown in Section 6 of the Grapevine World white paper. In this case, a Pharmaceutical company requires data for a trial, and uses the Grapevine Backbone to request it. 

![Diagram UML of the use case](http://www.mascanc.net/ucuml.png)

In steps 1&2, Patients and HPOs register with Grapevine, in step 3 data is requested, in step 4 the data broker matches potential canditates. This part deserves a bit more focus. In fact agreements shall be made amongst the Grapevine foundation with the requesting Pharma in order to provide the best fit to match patient that suit the requirements from the caller. Matching criteria shall be evaluated case-by-case, thus for this part the component will provide the XDS query criteria by default, with geolocalization of the user. In steps 5 and 6, the patient consents, and such consent is submitted to the HPOs which she registered in the Grapevine database in the form of IHE BPPC. In steps 7 and 8 the GOE queries document metadata, in step 9 metadata is anonymized, in step 10 payment is determined and the requestor is informed (step 11). In step 12 the payment is transferred and in step 13 data retrieval is enabled. In steps 14-17 patients and HPOs are informed and data is retrieved. In step 18 data is cached and anonymized on the data broker, in step 19 data is retrieved by pharma while in the last steps (20-22) payment distributed to patients and HPOs (consult the whitepaper for more detailed information). 

### The FSM

The above UML diagram can be represented in a Non Deterministic Finite Automaton (NFA) represnted as follows.
 
![The NFA of the GOE](http://www.mascanc.net/fsm.png)

The system starts with the `REQUEST_WAIT` state, waiting obviously for new request. When the new request arrives (`Pharma_req_data`) we enter in the `SELECT_MATCH` status where the GOE selects the potential patients matching the query from Pharma. If the query is invalid, we turn back to the initial state (`Invalid_req`), and if there are no matching patient, we end in the `ERROR_PROCES` end state. After succesfully selected the patients we change state using the `Notify_patients` transaction and we go in the `COLLECT_CONS` state. If no patient give consent, we transact to the error state using the `no_cons` transaction. Otherwise we move to the `CONSENT_SUBM` state using the `submit_cnst_hpo` transaction which submits all the received consents to the HPOs for which the patient is registered and known by the GOE. After requesting the metadata (`req_mdata`), we collect all of them and we transact to `CLLECT_MDATA`. If no documents are found, the `no_doc_found` transactions goes in the error state. Otherwise we evaluate the amount, and we notify it (`ntfy_amount`). We then wait for the grapes in the state `AN_WAIT_GRAP`. If no grapes are received in a given quantum of time, the transaction `no_grapes_recv` moves to the error state. Otherwise the NFA's next state is `GRAPES_RECEVD`. At this time w notify the patients and the hpo (`ntfy_hpo_pat`) and we record a new state change (`PAT_HPO_NTFYD`). We then retrieve the documents (`retrieve_doc`) and we collect and anonymize all the data (`DATA_COLLECT`). Notably the [anonymization](https://www.ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Handbook_De-Identification_Rev1.1_2014-06-06.pdf) algorithms are pluggable. They span from simply removing the patient identifier from CDA to a more complex an AI-based solutions, TBD. If no data is returned in the retrieve, we transact to the error state using the `no_data_found`. Otherwise we distribute grapes (`distr_grape`) and we move to the `GRAPES_DISTR`. After sending data with `send_data` action, we conclude in the `DATA_SENT`. 

We use this finite state machine to define our logs to reconstruct the state of a crashed actor. This NFA also defines the information that are logged at the GOE. 


# Timeline
This is a rough distribution of timelines expected for the development of the GOE. 

* Q2 2018 Ethereum development: The crowdsale and the ERC-20 token 
* Q3 2018 (Late summer, Fall) Version ready for audit and pentest
* Q1 2019 Production (w.r.t. the Grapevine World timeline)

# Contributors

* Massimiliano Masi <massimiliano.masi@tiani-spirit.com> - [github.com/mascanc](http://github.com/mascanc)
* Abdallah Miladi <abdallah.miladi@tiani-spirit.com>
