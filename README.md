# langDCAT-AP: Anvendelsesprofil til beskrivelse af sprogteknologiske datasæt (UDKAST/DRAFT)

- Namespace: https://data.gov.dk/profile/langDCAT-AP/
- Preferred prefix: langdcat-ap
- Modelnavn (label): langDCAT-AP
- Modelansvarlig (responsibleEntity): Digitaliseringsstyrelsen
- Versionnummer (versionInfo): 0.2.0
- Seneste opdateringsdato (dateModified): 2020-05-01
- Modelstatus (modelStatus): development
- Godkendelsesstatus (approvalStatus): afventer godkendelse
- Forretningsområde (theme): http://www.form-online.dk/opgavenoegle/06/#06.38.10.10
- Kommentar (comment) @da: Anvendelsesprofil til beskrivelse af sprogteknologiske datasæt 
- Kommentar (comment) @en: Application profile for the description of language technology datasets 

OBS: Denne anvendelsesprofil blive opdateret iht. den dansk anvendelsesprofil for beskrivelse af datasæt og datakataloger DCAT-AP-DK 2.0 når denne er godkendt. 

Læs mere om DCAT-AP-DK på dette link: https://digst.github.io/DCAT-AP-DK/releases/v.2.0/docs/

Prefix|	Namespace|	Vocabulary |
|---|---|---|
|dct	|	http://purl.org/dc/terms/	|	Dublin Core Terms|
|rdf	|	http://www.w3.org/1999/02/22-rdf-syntax-ns#|	The RDF Concepts Vocabulary|
|rdfs	|	http://www.w3.org/2000/01/rdf-schema#	|	RDF Schema 1.1|
|dctype	|	http://purl.org/dc/dcmitype/		|	 DCMI Type|
|owl	|	http://www.w3.org/2002/07/owl#	|	OWL Web Ontology Language|
|voaf	|	http://purl.org/vocommons/voaf#	|	Vcommons|
|vann	|	http://purl.org/vocab/vann/	|		A Vocabulary for Annotating Vocabulary Description|
|foaf	|	http://xmlns.com/foaf/0.1/	|		Friend of a Friend|
|skos	|	http://www.w3.org/2004/02/skos/core#	|	Simple Knowledge Organization System|
|schema	|	http://schema.org/	|			Schema.org
|xsd	|	http://www.w3.org/2001/XMLSchema#	|	XSD Schema |
|vcard|	http://www.w3.org/2006/vcard/ns#| VCard Ontology
|org	|	http://www.w3.org/ns/org# |		The Organization Ontology (W3C)|
|dk		|http://www.data-knowledge.org/dk/	|	The Data Knowledge Vocabulary|

|duv		|http://www.w3.org/ns/duv#	|	Data Usage Vocabulary|
|dcat	|	http://www.w3.org/ns/dcat#	|		Data Catalog Vocabulary (DCAT)|
|dcat-dk	|	https://data.gov.dk/model/core/dcat-dk# |			DCAT-DK	|
|dcat-ap-dk	|	https://data.gov.dk/model/profile/dcat-ap-dk# |			DCAT-AP-DK	|
|langdcat-ap	|	https://data.gov.dk/model/profile/lang-dcat-ap# |			langDCAT-AP	|
|ms		|http://lodserver.iula.upf.edu/Metashare/ontology/	|	MetaShare| Se også: http://www.meta-net.eu/meta-share/META-SHARE%20%20documentationUserManual.pdf & https://github.com/martavillegas/metadata


