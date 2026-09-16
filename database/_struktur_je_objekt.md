# Datenbankstruktur

Jedes Modellobjekt wird als eigene XML-Datei gespeichert.

- fachanwendungen/FA-xxx.xml
- technologiegruppen/TG-xxx.xml
- technologien/T-xxx.xml
- technologieversionen/TV-xxx.xml
- herstellerprodukte/HP-xxx.xml
- herstellerproduktversionen/HPV-xxx.xml
- externe_urls/URL-xxx.xml
- beziehungen/<Von>__<Zu>.xml

## Modellierungsregel für Technologie und Version

Die Fachanwendung kann zunächst direkt mit einer Technologie verbunden werden, wenn die konkrete Version noch nicht bekannt ist:

`FA → T`

Sobald die verwendete Technologieversion ermittelt wurde, wird die Beziehung auf die Version umgehängt:

`FA → TV`

Dabei wird für dieselbe Verwendung nicht gleichzeitig `FA → T` und `FA → TV` geführt.

## Modellierungsregel für Herstellerprodukt und Version

Analog kann die Fachanwendung zunächst direkt mit einem Herstellerprodukt verbunden werden, wenn die konkrete Produktversion noch nicht bekannt ist:

`FA → HP`

Sobald die verwendete Herstellerproduktversion ermittelt wurde, wird die Beziehung auf die Version umgehängt:

`FA → HPV`

Auch hier wird für dieselbe Verwendung nicht gleichzeitig `FA → HP` und `FA → HPV` geführt.

## Gruppierung und Versionierung

Die Technologiegruppen sind fachanwendungsunabhängig. Die hierarchische Modellierung lautet:

`TG → T → TV`

Die Technologiegruppe ist kein Zwischenobjekt zwischen Fachanwendung und Technologie bzw. Technologieversion.

Quelle des aktuellen Modellstands: Excel-Arbeitsmodell 2026-09-15.