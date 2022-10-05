---
description: Es sind fünf vordefinierte Zugriffssteuerungsgruppen verfügbar, Sie können jedoch bei Bedarf zusätzliche Gruppen erstellen und verwalten.
title: Grundlagen zu Zugangssteuerungsgruppen
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# Grundlagen zu Zugangssteuerungsgruppen{#understanding-access-control-groups}

{{eol}}

Es sind fünf vordefinierte Zugriffssteuerungsgruppen verfügbar, Sie können jedoch bei Bedarf zusätzliche Gruppen erstellen und verwalten.

Sie können die Mitglieder jeder Zugriffskontrollgruppe sowie die Verzeichnisse definieren, auf die jede Gruppe Schreibzugriff oder Schreibzugriff hat.

Die vordefinierten Gruppen werden wie folgt definiert:

| Gruppe | Beschreibung |
|---|---|
| Administratoren | Ermöglicht Zugriff auf alle Ordner und Dateien. Die Standard-IP-Adresse ist 127.0.0.1 (lokaler Host). |
| Sensoren | Ermöglicht Zugriff auf nur die Dateien, die von [!DNL Sensor] zur Datenübertragung. |
| Benutzer | Ermöglicht schreibgeschützten Zugriff auf die Elemente, die für eine [!DNL Insight] Benutzer , um grundlegende Analyseaufgaben durchzuführen. |
| Power Users | Ermöglicht schreibgeschützten Zugriff auf die Elemente, die für eine [!DNL Insight] Benutzer zur Durchführung grundlegender Analyseaufgaben sowie Lese- und Schreibzugriff auf die [!DNL Profiles] Ordner zum Ändern von Profilen. |
| Cluster-Server | Ermöglicht Zugriff auf [!DNL Insight Servers] die als Cluster-Server bezeichnet werden. |
| Berichtsserver | Ermöglicht Zugriff auf [!DNL Report] Maschinen, die eine Verbindung zu [!DNL Insight Server]. |

Mitglieder einer Zugriffskontrollgruppe werden anhand ihrer IP-Adressen oder SSL-Zertifikatinformationen definiert.

Wenn kein SSL-Zertifikat verfügbar ist, kann eine IP-Adresse zum Definieren eines Gruppenmitglieds verwendet werden. Die typische Installation von [!DNL Insight] enthält ein SSL-Zertifikat, während die Verwendung von Zertifikaten für [!DNL Sensor(s)] ist optional. Für [!DNL Insight Server], werden Cluster-Server mit IP-Adressen anstelle von SSL-Zertifikaten definiert.

Die folgenden Codes können zur Definition von Gruppenmitgliedern verwendet werden:

| Zugriffstypen-Code | Definition |
|---|---|
| O | Organisation |
| CN | Gebrauchsname |
| L | Örtlichkeit |
| ST | Bundesland oder Provinz |
| C  | Country |
| OU | Organisationseinheit |
| E-Mail | E-Mail Adresse |
