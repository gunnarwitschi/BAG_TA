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

Der aktuelle Modellstand umfasst 19 konsolidierte Technologiegruppen:

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

- TG-002 + TG-003 → **TG-001**
- TG-022 → **TG-018**
- TG-023 → **TG-013**

Die bestehenden Schlüssel der Zielgruppen bleiben erhalten; dadurch sind Lücken in der Nummerierung beabsichtigt.

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
