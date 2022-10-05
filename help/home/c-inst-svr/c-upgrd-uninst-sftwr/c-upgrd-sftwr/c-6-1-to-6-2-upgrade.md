---
description: Aktualisieren von Serverkomponenten für Data Workbenchs 6.2 und 6.2.2
title: DWB-Server-Upgrade 6.1 auf 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 18%

---

# DWB-Server-Upgrade: 6.1 auf 6.2{#dwb-server-upgrade-to}

{{eol}}

Aktualisieren von Serverkomponenten für Data Workbenchs 6.2 und 6.2.2

## Aktualisierungsprobleme für 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Das Attributionsprofil ist für Benutzer konfiguriert, die das Adobe SC-Profil implementiert haben, um den Analytics (SC/Insight)-Daten-Feed zu verwenden. Standardmäßig werden die Marketing- und Konversionsereignisse als Standardinteraktionen verwendet, die in den regelbasierten Modellen ausgewertet werden. Siehe [Bereitstellen des Attributionsprofils](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en) für weitere Informationen.
* Wenn Sie für Benutzer des Adobe SC-Profils, die auf Data Workbench 6.2 aktualisieren, nicht die Standardkonfigurationen verwenden, überprüfen Sie, ob die Variable [!DNL x-bot_id] Wert in [!DNL SC Fields.cfg] ordnungsgemäß dekodiert und die [!DNL x-bot_id] -Feld ordnungsgemäß im [!DNL Decoding Instructions.cfg] und [!DNL Exclude Hit.cfg] Dateien. Dies ist nur dann ein Problem, wenn Sie die Konfigurationsdatei aus der Standardkonfiguration geändert haben.
* Wenn Sie nicht verwendete Felder in der [!DNL Dataset > Log Processing > SC Fields.cfg] für das Adobe SC-Profil, müssen Sie aktualisieren, um die aktualisierten Feldwerte für das Attributionsprofil aufzunehmen (siehe [Bereitstellen des Attributionsprofils](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)).

## Aktualisierungsprobleme für 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* Die **[!UICONTROL Browsers]** und **[!UICONTROL Operating Systems]** Lookup-Dateien werden im Rahmen der alten Version nicht aktualisiert **[!UICONTROL Traffic]** profile (z. B. [!DNL Lookups\Traffic\Browsers.txt)]. Stattdessen wird die **[!UICONTROL Traffic]** Profil verwendet das DeviceAtlas-Bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]), um diese Konfigurationsinformationen bereitzustellen.
* Data Workbench 6.2.1 ist die letzte Version, die einen Download der 32-Bit-Clientanwendung umfasst. Alle zukünftigen Clientanwendungs-Downloads werden 64-Bit sein und Windows 7 oder höher erfordern. Die Speicherbeschränkungen der 32-Bit-Anwendung werden mit Einführung der 64-Bit-Anwendung ab Version 6.1 behoben.

>[!NOTE]
>
>Bei der 32-Bit-Version der Data Workbench Client-Anwendung können bei der Ausführung von Prognosemodellen mit Clustering- und Scoring-Funktionen potenzielle Probleme im Zusammenhang mit Speicherbeschränkungen auftreten.
