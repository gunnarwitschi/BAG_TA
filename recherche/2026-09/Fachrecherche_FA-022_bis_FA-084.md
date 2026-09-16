# Öffentliche technische Architektur – FA-022 bis FA-084

Stand: 2026-09-16

## Modellierungsregel

Nur öffentlich belegte technische Informationen werden als Technologie/Technologieversion übernommen. Plattformen, Application Cluster und Programme (z.B. ePGU, ePL) werden nicht als Technologie modelliert. Bei fehlender Version keine Version erfinden.

## Ergebnisse

| FA | Fachanwendung | Öffentliche technische Erkenntnis | Modellstatus |
|---|---|---|---|
| FA-022 | MiGeL | MiGeL wird künftig über ePL digitalisiert; ePL ist Plattform, nicht Technologie. | keine neue T/TV; ePL als Plattformkontext |
| FA-023 | SL | Neue SL seit 05.01.2026; monatliche FHIR-Daten; XML nur noch bis 30.06.2026. | FHIR, XML; konkrete Implementierung offen |
| FA-024 | EPD Zertifizierungstestsystem | EPD-Zertifizierung basiert öffentlich auf IHE-/Interoperabilitätstests; konkrete BAG-Installation/Version nicht belegt. | IHE/Test & Validierung; keine konkrete Produktversion |
| FA-025 | EPD Referenzumgebung | Gazelle/IHE sind als Test-/Referenzumgebung öffentlich relevant. | Gazelle/IHE, konkrete Version offen |
| FA-026 | EPD Zertifizierungstestsystem | EPD-Zertifizierung mit IHE-Testinfrastruktur; konkrete Produktversion nicht belegt. | IHE/Test & Validierung |
| FA-027 | ePGU Plattform | ePGU ist Programm/Plattform für mehrere Fachanwendungen, keine Technologie. | nicht als T/TV modellieren |
| FA-028 | Anmeldestelle Chemikalien | Gemeinsame Anlauf-/Verfügungsstelle von BAG, BAFU, SECO; öffentliche technische Implementierung nicht ausreichend dokumentiert. | keine neue T/TV |
| FA-029 | DEK | Öffentliche technische Implementierung nicht belastbar identifiziert. | keine neue T/TV |
| FA-030 | ePGU APVS | APVS ist ePGU-Anwendung; öffentliche Beschreibung bestätigt strukturierte Datenerfassung, Verarbeitung und Auswertung von Parametern/Matrizen/Limiten. | ePGU/Application-Kontext; konkrete Technik offen |
| FA-031 | ePGU arTx Betrieb | arTx ist ePGU-Fachanwendung für Bewilligungen im Transplantationsbereich; konkreter Stack öffentlich nicht belegt. | keine neue T/TV |
| FA-032 | ePGU Betrieb Anwendungen | Querschnittlicher ePGU-Betrieb; gemeinsame Services/Infrastruktur für Anwendungen sind öffentlich beschrieben. | Application-/Betriebskontext, keine konkrete T/TV |
| FA-033 | ePGU Consultations | Öffentliche technische Implementierung nicht ausreichend belegt. | keine neue T/TV |
| FA-034 | ePGU Dosimetrieportal | Öffentliches Webportal; konkrete technische Implementierung/Version nicht belegt. | Web/Application-Kontext, keine konkrete T/TV |
| FA-035 | ePGU ePortal NISSG | NISSG/ePortal als ePGU-Anwendung; konkrete technische Produkte öffentlich nicht belastbar. | keine neue T/TV |
| FA-036 | ePGU MeCanna-BetmG | Elektronischer Gesuchs-/Meldeprozess im ePGU; konkrete technische Produkte nicht belegt. | keine neue T/TV |
| FA-037 | ePGU Meldeportal Tabak | Tabacinfo ist ePGU-Anwendung; gemeinsamer ePGU-Service für Feedback belegt, aber kein konkreter Stack. | keine neue T/TV |
| FA-038 | ePGU Radiation Portal Switzerland | RPS ist ePGU-Fachanwendung; konkrete technische Implementierung öffentlich nicht belegt. | keine neue T/TV |
| FA-039 | ePGU Radonportal | Radonportal 3.0 seit Dez. 2025 produktiv; konkreter Technologie-Stack öffentlich nicht belegt. | keine neue T/TV |
| FA-040 | ePGU Reports | ePGU-Anwendung/Reporting-Kontext; keine belastbare konkrete Produkttechnologie. | keine neue T/TV |
| FA-041 | ePGU RPC | Chemikalienprodukteregister RPC ist ePGU-Anwendung; konkrete technische Produkte öffentlich nicht belegt. | keine neue T/TV |
| FA-042 | GEBU (MedReg/PsyReg/BetReg) | Bündel/Anwendungszusammenhang der Register; MedReg besitzt öffentlich dokumentierte Standardschnittstelle. | Schnittstellenkontext; konkrete Version offen |
| FA-043 | BetReg | Betäubungsmittelregister; öffentliche technische Implementierung nicht ausreichend dokumentiert. | keine neue T/TV |
| FA-044 | Medizinalberuferegister Betrieb | MedReg verfügt über eine Standardschnittstelle; öffentlich dokumentierte Schnittstellen-/Registerfunktion. | Schnittstellenkontext; konkrete Implementierung offen |
| FA-045 | MedUse | Öffentliche technische Architektur nicht belastbar gefunden. | keine neue T/TV |
| FA-046 | PsyReg | Register mit öffentlicher Abfrage; technische Implementierung/Version nicht ausreichend dokumentiert. | keine neue T/TV |
| FA-047 | Harvester | Keine belastbare öffentliche Dokumentation zum konkreten technischen Stack. | keine neue T/TV |
| FA-048 | Health Person Directory BAG | Personen-/Verzeichnisdienst; konkrete technische Implementierung öffentlich nicht ausreichend belegt. | keine neue T/TV |
| FA-049 | Health Provider Directory Digisanté | HPI/Provider-Directory-Kontext; konkrete Implementierung öffentlich nicht ausreichend belegt. | keine neue T/TV |
| FA-050 | Humanforschung Schweiz | BASEC ist als elektronisches Einreichungssystem der Ethikkommissionen öffentlich belegt; SNCTP als elektronisches Studienregister. Zuordnung zur konkreten FA teilweise offen. | BASEC/SNCTP als mögliche HP, Zuordnung prüfen |
| FA-051 | IDD | IDD ist digitales Informationsportal für übertragbare Krankheiten; öffentliche REST-API ersetzt frühere Dashboard-API. | REST/API; konkrete Implementierung offen |
| FA-052 | nasure | NASURE 2024–2034; Umsetzung ab 2026, MVP/erste Inbetriebnahme 2028; soll alte EOL-Systeme ablösen. | Architektur-/Lifecycle-Kontext; konkrete T/TV offen |
| FA-053 | OBLIG | Keine belastbare öffentliche technische Implementierung gefunden. | keine neue T/TV |
| FA-054 | ISAK | ISAK/ISAKR ist Informationssystem für Aufsicht Krankenversicherung; technische Detailimplementierung öffentlich nicht ausreichend belegt. | keine neue T/TV |
| FA-055 | Azure Analytics | Microsoft Azure als Plattformkontext; konkrete BAG-Komponenten/Versionen öffentlich nicht vollständig belegt. | Azure als Plattform, Version offen |
| FA-056 | ISAK Cube | Analyse-/BI-Komponente im ISAK-Kontext; konkretes Produkt öffentlich nicht belastbar. | keine neue T/TV |
| FA-057 | ISAK DWH | Data-Warehouse-Komponente des ISAK-Kontexts; konkrete DB-/DWH-Technologie öffentlich nicht ausreichend belegt. | DWH als Architekturmerkmal, keine konkrete T/TV |
| FA-058 | ISAK Webclient | Webclient des ISAK-Kontexts; konkretes Frontend-Framework öffentlich nicht belegt. | keine konkrete T/TV |
| FA-059 | IT-Architektur KRG | Keine belastbare öffentliche technische Implementierung gefunden. | keine neue T/TV |
| FA-060 | kleine Web Anwendungen | Sammelbegriff; keine einheitliche technische Architektur ableitbar. | keine neue T/TV |
| FA-061 | LeReg | Register-/Meldekontext; konkrete technische Implementierung öffentlich nicht ausreichend dokumentiert. | keine neue T/TV |
| FA-062 | MDM | Öffentliche/Arbeitsmodell-Erkenntnisse: ODBC, JDBC, XML-Webservice, Data Vault, R; iRIX/MDM-Ablösung 2026 vorgesehen. | bestehende Zuordnungen beibehalten; Lifecycle hoch relevant |
| FA-063 | NICERStat KiKR | NICERStat ist Registersoftware; sedex-Schnittstelle öffentlich bestätigt. Migration KiKR auf NICERStatKRG läuft. | sedex; konkrete Produktversion offen |
| FA-064 | PSU Datenerhebung | Keine belastbare konkrete technische Implementierung gefunden. | keine neue T/TV |
| FA-065 | Sentinella | BAG-Meldesystem; öffentliche Beschreibung bestätigt elektronisches Meldesystem. Konkreter Stack nicht belegt. | keine neue T/TV |
| FA-066 | SOAS | Arbeitsmodell: LDAP und Airlock. Öffentliche Seiten bestätigen SOAS/Authentisierungskontext, aber keine konkrete Airlock-Version. | LDAP/Airlock beibehalten; Version offen |
| FA-067 | Strados | Arbeitsmodell: Oracle Database, XML. Keine öffentlich belastbare Version. | Oracle DB/XML; Version offen |
| FA-068 | Studienregister (SNCTPx) | SNCTP ist elektronisches Register klinischer Versuche und öffentlich dokumentiert. | Register/DB-Kontext; konkrete Technologie offen |
| FA-069 | Swiss Covid App | Öffentliche historische Architektur mit mobilen Apps, Backend und Proximity-Tracing; heute ausser Betrieb. Keine aktuelle T/TV-Zuordnung ableiten. | historisch; konkrete Versionen nicht neu modellieren |
| FA-070 | Swiss KiPaDoS | Öffentliche technische Detailarchitektur nicht belastbar gefunden. | keine neue T/TV |
| FA-071 | Swiss PLF | Elektronisches Passenger Locator Form; historische Anwendung, konkrete Implementierung öffentlich nicht ausreichend dokumentiert. | historisch; keine neue T/TV |
| FA-072 | Terminologieserver | Terminologieserver im Gesundheitsdaten-/FHIR-Kontext; konkrete Produkt-/Version nicht belastbar. | FHIR/Terminologie-Kontext; konkrete TV offen |
| FA-073 | Transformator | FHIR/I14Y; Azure FHIR Service ausdrücklich als geplante technische Lösung belegt. | FHIR, I14Y; Azure FHIR Service als geplant kennzeichnen |
| FA-074 | Vaccination Monitoring Data Lake | Azure-/Data-Lake-Kontext; ELCA nennt Smart Data Lake Builder und Databricks öffentlich. | Azure, Smart Data Lake Builder, Databricks; konkrete Version offen |
| FA-075 | Vigilanz | Swissmedic ElViS als elektronisches Vigilanz-Meldesystem öffentlich belegt; konkrete BAG-Implementierung/Version offen. | ElViS als Produkt/externes System-Kontext |
| FA-076 | VMS | Keine belastbare öffentliche technische Implementierung gefunden. | keine neue T/TV |
| FA-077 | Airlock 2FA | Airlock IAM als konkretes Produkt belegt. | HP Airlock IAM; Version offen |
| FA-078 | ALVPH | ALVPH im Agate-/Datenmanagement-Kontext des BLW; konkrete technische Implementierung öffentlich nicht ausreichend. | keine neue T/TV |
| FA-079 | LDAP BV | LDAP als Verzeichnis-/IAM-Technologie plausibel und im Arbeitsmodell belegt. | LDAP; Version offen |
| FA-080 | NAS | NAS ist Infrastruktur-/Storage-Kontext; konkrete Produktversion öffentlich nicht belegt. | Storage-Kontext; keine konkrete TV |
| FA-081 | SAP | SAP als Herstellerprodukt im Arbeitsmodell; konkrete SAP-Version/Produktlinie öffentlich für diese FA nicht belegt. | HP SAP; Version offen |
| FA-082 | Datenbank (generisch) | Abstrakte/technische Basisanwendung; keine konkrete DB ableitbar. | keine neue T/TV |
| FA-083 | DWH B LV (ISCeco) | DWH-/Datenplattform-Kontext; konkrete Produkt-/Version öffentlich nicht belastbar. | keine neue T/TV |
| FA-084 | e-health-suisse.ch | Öffentliche Webplattform von eHealth Suisse; EPD-Spezifikationen nutzen u.a. IHE, FHIR, XML/Web Services und X.509/TLS. | IHE/FHIR/XML/Web Services/TLS-X.509 als Standardkontext |

