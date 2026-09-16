# Objektkürzel und Beziehungen

## Zweck

Diese Dokumentation beschreibt die im technischen Architekturmodell verwendeten Objektkürzel sowie die grundlegenden Beziehungen zwischen den Objekttypen.

## Objektkürzel

| Kürzel | Bezeichnung | Umfang |
|---|---|---|
| **FA** | Fachanwendung | Eine fachlich abgegrenzte Anwendung bzw. ein Anwendungssystem des BAG. Dazu gehören u. a. Name, IKT-ID, EA-Pfad, Owner, Betreiber, Alias, Innovator-UUID und externe URL. |
| **TG** | Technologiegruppe | Eine Gruppierung von Technologien innerhalb einer Fachanwendung. Sie dient zur Strukturierung und Klassifikation von Technologien. Sie ist kein notwendiges Zwischenobjekt für die Beziehung zwischen Fachanwendung und Technologie. |
| **T** | Technologie | Ein konkreter technischer Baustein bzw. eine Technologie, z. B. LDAP, X.509, FHIR, SFTP, Angular oder SLES. Eine Technologie ist einer Technologiegruppe zugeordnet. |
| **TV** | Technologieversion | Eine konkrete Version einer Technologie, einschliesslich Lifecycle-Informationen wie End of Life, Betrieb von und Betrieb bis. Beispiel: SUSE Linux Enterprise Server 15. |
| **HP** | Herstellerprodukt | Ein konkretes Produkt eines Herstellers, das bei einer Fachanwendung eingesetzt wird bzw. dessen Einsatz dokumentiert oder recherchiert wurde. |
| **HPV** | Herstellerproduktversion | Eine konkrete Version eines Herstellerprodukts, einschliesslich Lifecycle-Informationen wie End of Life, End of Sales, End of Support sowie Betriebszeitraum. |
| **URL** | Externe URL | Eine externe Referenz zu einem Objekt, z. B. eine offizielle BAG-Seite, Produktseite oder technische Dokumentation. Die URL wird über Objekttyp und Objektschlüssel einem Objekt zugeordnet. |

## Vollständige Liste der Technologiegruppen

Die folgende Liste entspricht dem aktuellen Excel-Arbeitsmodell. Die Technologiegruppen sind jeweils einer Fachanwendung zugeordnet.

| Schlüssel | Fachanwendung | Technologiegruppe |
|---|---|---|
| **TG-001** | FA-002 | Protokolle & Standards |
| **TG-002** | FA-003 | Protokolle & Standards |
| **TG-003** | FA-004 | Protokolle & Standards |
| **TG-004** | FA-005 | Protokolle & Datenformate |
| **TG-005** | FA-010 | Webserver |
| **TG-006** | FA-011 | Backend-Technologie |
| **TG-007** | FA-020 | Betriebsplattform |
| **TG-008** | FA-020 | Datenanalyse & Orchestrierung |
| **TG-009** | FA-020 | Datenbank & Storage |
| **TG-010** | FA-021 | Interoperabilitätsstandards |
| **TG-011** | FA-025 | Test- und Interoperabilitätsplattform |
| **TG-012** | FA-051 | Web & Cloud |
| **TG-013** | FA-054 | Datenübertragung |
| **TG-014** | FA-054 | Authentifizierung |
| **TG-015** | FA-062 | Datenzugriff & Integration |
| **TG-016** | FA-062 | Datenmodellierung |
| **TG-017** | FA-062 | Client |
| **TG-018** | FA-066 | Identity & Access Management |
| **TG-019** | FA-067 | Datenbank & Integration |
| **TG-020** | FA-073 | Interoperabilität & Cloud |
| **TG-021** | FA-074 | Cloud & Data Lake |
| **TG-022** | FA-077 | Identity & Access Management |
| **TG-023** | FA-063 | Datenübertragung |

## Beziehungen

Beziehungen sind kein eigener fachlicher Objekttyp mit einem Kürzel wie FA, T oder HP. Sie werden über die beteiligten Schlüssel identifiziert.

### Fachanwendung und Technologie

Die zentrale Architekturbeziehung zwischen einer Fachanwendung und einer Technologie ist **direkt**:

```text
FA-002  ── verwendet ──>  T-001
```

Die Technologiegruppe ist **kein Zwischenknoten**:

```text
FA-002  ──> TG-001 ──> T-001    # nicht als Architekturbeziehung verwenden
```

Stattdessen gilt:

```text
FA-002  ── verwendet ──>  T-001
                              │
                              └── gehört zu ──> TG-001
```

Damit kann direkt beantwortet werden, welche Technologien eine Fachanwendung verwendet. Die Technologiegruppe dient zusätzlich zur Strukturierung der Technologien.

### Technologie und Technologieversion

Eine Technologie kann konkrete Versionen haben:

```text
T-019  ── hat Version ──>  TV-001
```

Beispiel:

```text
T-019   SUSE Linux Enterprise Server
TV-001  SUSE Linux Enterprise Server 15
```

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
                                  │
                                  │ verwendet
                                  ▼
                         ┌─────────────────┐
                         │  Technologie    │
                         │       T         │
                         └───────┬─────────┘
                                 │
                     gehört zu   │
                                 ▼
                         ┌─────────────────┐
                         │ Technologiegruppe│
                         │       TG        │
                         └─────────────────┘

                         T ──> TV
                         HP ──> HPV
                         FA/T/HP ──> URL
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

Beispiel einer direkten Beziehung:

`beziehungen/FA-002__T-001.xml`

Die Beziehung enthält den Beziehungstyp und den Datenstatus. Die Dateistruktur macht die beteiligten Objekte unmittelbar erkennbar.
