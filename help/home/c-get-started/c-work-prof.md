---
description: Data Workbench lädt Profile auf Ihren Computer herunter.
title: Profile
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Profile{#profiles}

{{eol}}

Data Workbench lädt Profile auf Ihren Computer herunter.

Wenn Sie ein Profil zum ersten Mal laden, müssen Sie über eine Netzwerkverbindung zum [!DNL Data Workbench server] und online arbeiten, damit die Data Workbench die erforderlichen Dateien von der [!DNL Data Workbench server].

Das Herunterladen des Profils kann mehrere Minuten dauern. Sie sollten nicht mit dem Profil arbeiten, bis der Daten-Cache zu füllen beginnt, aber Sie müssen nicht warten, bis er voll ist. Sie können den Fortschritt des Daten-Caches, den Fortschritt der Profilsynchronisierung sowie das Datum und die Uhrzeit der zuletzt verarbeiteten Daten verfolgen, indem Sie beim Laden des Profils die Statusleisten anzeigen.

>[!NOTE]
>
>Sie sehen keine Daten in von Ihnen hinzugefügten Visualisierungen, bis der Daten-Cache zu füllen beginnt.

Beim nächsten Laden des Profils werden das Profil und seine Daten nur heruntergeladen, wenn eine Netzwerkverbindung zum [!DNL Data Workbench server] und arbeiten online. Wenn Sie offline arbeiten, werden das Profil und seine Daten aus dem Cache Ihres Computers geladen. In diesem Fall zeigen Sie die Version des Profils und der Daten an, die beim letzten Mal heruntergeladen wurden, als Sie mit dem Profil online arbeiteten. Weitere Informationen zur Online- und Offline-Arbeit finden Sie unter [Offline und online arbeiten](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

Wenn Sie Ihr Profil ändern müssen (mithilfe des [!DNL Profile Manager] oder [!DNL Server Files Manager]), sollten Sie online sicherstellen, dass Sie über die aktuellste Version des Profils verfügen. Weitere Informationen zum [!DNL Profile Manager] und [!DNL Server Files Manager], siehe [Verwaltungsschnittstellen](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Wenn Sie kein Profil aufrufen oder laden können, müssen Sie möglicherweise Folgendes bestätigen:

* Sie verfügen über eine Netzwerkverbindung zum [!DNL Data Workbench server] Computer, auf dem sich das Profil befindet.
* Sie verfügen über die entsprechenden Berechtigungen für den Zugriff auf das Profil.

Wenden Sie sich zur Unterstützung an Ihren Systemadministrator.

## Profile laden oder wechseln {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Launch-Data Workbench.
1. Klicken Sie in der Seitenleiste auf den Profilnamen und klicken Sie auf **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, wobei *Profilname* ist das Profil, mit dem Sie arbeiten möchten.

   ![](assets/sidebar_profile.png)

Wenn Sie das ausgewählte Profil zum ersten Mal laden, kann es mehrere Minuten dauern, bis ausreichend Daten heruntergeladen sind, um eine Visualisierung zu füllen.

## Zugriff auf ein Profil in einem Cluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench von Benutzern, die auf ein Profil zugreifen, das auf einer

Data Workbench-Servercluster identifizieren nur den Übergeordneten Data Workbench Server in der Konfigurationsdatei der Data Workbench ( [!DNL Insight.cfg]). Aus Sicht des Data Workbench-Benutzers ist das Profil nur auf einem Data Workbench Server (dem Übergeordneten Data Workbench Server) zugänglich. Abfragen von Analysten können jedoch an einen beliebigen Data Workbench Server im Cluster weitergeleitet werden.

Weitere Informationen zu Profilen, die auf einem Data Workbench Server-Cluster ausgeführt werden, finden Sie im *Handbuch zur Installation und Verwaltung von Serverprodukten*.
