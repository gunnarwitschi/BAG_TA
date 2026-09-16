# Objektkürzel und Beziehungen

## Zweck

Diese Dokumentation beschreibt die im technischen Architekturmodell verwendeten Objektkürzel sowie die grundlegenden Beziehungen zwischen den Objekttypen.

## Objektkürzel

| Kürzel | Bezeichnung | Umfang |
|---|---|---|
| **FA** | Fachanwendung | Eine fachlich abgegrenzte Anwendung bzw. ein Anwendungssystem des BAG. Dazu gehören u. a. Name, IKT-ID, EA-Pfad, Owner, Betreiber, Alias, Innovator-UUID und externe URL. |
| **TG** | Technologiegruppe | Eine Gruppierung von Technologien. Sie dient zur Strukturierung und Klassifikation von Technologien. Die Fachanwendung ist **nicht** Teil der TG-T-Beziehung. |
| **T** | Technologie | Ein konkreter technischer Baustein bzw. eine Technologie, z. B. LDAP, X.509, FHIR, SFTP, Angular oder SLES. |
| **TV** | Technologieversion | Eine konkrete Version einer Technologie, einschliesslich Lifecycle-Informationen wie End of Life, Betrieb von und Betrieb bis. Beispiel: SUSE Linux Enterprise Server 15. |
| **HP** | Herstellerprodukt | Ein konkretes Produkt eines Herstellers, das bei einer Fachanwendung eingesetzt wird bzw. dessen Einsatz dokumentiert oder recherchiert wurde. |
| **HPV** | Herstellerproduktversion | Eine konkrete Version eines Herstellerprodukts, einschliesslich Lifecycle-Informationen wie End of Life, End of Sales, End of Support sowie Betriebszeitraum. |
| **URL** | Externe URL | Eine externe Referenz zu einem Objekt, z. B. eine offizielle BAG-Seite, Produktseite oder technische Dokumentation. Die URL wird über Objekttyp und Objektschlüssel einem Objekt zugeordnet. |

## Vollständige Liste der Technologiegruppen

Die Technologiegruppen bilden eine Strukturierungsebene für Technologien. Eine Technologiegruppe gruppiert Technologien; sie ist nicht als Zwischenobjekt zwischen Fachanwendung und Technologie zu verstehen.

| Schlüssel | Technologiegruppe |
|---|---|
| **TG-001** | Protokolle & Standards |
| **TG-002** | Protokolle & Standards |
| **TG-003** | Protokolle & Standards |
| **TG-004** | Protokolle & Datenformate |
| **TG-005** | Webserver |
| **TG-006** | Backend-Technologie |
| **TG-007** | Betriebsplattform |
| **TG-008** | Datenanalyse & Orchestrierung |
| **TG-009** | Datenbank & Storage |
| **TG-010** | Interoperabilitätsstandards |
| **TG-011** | Test- und Interoperabilitätsplattform |
| **TG-012** | Web & Cloud |
| **TG-013** | Datenübertragung |
| **TG-014** | Authentifizierung |
| **TG-015** | Datenzugriff & Integration |
| **TG-016** | Datenmodellierung |
| **TG-017** | Client |
| **TG-018** | Identity & Access Management |
| **TG-019** | Datenbank & Integration |
| **TG-020** | Interoperabilität & Cloud |
| **TG-021** | Cloud & Data Lake |
| **TG-022** | Identity & Access Management |
| **TG-023** | Datenübertragung |

## Beziehungen

Beziehungen sind kein eigener fachlicher Objekttyp mit einem Kürzel wie FA, T oder HP. Sie werden über die beteiligten Schlüssel identifiziert.

### Fachanwendung und Technologieversion

Die zentrale Architekturbeziehung ist **direkt zwischen Fachanwendung und Technologieversion**:

```text
FA-xxx  ── verwendet ──>  TV-xxx
```

Eine Fachanwendung verwendet damit eine konkrete Technologieversion. Die Technologieversion verweist auf die übergeordnete Technologie.

```text
FA-xxx  ── verwendet ──>  TV-xxx
                           │
                           └── gehört zu ──> T-xxx
```

### Technologiegruppe, Technologie und Technologieversion

Die technische Strukturierung erfolgt unabhängig von der FA-Beziehung:

```text
TG-xxx  ── gruppiert ──>  T-xxx  ── gruppiert/umfasst ──>  TV-xxx
```

Damit gilt als Modellierungsregel:

**TG gruppiert T gruppiert TV**

Die Technologiegruppe wird somit nicht benötigt, um die Beziehung einer Fachanwendung zu ihrer verwendeten Technologieversion herzustellen.

### Herstellerprodukt und Version

Analog werden Herstellerprodukte und deren Versionen getrennt modelliert:

```text
HP-xxx  ── hat Version ──>  HPV-xxx
```

### Gesamtbild

```text
                    ┌─────────────────┐
                    │ Fachanwendung   │
                    │      FA         │
                    └────────┬────────┘
                             │ verwendet
                             ▼
                    ┌─────────────────┐
                    │Technologieversion│
                    │      TV         │
                    └────────┬────────┘
                             │ gehört zu
                             ▼
                    ┌─────────────────┐
                    │  Technologie    │
                    │       T         │
                    └────────┬────────┘
                             │ gruppiert durch
                             ▼
                    ┌─────────────────┐
                    │Technologiegruppe│
                    │       TG        │
                    └─────────────────┘

                    HP ──> HPV
                    FA/T/TV/HP ──> URL
```

## Dateinamen in GitHub

Die Modellobjekte werden einzeln gespeichert:

- `fachanwendungen/FA-xxx.xml`
- `technologiegruppen/TG-xxx.xml`
- `technologien/T-xxx.xml`
- `technologieversionen/TV-xxx.xml`
- `herstellerprodukte/HP-xxx.xml`
- `herstellerproduktversionen/HPV-xxx.xml`
- `externe_urls/URL-xxx.xml`
- `beziehungen/<Von-Schlüssel>__<Zu-Schlüssel>.xml`

Beispiel einer direkten Architekturbeziehung:

`beziehungen/FA-002__TV-xxx.xml`

Die Beziehung enthält den Beziehungstyp und den Datenstatus. Die Dateistruktur macht die beteiligten Objekte unmittelbar erkennbar.
