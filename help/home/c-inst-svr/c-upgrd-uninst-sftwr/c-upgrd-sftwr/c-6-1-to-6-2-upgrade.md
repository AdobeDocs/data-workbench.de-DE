---
description: Aktualisieren von Serverkomponenten für Data Workbenchs 6.2 und 6.2.2
title: DWB-Server-Upgrade 6.1 auf 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 18%

---

# DWB-Server-Upgrade: 6.1 auf 6.2{#dwb-server-upgrade-to}

Aktualisieren von Serverkomponenten für Data Workbenchs 6.2 und 6.2.2

## Aktualisierungsprobleme für 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Das Attributionsprofil ist für Benutzer konfiguriert, die das Adobe SC-Profil implementiert haben, um den Analytics (SC/Insight)-Daten-Feed zu verwenden. Standardmäßig werden die Marketing- und Konversionsereignisse als Standardinteraktionen verwendet, die in den regelbasierten Modellen ausgewertet werden. Weitere Informationen finden Sie unter [Bereitstellen des Attributionsprofils](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en) .
* Wenn Sie für Benutzer des Adobe SC-Profils, die auf Data Workbench 6.2 aktualisieren, nicht die Standardkonfigurationen verwenden, überprüfen Sie, ob der [!DNL x-bot_id]-Wert in der [!DNL SC Fields.cfg]-Datei ordnungsgemäß dekodiert wird und das [!DNL x-bot_id]-Feld ordnungsgemäß in den Dateien [!DNL Decoding Instructions.cfg] und [!DNL Exclude Hit.cfg] aufgeführt ist. Dies ist nur dann ein Problem, wenn Sie die Konfigurationsdatei aus der Standardkonfiguration geändert haben.
* Wenn Sie nicht verwendete Felder in der Datei [!DNL Dataset > Log Processing > SC Fields.cfg] für das Adobe SC-Profil gelöscht haben, müssen Sie aktualisieren, um die aktualisierten Feldwerte für das Attributionsprofil aufzunehmen (siehe [Bereitstellen des Attributionsprofils](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)).

## Aktualisierungsprobleme für 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* Die Lookup-Dateien **[!UICONTROL Browsers]** und **[!UICONTROL Operating Systems]** werden nicht im alten **[!UICONTROL Traffic]**-Profil aktualisiert (z. B. [!DNL Lookups\Traffic\Browsers.txt)]. Stattdessen verwendet die Konfiguration des Profils **[!UICONTROL Traffic]** das DeviceAtlas-Bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]), um diese Konfigurationsinformationen bereitzustellen.
* Data Workbench 6.2.1 ist die letzte Version, die einen Download der 32-Bit-Clientanwendung umfasst. Alle zukünftigen Clientanwendungs-Downloads werden 64-Bit sein und Windows 7 oder höher erfordern. Die Speicherbeschränkungen der 32-Bit-Anwendung werden mit Einführung der 64-Bit-Anwendung ab Version 6.1 behoben.

>[!NOTE]
>
>Bei der 32-Bit-Version der Data Workbench Client-Anwendung können bei der Ausführung von Prognosemodellen mit Clustering- und Scoring-Funktionen potenzielle Probleme im Zusammenhang mit Speicherbeschränkungen auftreten.
