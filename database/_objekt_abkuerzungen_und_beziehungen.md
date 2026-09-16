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

Der aktuelle Modellstand umfasst **8 konsolidierte Technologiegruppen**:

| Schlüssel | Technologiegruppe |
|---|---|
| **TG-001** | Integration & Interoperabilität |
| **TG-005** | Web & Applikation |
| **TG-007** | Plattform & Cloud |
| **TG-008** | Datenanalyse & Orchestrierung |
| **TG-009** | Datenmanagement & Storage |
| **TG-011** | Test & Validierung |
| **TG-013** | Datenübertragung |
| **TG-014** | Identity & Access Management |

### Konsolidierungen

Die bisherigen Technologiegruppen wurden auf acht fachanwendungsunabhängige Gruppen konsolidiert:

- TG-001, TG-002, TG-003, TG-004, TG-010, TG-015 und TG-020 → **TG-001 Integration & Interoperabilität**
- TG-005, TG-006 und TG-017 → **TG-005 Web & Applikation**
- TG-007, TG-012 und TG-021 → **TG-007 Plattform & Cloud**
- TG-008 → **TG-008 Datenanalyse & Orchestrierung**
- TG-009, TG-016 und TG-019 → **TG-009 Datenmanagement & Storage**
- TG-011 → **TG-011 Test & Validierung**
- TG-013 und TG-023 → **TG-013 Datenübertragung**
- TG-014, TG-018 und TG-022 → **TG-014 Identity & Access Management**

Die bestehenden Schlüssel der Zielgruppen bleiben erhalten; dadurch sind Lücken in der Nummerierung beabsichtigt. Im aktuellen Zielmodell existieren damit **8 TG**.

## Beziehungen

### Fachanwendung → Technologieversion

Die Zielbeziehung des technischen Architekturmodells ist:

```text
FA-xxx ── verwendet ──> TV-xxx
```

Im aktuellen Datenbestand existieren noch Zuordnungen **FA → T**, wenn die konkrete Version noch nicht ermittelt wurde. Diese sind als offene/temporäre Zuordnungen zu behandeln und werden bei Vorliegen der Version auf **FA → TV** umgestellt. Es werden keine Technologieversionen ohne belastbare Quelle erfunden.

### Technologiegruppe → Technologie → Technologieversion

```text
TG-xxx ── gruppiert ──> T-xxx ── gehört zu ──> TV-xxx
```

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
