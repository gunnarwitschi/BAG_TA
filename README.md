# BAG Technische Architektur – Fachanwendungen

Strukturierte XML-Datenbank der für die technische Architektur der BAG-Fachanwendungen erhobenen Informationen.

## Grundlage

Ausgangspunkt ist **„Fachanwendungen L1“, Version 1.0 Proposed, generiert am 14.09.2026**.

Die Daten wurden für die weitere technische Architekturarbeit normalisiert:

- 84 Fachanwendungen
- Primärschlüssel: `FA-001` bis `FA-084`
- `IKT_ID` bleibt als sekundärer Schlüssel erhalten, sofern vorhanden
- 22 Technologiegruppen
- 47 Technologien
- 1 belegte Technologieversion
- 14 Herstellerprodukte
- aktuell keine verifizierten Herstellerproduktversionen
- 77 externe URLs
- 62 Beziehungen

## Datenqualität

Es werden technische Angaben nicht erfunden. Wenn eine Technologie, Produktzuordnung oder Version nicht durch die zugrunde liegenden Quellen belegt werden konnte, bleibt sie offen bzw. ist entsprechend als Datenstatus gekennzeichnet.

Insbesondere wird eine aktuelle Hersteller-Version **nicht automatisch als installierte BAG-Version interpretiert**.

Geplante Technologien werden als geplant gekennzeichnet und nicht als produktiver Ist-Zustand dargestellt.

## XML-Struktur

| Datei | Inhalt |
|---|---|
| `database/fachanwendungen.xml` | Fachanwendungen inkl. IKT_ID, Owner, Betreiber, Notizen und URL |
| `database/technologiegruppen.xml` | Gruppierung Technologien |
| `database/technologien.xml` | Technologien |
| `database/technologieversionen.xml` | belegte Technologieversionen inkl. Lifecycle |
| `database/herstellerprodukte.xml` | Herstellerprodukte |
| `database/herstellerproduktversionen.xml` | Herstellerproduktversionen |
| `database/externe_urls.xml` | URLs für alle relevanten Objekttypen |
| `database/beziehungen.xml` | Beziehungen zwischen Architektur-Objekten |
| `database/schritt2_abdeckung.xml` | Abdeckung und offene Punkte |

Das XML-Modell verwendet UTF-8 und ist für eine spätere Weiterverarbeitung bzw. Transformation in andere EA- oder Repository-Formate vorgesehen.
