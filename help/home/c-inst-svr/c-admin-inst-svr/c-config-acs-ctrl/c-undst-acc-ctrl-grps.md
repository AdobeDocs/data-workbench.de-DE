---
description: Es sind fünf vordefinierte Zugriffskontrollgruppen verfügbar, Sie können jedoch bei Bedarf weitere Gruppen erstellen und verwalten.
solution: Insight
title: Zugriffssteuerungsgruppen
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zugriffssteuerungsgruppen{#understanding-access-control-groups}

Es sind fünf vordefinierte Zugriffskontrollgruppen verfügbar, Sie können jedoch bei Bedarf weitere Gruppen erstellen und verwalten.

Sie können die Mitglieder jeder Zugriffskontrollgruppe sowie die Ordner definieren, auf die jede Gruppe Schreibzugriff oder Schreibzugriff hat.

Die vordefinierten Gruppen werden wie folgt definiert:

| Gruppe | Beschreibung |
|---|---|
| Administratoren | Ermöglicht den Zugriff auf alle Ordner und Dateien. Die Standard-IP-Adresse ist 127.0.0.1 (lokaler Host). |
| Sensoren | Ermöglicht den Zugriff nur auf die Dateien, die zur Datenübertragung verwendet [!DNL Sensor] werden. |
| Benutzer | Ermöglicht schreibgeschützten Zugriff auf die Elemente, die ein [!DNL Insight] Benutzer zur Durchführung grundlegender Analyseaufgaben benötigt. |
| Power-Benutzer | Ermöglicht schreibgeschützten Zugriff auf die Elemente, die ein [!DNL Insight] Benutzer zur Durchführung grundlegender Analyseaufgaben benötigt, sowie Lese- und Schreibzugriff auf den [!DNL Profiles] Ordner zum Ändern von Profilen. |
| Clusterserver | Ermöglicht Zugriff auf [!DNL Insight Servers] die als Cluster-Server ausgewiesenen Server. |
| Berichtsserver | Ermöglicht den Zugriff auf [!DNL Report] Computer, die eine Verbindung zum [!DNL Insight Server]System herstellen. |

Mitglieder einer Zugriffskontrollgruppe werden mithilfe ihrer IP-Adressen oder SSL-Zertifikatinformationen definiert.

Wenn kein SSL-Zertifikat verfügbar ist, kann eine IP-Adresse verwendet werden, um ein Gruppenmitglied zu definieren. Die typische Installation von [!DNL Insight] enthält ein SSL-Zertifikat, während die Verwendung von Zertifikaten für [!DNL Sensor(s)] optional ist. Cluster-Server [!DNL Insight Server]werden beispielsweise mit IP-Adressen anstelle von SSL-Zertifikaten definiert.

Die folgenden Codes können zur Definition von Gruppenmitgliedern verwendet werden:

| Zugriffsart-Code | Definition |
|---|---|
| O | Organisation |
| CN | Allgemeiner Name |
| L | Örtlichkeit |
| ST | Bundesland oder Bundesland |
| C | Land |
| OU | Referat &quot;Organisation&quot; |
| E-Mail | E-Mail-Adresse |

