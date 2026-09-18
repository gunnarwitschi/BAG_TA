# Abgleich mit BAG-DT/bag-arch-inventory

Stand der Zusatzquelle: 2026-09-01.

## Zweck

Das Repository `BAG-DT/bag-arch-inventory` wird als zusätzliche Quelle für die technische Architektur des BAG verwendet. Es verbindet Fachanwendungen mit Betriebsbeständen aus SGC, Atlantica/Azure und weiteren BIT-Quellen.

Die Quelle wird nicht als Ersatz für das BAG-TA-Modell verwendet. Sie liefert insbesondere technische Betriebsnachweise und konkrete Ausprägungen.

## Abgleich mit BAG-TA

Der PFCT/IKT-Schlüssel erlaubt einen belastbaren Abgleich, soweit beide Modelle dieselbe PFCT-ID führen. Zusätzlich bestehen Namensgleichheiten, die nur als Kandidaten und nicht automatisch als Identität behandelt werden.

Die Quelle enthält 69 Fachanwendungen (einschliesslich Cluster). Das BAG-TA-Modell enthält 84 Fachanwendungen. Die Nummernkreise sind daher nicht direkt vergleichbar.

## Belastbar zuordenbare technische Ergänzungen

| BAG-TA | PFCT | Befund aus bag-arch-inventory |
|---|---:|---|
| FA-001 Abfragedienste EPGD | 24240 | Windows Server 2019 virtuell |
| FA-009 BAGSAN | 23908 | Windows Server 2019 virtuell; SUSE Linux Enterprise Server |
| FA-012 Dashboard Krankenversicherung | 30630 | Azure Subscription bag-kvd-prd; Container Apps, PostgreSQL Flexible Server, Key Vault, Storage, Static Web Site, Load Balancer, VM Scale Set, Monitoring/Security |
| FA-015 BetmG | 22760 | MS SQL Server 2019; Windows Server 2019 virtuell |
| FA-021 Elektronische Plattform Leistungen | 28145 | Azure Subscription bag-epb-prd; Container Apps/Jobs, PostgreSQL Flexible Server, Key Vault, Storage, Monitoring/Security |
| FA-036 ePGU MeCanna-BetmG | 28343 | Azure Security Automation im ePGU-Umfeld |
| FA-039 ePGU Radonportal | 25796 | Azure Subscription bag-radon-prd; Container Apps, PostgreSQL Flexible Server, Key Vault, Storage, Monitoring/Security |
| FA-047 Harvester | 28593 | Linux Server SLES 15 nRZ; Linux Server SLES 15 virtuell (ADB Anbindung) |
| FA-054 ISAK | 20444 | MS SQL Server 2016; Windows Server 2016 virtuell |
| FA-059 IT-Architektur KRG | 27930 | Azure Subscription bag-cr-prd; zusätzlich AD Gruppe und Keycloak Realm |
| FA-066 SOAS | 8652 | MS SQL Server 2016/2022; Windows Server 2016/2022 nRZ |

## Modellierungsentscheidungen

- Konkrete Windows-/SQL-Versionen werden als Technologieversionen modelliert.
- Microsoft SQL Server nutzt die bereits bestehende Technologie T-022.
- Microsoft Windows Server wurde als neue Technologie T-049 mit TV-002 bis TV-004 angelegt.
- PostgreSQL wurde als neue Technologie T-051 mit TV-008 (PostgreSQL 17) angelegt, weil die bestehende BAG-TA-Datenbasis dafür bisher keinen eigenen Technologie-Knoten enthielt.
- Microsoft Azure bleibt T-046; die einzelnen Azure-Ressourcentypen werden nicht ungeprüft als eigene BAG-TA-Technologien übernommen.
- SLES 15 verwendet die bereits bestehende Technologie T-019 und TV-001.
- Herstellerprodukt und Technologie bleiben getrennt.

## Neue Beziehungen

Aus dem Betriebsbestand wurden FA→T bzw. FA→TV Beziehungen ergänzt. Die Quelle ist im Datenstatus der Beziehung als `BAG-DT/bag-arch-inventory` gekennzeichnet.

## Wichtige Einschränkungen

Die Azure-Ressourcentypen sind Betriebsbestandsdaten. Eine Ressource wie `Azure app/containerapps` beweist die Nutzung eines Azure-Dienstes, ist aber nicht automatisch eine fachliche Technologie im Sinne des BAG-TA-Metamodells.

Die Quelle enthält ausserdem Anwendungen, die im aktuellen BAG-TA-84er-Anker nicht enthalten sind, beispielsweise BAG-ISAK-Relaunch, BAG-Krebsregister, BAG-PlatformServices und BAG-DataHub. Diese werden nicht automatisch als neue Fachanwendungen in den 84er-Anker aufgenommen.

Bei APVS/RPC, MedReg und anderen mehrfach oder unterschiedlich geschnittenen Anwendungen bestehen bewusst offene Zuordnungen. Insbesondere darf die gemeinsame PFCT-ID 20326 nicht zur Verschmelzung von APVS und RPC führen.

## Quelle

BAG-DT/bag-arch-inventory, Branch `main`, Stand 2026-09-01.
