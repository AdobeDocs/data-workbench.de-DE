---
description: Data Workbench lädt Profile auf Ihren Computer herunter.
title: Profile
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profile{#profiles}

Data Workbench lädt Profile auf Ihren Computer herunter.

Wenn Sie zum ersten Mal ein Profil laden, müssen Sie über eine Netzwerkverbindung zum Profil verfügen [!DNL Data Workbench server] und online arbeiten, damit Data Workbench die erforderlichen Dateien aus dem [!DNL Data Workbench server]herunterladen kann.

Das Herunterladen des Profils kann einige Minuten dauern. Sie sollten erst dann mit dem Profil arbeiten, wenn der Datencache zu füllen beginnt. Sie müssen jedoch nicht warten, bis er voll ist. Sie können den Fortschritt des Datenspeichers, den Fortschritt der Profilsynchronisierung sowie Datum und Uhrzeit der zuletzt verarbeiteten Daten verfolgen, indem Sie die Statusleisten beim Laden des Profils überprüfen.

>[!NOTE]
>
>Daten in Visualisierungen, die Sie hinzufügen, werden erst dann angezeigt, wenn der Datencache zu füllen beginnt.

Wenn Sie das Profil das nächste Mal laden, werden Aktualisierungen des Profils und der zugehörigen Daten nur heruntergeladen, wenn Sie eine Netzwerkverbindung zum Profil haben [!DNL Data Workbench server] und online arbeiten. Wenn Sie offline arbeiten, werden das Profil und seine Daten aus dem Cache Ihres Computers geladen. In diesem Fall zeigen Sie die Version des Profils und der Daten an, die beim letzten Mal heruntergeladen wurden, wenn Sie mit dem Profil online gearbeitet haben. Weitere Informationen zum Arbeiten im Internet und im Offlinemodus finden Sie unter Offline- und Online- [Arbeit](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

Wenn Sie Ihr Profil ändern müssen (mit der [!DNL Profile Manager] oder der [!DNL Server Files Manager]), sollten Sie online arbeiten, um sicherzustellen, dass Sie über die aktuellste Version des Profils verfügen. Weitere Informationen zum [!DNL Profile Manager] und zum [!DNL Server Files Manager]finden Sie unter [Verwaltungsschnittstellen](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Wenn Sie nicht auf ein Profil zugreifen oder ein Profil laden können, müssen Sie möglicherweise Folgendes bestätigen:

* Sie haben eine Netzwerkverbindung mit dem [!DNL Data Workbench server] Computer, auf dem sich das Profil befindet.
* Sie haben die entsprechenden Berechtigungen, um auf das Profil zuzugreifen.

Wenden Sie sich zwecks Hilfe an Ihren Systemadministrator.

## Profile laden oder wechseln {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Starten Sie Data Workbench.
1. Klicken Sie in der Seitenleiste auf den Profilnamen und klicken Sie auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*. Dabei ist der *Profilname* das Profil, mit dem Sie arbeiten möchten.

   ![](assets/sidebar_profile.png)

Wenn Sie das ausgewählte Profil zum ersten Mal laden, kann es mehrere Minuten dauern, bis genügend Daten heruntergeladen wurden, um eine Visualisierung auszufüllen.

## Zugriff auf ein Profil in einem Cluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench-Benutzer, die auf ein Profil zugreifen, das auf einem

Der Data Workbench-Servercluster identifiziert nur den Master-Data Workbench-Server in der Data Workbench-Konfigurationsdatei ( [!DNL Insight.cfg]). Aus Sicht des Data Workbench-Benutzers ist das Profil nur auf einem Data Workbench-Server (dem Master Data Workbench-Server) verfügbar. Abfragen von Analysten können jedoch an beliebige Data Workbench-Server im Cluster weitergeleitet werden.

Weitere Informationen zu Profilen, die auf einem Data Workbench Server-Cluster ausgeführt werden, finden Sie im Handbuch zur Installation und Verwaltung von *Serverprodukten*.
