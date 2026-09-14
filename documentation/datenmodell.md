# Datenmodell

## Identifikation

Jedes Objekt besitzt einen stabilen internen Schlüssel. Fachanwendungen verwenden `FA-001` … `FA-084`. Die ursprüngliche `IKT_ID` wird zusätzlich gespeichert und nicht als Primärschlüssel verwendet.

## Beziehungen

Referenzen werden über die internen Schlüssel geführt. Dadurch bleiben Beziehungen auch bei Änderungen an Namen oder IKT_IDs stabil.

## Lifecycle

Für Technologie- und Herstellerproduktversionen werden die Attribute für End of Life, End of Sales, End of Support sowie Betriebsbeginn/-ende separat geführt.

Ein Lifecycle-Datum darf nur dann als tatsächlicher BAG-Lifecycle interpretiert werden, wenn die betreffende Version und deren Einsatz bei der BAG belegt sind.

## Quellenstatus

Der Datenstatus unterscheidet insbesondere belegte Angaben, öffentliche Recherche, geplante Zielarchitektur und offene Punkte. Öffentliche Herstellerdokumentation wird nicht mit einer installierten BAG-Version gleichgesetzt.
