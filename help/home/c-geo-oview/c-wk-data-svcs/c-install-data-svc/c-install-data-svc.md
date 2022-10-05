---
description: Informationen zum Installieren eines Datendienstes auf einem Data Workbench-Server.
title: Installieren eines Daten-Services auf einem Data Workbench-Server
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# Installieren eines Daten-Services auf einem Data Workbench-Server{#installing-a-data-service-on-a-data-workbench-server}

{{eol}}

Informationen zum Installieren eines Datendienstes auf einem Data Workbench-Server.

Wenn Sie den IP-Geo-Intelligence-Datendienst oder den IP-Geostandortdatendienst verwenden, müssen Sie entweder den [!DNL IP Geo-intelligence] oder [!DNL IP Geo-location] Profil und die zugehörigen Lookup-Dateien auf Ihrem Data Workbench-Server. Nachdem Sie die Data Workbench installiert haben, müssen Sie die folgenden Schritte ausführen [!DNL Geography] Profil. Siehe [Installieren von Data Workbench Geography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Wenn Sie Data Workbench nicht installiert haben, folgen Sie den Anweisungen im Abschnitt *Data Workbench-Benutzerhandbuch* vor dem Fortfahren.

>[!NOTE]
>
>Um die Datendienstdateien zu installieren, benötigen Sie Zugriff auf die Dateien auf dem Data Workbench-Server.

Adobe verteilt die IP-Geo-Intelligence- und IP-Geostandortdatendienste als [!DNL .zip] Dateien. Jeder [!DNL .zip] -Datei enthält zwei Ordner: Suchen und Profile. Um einen Datendienst auf dem Data Workbench-Server zu installieren, müssen Sie die folgenden Schritte ausführen:

* Installieren Sie das Datendienstprofil. Siehe [Installieren des Datendienstprofils](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Installieren Sie die Datendienst-Suchen. Siehe [Installieren der Lookup-Dateien für den Datendienst](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

Sie müssen das Datendienstprofil und die Lookup-Dateien auf dem Data Workbench-Servercomputer installieren, auf dem Sie Ihr Datensatzprofil verarbeiten und ausführen. Wenn Sie einen Data Workbench-Servercluster ausführen, müssen Sie die Dateien auf dem Übergeordneten Server installieren. Informationen zu Datensatzprofilen finden Sie in der *Anleitung zur Datensatzkonfiguration*.