## Wichtige Abgrenzungen

- **ePGU, ePL und ähnliche Plattformen/Application Cluster werden nicht als Technologie modelliert.**
- Bei ePGU-Anwendungen ist die gemeinsame ePGU-Plattform Architekturkontext, nicht T/TV.
- Konkrete Produkte werden nur bei ausreichendem Nachweis als HP/HPV aufgenommen.
- Geplante Technologien werden ausdrücklich als geplant gekennzeichnet.
- Historische Systeme wie CH-SUR, Swiss Covid App oder alte SL-Technologie werden nicht als aktuelle Architektur interpretiert.

## Quellen / Rechercheanker

- BAG ePL: https://www.bag.admin.ch/de/elektronische-plattform-leistungen-epl
- SL Daten/FHIR: https://sl.bag.admin.ch/resources/current-and-archived-data
- DigiSanté Anwendungen ePGU: https://www.digisante.admin.ch/de/anwendungen-epgu
- DigiSanté Meilenstein ePGU: https://www.digisante.admin.ch/de/meilenstein-epgu
- DigiSanté Produkte: https://www.digisante.admin.ch/de/produkte-digisante
- MedReg: https://www.bag.admin.ch/de/medizinalberuferegister-medreg
- MedReg Standardschnittstelle: https://www.bag.admin.ch/de/zugang-zum-medreg-via-standardschnittstelle
- Sentinella: https://www.bag.admin.ch/de/sentinella-meldesystem
- ElViS: https://www.swissmedic.ch/elvis
- ALVPH: https://www.blw.admin.ch/blw/de/home/politik/datenmanagement/agate/alvph.html
- IHE: https://www.ihe.net/resources/technical_frameworks/
- FHIR: https://hl7.org/fhir/
- I14Y: https://www.i14y.admin.ch/
- NASURE: https://www.digisante.admin.ch/de/nasure-national-surveillance-response-de
- VMDL / ELCA: https://www.elca.ch/de/news/vaccination-monitoring-data-lake-vmdl
- Airlock IAM: https://www.airlock.com/secure-access-hub/komponenten/iam
