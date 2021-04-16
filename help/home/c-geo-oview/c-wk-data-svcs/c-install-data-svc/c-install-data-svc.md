---
description: Informationen zum Installieren eines Datendiensts auf einem Data Workbench-Server.
title: Installieren eines Daten-Services auf einem Data Workbench-Server
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# Installieren eines Daten-Services auf einem Data Workbench-Server{#installing-a-data-service-on-a-data-workbench-server}

Informationen zum Installieren eines Datendiensts auf einem Data Workbench-Server.

Wenn Sie den IP-Geo-Intelligence-Datendienst oder den IP-Geo-Location-Datendienst verwenden, müssen Sie entweder das [!DNL IP Geo-intelligence]- oder das [!DNL IP Geo-location]-Profil und die zugehörigen Lookup-Dateien auf Ihrem Data Workbench-Server installieren. Nach der Installation des Profils data workbench [!DNL Geography] müssen Sie die folgenden Schritte ausführen. Siehe [Data Workbench-Geografie installieren](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Wenn Sie die Data Workbench nicht installiert haben, befolgen Sie die Anweisungen im *Data Workbench Benutzerhandbuch*, bevor Sie fortfahren.

>[!NOTE]
>
>Um die Datendienstdateien zu installieren, müssen Sie Zugriff auf die Dateien auf dem Data Workbench-Server haben.

Adobe verteilt die IP-Geo-Intelligence- und IP-Geo-Location-Datendienste als [!DNL .zip]-Dateien. Jede [!DNL .zip]-Datei enthält zwei Ordner: Suchen und Profile. Um einen Datendienst auf dem Data Workbench-Server zu installieren, müssen Sie die folgenden Schritte ausführen:

* Installieren Sie das Datendienst-Profil. Siehe [Installieren des Data Service-Profils](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Installieren Sie die Datendienst-Suchen. Siehe [Installieren der Datendienst-Suchdateien](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

Sie müssen das Datendienst-Profil und die Nachschlagedateien auf dem Datenbasis-Servercomputer installieren, auf dem Sie Ihr DataSet-Profil verarbeiten und ausführen. Wenn Sie ein Data Workbench-Servercluster ausführen, müssen Sie die Dateien auf dem Übergeordnet-Server installieren. Weitere Informationen zu DataSet-Profilen finden Sie im Handbuch *Konfiguration von DataSet*.
