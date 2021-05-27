---
description: Es sind fünf vordefinierte Zugriffssteuerungsgruppen verfügbar, Sie können jedoch bei Bedarf zusätzliche Gruppen erstellen und verwalten.
title: Grundlagen zu Zugangssteuerungsgruppen
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# Grundlagen zu Zugangssteuerungsgruppen{#understanding-access-control-groups}

Es sind fünf vordefinierte Zugriffssteuerungsgruppen verfügbar, Sie können jedoch bei Bedarf zusätzliche Gruppen erstellen und verwalten.

Sie können die Mitglieder jeder Zugriffskontrollgruppe sowie die Verzeichnisse definieren, auf die jede Gruppe Schreibzugriff oder Schreibzugriff hat.

Die vordefinierten Gruppen werden wie folgt definiert:

| Gruppe | Beschreibung |
|---|---|
| Administratoren | Ermöglicht Zugriff auf alle Ordner und Dateien. Die Standard-IP-Adresse ist 127.0.0.1 (lokaler Host). |
| Sensoren | Ermöglicht Zugriff auf nur die Dateien, die von [!DNL Sensor] zur Datenübertragung verwendet werden. |
| Benutzer | Ermöglicht schreibgeschützten Zugriff auf die Elemente, die für die Ausführung grundlegender Analyseaufgaben durch einen [!DNL Insight]-Benutzer erforderlich sind. |
| Power Users | Ermöglicht schreibgeschützten Zugriff auf die Elemente, die für einen [!DNL Insight]-Benutzer zur Durchführung grundlegender Analyseaufgaben erforderlich sind, sowie Lese- und Schreibzugriff auf den Ordner [!DNL Profiles] zum Ändern von Profilen. |
| Cluster-Server | Ermöglicht Zugriff auf [!DNL Insight Servers], die als Cluster-Server gekennzeichnet sind. |
| Berichtsserver | Ermöglicht Zugriff auf [!DNL Report]-Computer, die eine Verbindung zu [!DNL Insight Server] herstellen. |

Mitglieder einer Zugriffskontrollgruppe werden anhand ihrer IP-Adressen oder SSL-Zertifikatinformationen definiert.

Wenn kein SSL-Zertifikat verfügbar ist, kann eine IP-Adresse zum Definieren eines Gruppenmitglieds verwendet werden. Die typische Installation von [!DNL Insight] umfasst ein SSL-Zertifikat, während die Verwendung von Zertifikaten für [!DNL Sensor(s)] optional ist. Für [!DNL Insight Server] werden Cluster-Server mit IP-Adressen anstelle von SSL-Zertifikaten definiert.

Die folgenden Codes können zur Definition von Gruppenmitgliedern verwendet werden:

| Zugriffstypen-Code | Definition |
|---|---|
| O | Organisation |
| CN | Gebrauchsname |
| L | Örtlichkeit |
| ST | Bundesland oder Provinz |
| C | Country |
| OU | Organisationseinheit |
| E-Mail | E-Mail Adresse |
