# Objektkürzel und Beziehungen

## Zweck

Diese Dokumentation beschreibt die im technischen Architekturmodell verwendeten Objektkürzel sowie die grundlegenden Beziehungen zwischen den Objekttypen.

## Metamodell – Kernregel

Die Fachanwendung wird direkt mit der verwendeten Technologieversion verbunden:

```text
FA ── verwendet ──> TV
                    │
                    └── gehört zu ──> T
                                      │
TG ── gruppiert ──────────────────────┘
```

Damit gilt:
- **FA verwendet TV**
- **TG gruppiert T**
- **T gehört zu TV**
- **TG ist fachanwendungsunabhängig**

Die Technologiegruppe ist **kein Zwischenobjekt zwischen FA und T bzw. TV**.

## Objektkürzel

| Kürzel | Bezeichnung |
|---|---|
| **FA** | Fachanwendung |
| **TG** | Technologiegruppe |
| **T** | Technologie |
| **TV** | Technologieversion |
| **HP** | Herstellerprodukt |
| **HPV** | Herstellerproduktversion |
| **URL** | Externe URL |

## Technologiegruppen

Der aktuelle Modellstand umfasst **19 konsolidierte Technologiegruppen**. Die bestehenden Schlüssel der Zielgruppen bleiben erhalten; dadurch sind Lücken in der Nummerierung beabsichtigt.

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

Folgende bisherige Technologiegruppen wurden konsolidiert:

- TG-002 + TG-003 → **TG-001 Protokolle & Standards**
- TG-022 → **TG-018 Identity & Access Management**
- TG-023 → **TG-013 Datenübertragung**

Die übrigen 16 Technologiegruppen bleiben mit ihrem bestehenden Schlüssel bestehen. Die vier nicht mehr benötigten TG-Schlüssel **TG-002, TG-003, TG-022 und TG-023** werden nicht weiter als eigenständige Technologiegruppen geführt.

## Beziehungen

### Fachanwendung → Technologieversion

Die Zielbeziehung des technischen Architekturmodells ist:

```text
FA-xxx ── verwendet ──> TV-xxx
```

Im aktuellen Datenbestand können noch Zuordnungen **FA → T** bestehen, wenn die konkrete Technologieversion noch nicht ermittelt wurde. Diese sind als offene/temporäre Zuordnungen zu behandeln und werden bei Vorliegen einer belastbaren Version auf **FA → TV** umgestellt. Es werden keine Technologieversionen ohne belastbare Quelle erfunden.

### Technologiegruppe → Technologie → Technologieversion

```text
TG-xxx ── gruppiert ──> T-xxx ── gehört zu ──> TV-xxx
```

Die TG ist dabei unabhängig von der Fachanwendung. Eine Technologie kann von mehreren Fachanwendungen verwendet werden und wird trotzdem nur einmal unter einer Technologiegruppe geführt.

### Herstellerprodukte

Für Herstellerprodukte gilt analog:

```text
FA-xxx ── verwendet ──> HP-xxx
HP-xxx ── gehört zu ──> HPV-xxx
```

Eine direkte FA→HP-Beziehung kann solange bestehen, wie die konkrete Produktversion nicht ermittelt ist.

## Dateinamen in GitHub

- `fachanwendungen/FA-xxx.xml`
- `technologiegruppen/TG-xxx.xml`
- `technologien/T-xxx.xml`
- `technologieversionen/TV-xxx.xml`
- `herstellerprodukte/HP-xxx.xml`
- `herstellerproduktversionen/HPV-xxx.xml`
- `externe_urls/URL-xxx.xml`
- `beziehungen/<Von-Schlüssel>__<Zu-Schlüssel>.xml`

Quelle des aktuellen Datenstands: Arbeitsmodell Excel `Fachanwendungen_L1_Schritt2_Technische_Architektur_2026-09-16_TG_konsolidiert.xlsx`.
