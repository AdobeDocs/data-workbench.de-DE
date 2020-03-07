---
description: Das Dashboard erfordert bestimmte schreibgeschützte Berechtigungen, um auf Ihre Daten in der Datenbasis zugreifen und diese anzeigen zu können. Schreibberechtigungen sind nicht erforderlich.
solution: Analytics
title: Zugriffssteuerung konfigurieren
topic: Data workbench
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zugriffssteuerung konfigurieren{#configuring-access-control}

Das Dashboard erfordert bestimmte schreibgeschützte Berechtigungen, um auf Ihre Daten in der Datenbasis zugreifen und diese anzeigen zu können. Schreibberechtigungen sind nicht erforderlich.

Die Konfiguration der Zugriffssteuerung umfasst das Bearbeiten Ihrer [!DNL Access Control.cfg] Datei im/in FSU(s) und das Hinzufügen einer neuen Gruppe, um dem Data Workbench-Dashboard Zugriffsrechte zu erteilen:

1. Bearbeiten Sie die [!DNL AccessControl.cfg] Datei (vorzugsweise mithilfe der Data Workbench-Workstation).
1. Erstellen Sie eine neue Gruppe mit dem Namen *Insight Dashboard Access*.
1. Fügen Sie unter den Mitgliedern dieser Gruppe die entsprechende KN hinzu, die Sie zu diesem Zweck erhalten haben (Beispiel: CN:INSIGHT-USER01). Wenden Sie sich an den Adobe-Kundendienst, wenn Sie diese KN erhalten möchten.
1. Ändern Sie die Liste unter dem schreibgeschützten Zugriff dieser Gruppe so, dass sie Folgendes widerspiegelt:

* /Profile/$
* /Profile/
* /Adressen
* /Status/
* /Benutzer/$

1. Entfernen Sie alle Elemente aus dem Bereich für den Lese-/Schreibzugriff, da keine Schreibberechtigungen für das Dashboard erforderlich sind.
1. Speichern Sie die Änderungen an der [!DNL AccessControl.cfg] Datei auf dem Server, damit die Berechtigungen wirksam werden.