### Klasse:Dataset (datasæt) 
Property|	URI|	Range|	Usage note|	Card |
|---|---|---|---|---|
| description|  dct:description	 |  rdfs:Literal |  This property contains a free-text account of the Dataset. This property can be repeated for parallel language versions of the description.	 |  1..n |   |	
| title	|dct:title	|rdfs:Literal|	This property contains a name given to the Dataset. This property can be repeated for parallel language versions of the name.	|1..n|		
| publisher	|dct:publisher|	foaf:Agent	|This property refers to an entity (organisation) responsible for making the Dataset available.|	0..1|
| dataset responsible organisation |	dcat-dk: datasetResponsible Organisation|	org:FormalOrganisation	|(OBS: Dansk tilføjelse) datasætaansvarlig organisation: organisation  der er ansvarlig for den overordnede administration af alle forhold omkring et datasæt.|0..1|
| theme/ category	|dcat:theme, subproperty of dct:subject	|skos:Concept	|This property refers to a category of the Dataset. A Dataset may be associated with multiple themes.	|0..n|
| type	|dcat:type	|skos:Concept	|This property refers to the type of the Dataset. A controlled vocabulary for the values has been established based on The META-SHARE Metadata Schema	|0..n|
public administrative task type|	dcat-dk: publicAdministrative TaskType|	skos:Concept|(OBS: Dansk tilføjelse) Forvaltningsopgave: Angiver en eller flere forvaltningsopgaver jf. FORM som har dannet grundlag for dataindsamlingen|	0..n	|
| conforms to	|dct:conformsTo	|dct:Standard	|This property refers to an implementing rule or other specification.|	0..n|
| documentation	|foaf:page	|foaf:Document|	This property refers to a page or document about this Dataset.|	0..n|
| frequency	|dct:accrualPeriodicity	|dct:Frequency|	This property refers to the frequency at which Dataset is updated|	0..1|
| landing page|	dcat:landingPage|	foaf:Document|	This property refers to a web page that provides access to the Dataset, its Distributions and/or additional information. |	0..1|
| language	|dct:language	|dct:LinguisticSystem	|This property refers to a language of the Dataset. This property can be repeated if there are multiple languages in the Dataset.|	0..n|
| spatial/ geographical coverage|	dct:spatial|	dct:Location|	This property refers to a geographic region that is covered by the Dataset. |	0..n|
| payment imposed|	dcat-dk: payment ImposedContents|	xsd:Boolean	|	(OBS: Dansk tilføjelse) Betalingspålagt: Angiver om der er pålagt en betaling på det pågældende datasæt. |0..1|
| personal data category 	|dcat-dk: personalDataCategory	|skos:Concept	|(OBS: Dansk tilføjelse) Personoplysningskategori: Angiver hvilken type af personoplysninger som datasættet indeholder.|0..n	
| legal ressource |cv:hasLegalResource	|eli:LegalResource|(OBS: Dansk tilføjelse)	Hjemmel: Den hjemmel forankret i lovgivningen som har været gældende for dataindsamlingen.	 |0..n	|
| access rights|dct:accessRights|dct:RightsStatement| Information about who can access the resource or an indication of its security status.|---|
| license|dct:license|dct:License|A legal document giving official permission to do something with the resource.|0..1 |
| modality type|ms:modalityType|skos:Concept|Modality is the channel by which signs are transmitted (oral, gesture, written)|1..* |
| annotation type|ms:annotationType|ms:AnnotationType|Specifies the Annotation Level of the resource or the Annotation Type that a tool/ service requires or produces as an output|0..* |
| size information|ms:sizeInfo|ms:sizeInfo|Identifies the size of the resource|0..1|
...


### Klasse:Distribution (Datasætrepræsentation) 
Property|	URI|	Range|	Usage note|	Card |
|---|---|---|---|---|
| accessURL	|dcat:accessURL	|rdfs:Resource|	A URL of the resource that gives access to a distribution of the dataset. E.g. landing page, feed, SPARQL endpoint.	|1..n|		
| description|  dct:description	 |  rdfs:Literal |  This property contains a free-text account of the Distribution. This property can be repeated for parallel language versions of the description.	 |  0..n |   |	
| title	|dct:title	|rdfs:Literal|	This property contains a name given to the Distribution. This property can be repeated for parallel language versions of the name.	|0..n|		
| format |dct:format|dct:MediaTypeOrExtent|This property refers to the media type of the Distribution as defined in the official register of media types managed by IANA|0..1|
| licence|dct:license|dct:LicenseDocument|This property refers to the licence under which the Distribution is made available. |0..1|
| language	|dct:language	|dct:LinguisticSystem	|This property refers to a language of the Distribution. This property can be repeated if there are multiple languages in the Dataset.|	0..n|
| annotation type|ms:annotationType|ms:AnnotationType|Specifies the Annotation Level of the resource or the Annotation Type that a tool/ service requires or produces as an output|0..* |
| size information|ms:sizeInfo|ms:sizeInfo|Identifies the size of the resource|0..1|
...
