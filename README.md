# Semantic Web of Things Project-A Hybrid Semantic Annotation, Extraction and Reasoning Framework for Cyber Physical System
## SWoT Architecture
The whole system is composed of four main components: SWoT-O Annotator, EL Annotator, Knowledge Storage and Semantic Reasoner. 
<img src="./Github_src_readme_files/Paper/1.tif"/>
#### •	SWoT-O Annotator
This building block is designed for generating metadata representations templates and annotating semantics of WoT resources with SWoT-O vocabulary. The SWoT-O is extended from SSN upper ontology and reuses some other IoT ontologies. It describes a Sensor-Observation-Event-Rule-Actuator-Action model that is useful for further reasoning tasks in most of intelligent and automatic CPS applications, and it also describes some common necessary attributes of physical devices (including sensors and actuators), such as Location, Ownership, Unit and DeviceType. The annotator provides a graphical user interface (UI) for service modeler to create domain services.
#### •	EL Annotator
This building block is designed for extracting semantic entities from the metadata of WoT resources and aligning SWoT ontologies with the concepts in the commonsense KB. In our testbed, DBpedia is used for the referent commonsense KB. The input of this module is the annotated WoT instances according to SWoT-O ontology, and the output is the annotated WoT metadata data with linked entities and aligned ontological concepts to DBpedia. The subtasks are divided into Schema Type Extraction & Identification, Candidate Entity Generation & Ranking and Relation Extraction, The extraction model is extended from EL framework that is usually used for semantic extraction and alignment on relational Web data.
#### •	Knowledge Storage
This building block provides common APIs for storing knowledge graph into persistent database. For storage efficiency and scalability, the graph database is proposed to be used. Concepts, properties, entities and relationships in Resource Description Framework (RDF) formats are transferred to graphical data structures. For compatible with existing semantic reasoner, RDF-based knowledge storage is also used. The query of the KB is based on a SPARQL-compatible language which could be also used for graph database.
>> #### •	Semantic Reasoner
This building block is aimed at providing a semantic reasoning capability based on the linked hybrid knowledge. The reasoning process could be both based on logical rules or statistical method or hybrid method. The query is based on a SPARQL language, and a list of ranked entities that matches the query are returned. The rule is modeled based on Jena’s rule language, and the reasoning process is based on Jena API and Jena Reasoner. 

## SWoT-O Ontology
To provide a uniform ontology of CPS applications, the SWoT base ontology (SWoT-O) is mainly referred to and extended from SSN ontology, as well as reusing other IoT ontologies, such as Semantic Actuator Network (SAN) for actuator, Stream Annotation Ontology (SAO) for streaming data and QUDT ontology for units of measure. 
<img src="./Github_src_readme_files/Paper/2-new.jp2"/>
According to SWoT-O vocabulary, we then setup a basic domain knowledge base of how these sensors and actuators collaborate with each other via SWoT-O Annotator. The temperature sensor and camera are annotated as ssn:Sensor with :WoTProperty, such as qu:Unit, :Location (:Region and :Spot), :Owner and :EntityType, while the CAC is annotated as san:Actuator with :Action. The ssn:FeatureofInterest is modeled as the target scenario composed with :SensorProperty of temperature sensor, camera and CAC. The :PhysicalProcess is modeled as the causal relation among these there devices with their :SensorProperty as input and output parameters. In this use case, the causal relations are categorized into two kind (:PositiveCorrelationProcess and :NegativeCorrelationProcess) as a reference knowledge for diagnosing the cause of anomaly.
<img src="./Github_src_readme_files/Paper/8-new.jp2"/>

## Proof-of-Concept Demostration
#### Step 1: UI for Creating New Devices with SWoT-O
<img src="./Github_src_readme_files/1.jp2"/>
#### Step 2: View constructed domain KB via protege
<img src="./Github_src_readme_files/2.jp2"/>
<br>
<img src="./Github_src_readme_files/3.jp2"/>
<br>
<img src="./Github_src_readme_files/4.jp2"/>
#### Step 3: Entity Linking for domain WoT Knowledge
<img src="./Github_src_readme_files/5.jp2"/>
<br>
<img src="./Github_src_readme_files/6.jp2"/>
<br>
<img src="./Github_src_readme_files/Paper/16.jp2"/>
<br>
<img src="./Github_src_readme_files/Paper/16-2.jp2"/>
#### Step 4: Initialize Aomaly Diagnosis Model
<img src="./Github_src_readme_files/7.jp2"/>
<br>
<img src="./Github_src_readme_files/8.jp2"/>
<br>
<img src="./Github_src_readme_files/9.jp2"/>
<br>
<img src="./Github_src_readme_files/10.jp2"/>
<br>
<img src="./Github_src_readme_files/11.jp2"/>
<br>
<img src="./Github_src_readme_files/12.jp2"/>
<br>
