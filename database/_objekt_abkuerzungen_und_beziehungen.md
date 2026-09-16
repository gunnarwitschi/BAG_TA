# Objektkürzel und Beziehungen

## Zweck

Diese Dokumentation beschreibt die im technischen Architekturmodell verwendeten Objektkürzel sowie die grundlegenden Beziehungen zwischen den Objekttypen.

## Objektkürzel

| Kürzel | Bezeichnung | Umfang |
|---|---|---|
| **FA** | Fachanwendung | Eine fachlich abgegrenzte Anwendung bzw. ein Anwendungssystem des BAG. |
| **TG** | Technologiegruppe | Eine Gruppierung von Technologien. Sie dient zur Strukturierung und Klassifikation von Technologien. |
| **T** | Technologie | Ein konkreter technischer Baustein bzw. eine Technologie. |
| **TV** | Technologieversion | Eine konkrete Version einer Technologie, einschliesslich Lifecycle-Informationen. |
| **HP** | Herstellerprodukt | Ein konkretes Produkt eines Herstellers, das bei einer Fachanwendung eingesetzt wird bzw. dessen Einsatz dokumentiert oder recherchiert wurde. |
| **HPV** | Herstellerproduktversion | Eine konkrete Version eines Herstellerprodukts, einschliesslich Lifecycle-Informationen. |
| **URL** | Externe URL | Eine externe Referenz zu einem Objekt, z. B. eine offizielle BAG-Seite, Produktseite oder technische Dokumentation. |

## Technologiegruppen

Die Technologiegruppen sind fachanwendungsunabhängig. Gleichartige Gruppen werden nur einmal geführt und können Technologien aus mehreren Fachanwendungen gruppieren.

| Schlüssel | Technologiegruppe |
|---|---|
| **TG-001** | Protokolle & Standards |
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

### Konsolidierungen

Identische Technologiegruppen wurden zusammengeführt:

- TG-002 und TG-003 → **TG-001 Protokolle & Standards**
- TG-022 → **TG-018 Identity & Access Management**
- TG-023 → **TG-013 Datenübertragung**

Die bestehenden Schlüssel der bereits etablierten Gruppen bleiben erhalten.

## Beziehungen

### Fachanwendung und Technologieversion

```text
FA-xxx ── verwendet ──> TV-xxx
```

Eine Fachanwendung verwendet eine konkrete Technologieversion.

### Technologiegruppe, Technologie und Technologieversion

```text
TG-xxx ── gruppiert ──> T-xxx ── hat Version ──> TV-xxx
```

Damit gilt die Modellierungsregel:

**TG gruppiert T gruppiert TV**

Die Technologiegruppe ist kein Zwischenobjekt zwischen Fachanwendung und Technologieversion.

### Herstellerprodukt und Version

```text
HP-xxx ── hat Version ──> HPV-xxx
```

### Dateinamen in GitHub

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
