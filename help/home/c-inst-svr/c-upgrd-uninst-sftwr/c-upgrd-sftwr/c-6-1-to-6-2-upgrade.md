---
description: Aktualisieren von Serverkomponenten für Data Workbench 6.2 und 6.2.2
title: DWB Server-Upgrade 6.1 auf 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# DWB Server-Aktualisierung: 6.1 bis 6.2{#dwb-server-upgrade-to}

Aktualisieren von Serverkomponenten für Data Workbench 6.2 und 6.2.2

## Aktualisierungsfehler für 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Das Zuordnungsprofil ist für Benutzer konfiguriert, die das Adobe SC-Profil implementiert haben, um den Analytics-(SC/Insight-)Datenfeed zu verwenden. Standardmäßig werden die Marketing- und Umrechnungsereignisse als Standardinteraktionen verwendet, die in den regelbasierten Modellen ausgewertet werden. Weitere Informationen finden Sie unter [Bereitstellen des Zuordnungsprofils](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html) .
* Wenn Sie für Benutzer des Adobe SC-Profilupdates auf Data Workbench 6.2 nicht die Standardkonfigurationen verwenden, überprüfen Sie, ob der [!DNL x-bot_id] Wert in der [!DNL SC Fields.cfg] Datei korrekt dekodiert wird und ob das [!DNL x-bot_id] Feld ordnungsgemäß in den [!DNL Decoding Instructions.cfg] und den [!DNL Exclude Hit.cfg] Dateien aufgeführt wird. Dies ist nur dann ein Problem, wenn Sie die Konfigurationsdatei aus der Standardkonfiguration geändert haben.
* Wenn Sie nicht verwendete Felder in der [!DNL Dataset > Log Processing > SC Fields.cfg] Datei für das Adobe SC-Profil gelöscht haben, müssen Sie die aktualisierten Feldwerte für das Zuordnungsprofil aktualisieren (siehe [Bereitstellen des Zuordnungsprofils](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html)).

## Aktualisierungsfehler für 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* Die Dateien **[!UICONTROL Browsers]** und **[!UICONTROL Operating Systems]** Lookup werden nicht im alten **[!UICONTROL Traffic]** Profil aktualisiert (z. B. [!DNL Lookups\Traffic\Browsers.txt)]). Instead, configuration of the **[!UICONTROL Traffic]** profile will utilize the DeviceAtlas bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) to provide this configuration information.
* Data Workbench 6.2.1 ist die letzte Version, die einen Download der 32-Bit-Clientanwendung umfasst. Alle zukünftigen Clientanwendungs-Downloads werden 64-Bit sein und Windows 7 oder höher erfordern. Die Speicherbeschränkungen der 32-Bit-Anwendung werden mit Einführung der 64-Bit-Anwendung ab Version 6.1 behoben.

>[!NOTE]
>
>Bei der 32-Bit-Version der Data Workbench-Clientanwendung treten möglicherweise Probleme im Zusammenhang mit Speicherbeschränkungen auf, wenn Prognosemodelle mit den Clustering- und Bewertungsfunktionen ausgeführt werden.

