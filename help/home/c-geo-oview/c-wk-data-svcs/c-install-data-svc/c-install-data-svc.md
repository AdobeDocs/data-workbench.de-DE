---
description: Informationen zum Installieren eines Datendiensts auf einem Data Workbench-Server.
solution: Analytics
title: Installieren eines Datendienstes auf einem Data Workbench-Server
topic: Data workbench
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Installieren eines Datendienstes auf einem Data Workbench-Server{#installing-a-data-service-on-a-data-workbench-server}

Informationen zum Installieren eines Datendiensts auf einem Data Workbench-Server.

Wenn Sie den IP-Geo-Intelligence-Datendienst oder den IP-Geo-Standort-Datendienst verwenden, müssen Sie entweder das Profil [!DNL IP Geo-intelligence] [!DNL IP Geo-location] oder das Profil und die zugehörigen Lookup-Dateien auf Ihrem Data Workbench-Server installieren. Nachdem Sie das Data Workbench- [!DNL Geography] Profil installiert haben, müssen Sie die folgenden Schritte ausführen. Siehe [Installieren von Data Workbench Geografie](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Wenn Sie die Data Workbench nicht installiert haben, befolgen Sie die Anweisungen im *Data Workbench-Benutzerhandbuch* , bevor Sie fortfahren.

>[!NOTE]
>
>Um die Datendienstdateien zu installieren, müssen Sie Zugriff auf die Dateien auf dem Data Workbench-Server haben.

Adobe verteilt die Geo-Intelligence- und IP-Geo-Location-Datendienste als [!DNL .zip] Dateien. Jede [!DNL .zip] Datei enthält zwei Ordner: Suchen und Profile. Um einen Datendienst auf dem Data Workbench-Server zu installieren, müssen Sie die folgenden Schritte ausführen:

* Installieren Sie das Datendienstprofil. Siehe [Installieren des Datendienstprofils](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Installieren Sie die Datendienst-Suchen. Siehe [Installieren der Datendienst-Suchdateien](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

Sie müssen das Datendienstprofil und die Lookup-Dateien auf dem Datenbasis-Servercomputer installieren, auf dem Sie Ihr Datendienstprofil verarbeiten und ausführen. Wenn Sie ein Data Workbench-Servercluster ausführen, müssen Sie die Dateien auf dem Master-Server installieren. Weitere Informationen zu Datensatzprofilen finden Sie im Handbuch zur Konfiguration von *DataSet*.
