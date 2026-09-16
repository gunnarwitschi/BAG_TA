# Objektkürzel und Beziehungen

## Zweck

Diese Dokumentation beschreibt die im technischen Architekturmodell verwendeten Objektkürzel sowie die grundlegende Beziehung zwischen den Objekttypen.

## Objektkürzel

| Kürzel | Bezeichnung | Umfang |
|---|---|---|
| **FA** | Fachanwendung | Eine fachlich abgegrenzte Anwendung bzw. ein Anwendungssystem des BAG. Dazu gehören u. a. Name, IKT-ID, EA-Pfad, Owner, Betreiber, Alias, Innovator-UUID und externe URL. |
| **TG** | Technologiegruppe | Eine technische Gruppierung innerhalb einer Fachanwendung. Sie dient zur Strukturierung und Klassifikation von Technologien und ist kein notwendiges Zwischenobjekt für die Beziehung zwischen Fachanwendung und Technologie. |
| **T** | Technologie | Ein konkreter technischer Baustein bzw. eine Technologie, z. B. LDAP, X.509, FHIR, SFTP, Angular oder SLES. Eine Technologie ist einer Technologiegruppe zugeordnet. |
| **TV** | Technologieversion | Eine konkrete Version einer Technologie, einschliesslich Lifecycle-Informationen wie End of Life, Betrieb von und Betrieb bis. Beispiel: SUSE Linux Enterprise Server 15. |
| **HP** | Herstellerprodukt | Ein konkretes Produkt eines Herstellers, das bei einer Fachanwendung eingesetzt wird bzw. dessen Einsatz dokumentiert oder recherchiert wurde. |
| **HPV** | Herstellerproduktversion | Eine konkrete Version eines Herstellerprodukts, einschliesslich Lifecycle-Informationen wie End of Life, End of Sales, End of Support sowie Betriebszeitraum. |
| **URL** | Externe URL | Eine externe Referenz zu einem Objekt, z. B. eine offizielle BAG-Seite, Produktseite oder technische Dokumentation. Die URL wird über Objekttyp und Objektschlüssel einem Objekt zugeordnet. |

## Beziehungen

Beziehungen sind kein eigener fachlicher Objekttyp mit einem Kürzel wie FA, T oder HP. Sie werden über die beteiligten Schlüssel identifiziert.

### Fachanwendung und Technologie

Die zentrale Architekturbeziehung zwischen einer Fachanwendung und einer Technologie ist **direkt**:

```text
FA-002  ── verwendet ──>  T-001
```

### Technologie und Technologiegruppe

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
