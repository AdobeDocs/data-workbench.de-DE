---
description: Schritte zum Installieren der IP-Geo-Intelligence- oder IP-Geo-Location-Lookup-Dateien.
title: Installieren der Lookup-Dateien für den Daten-Service
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# Installieren der Lookup-Dateien für den Daten-Service{#installing-the-data-service-lookup-files}

Schritte zum Installieren der IP-Geo-Intelligence- oder IP-Geo-Location-Lookup-Dateien.

Die mit dem Datendienst-Profil bereitgestellte Abfragedatei (Lookups\*Profil name*\*Datendateiname*) ist eine Binärdatei ( [!DNL .bin]), die auf der Grundlage der IP-Adresse geografische Daten enthält. Sie müssen diese Datei regelmäßig ersetzen, um sicherzustellen, dass Sie über die neuesten geografischen Daten verfügen. Siehe [Aktualisieren von Datendienstdateien](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**So installieren Sie die IP-Geo-Intelligence- oder IP-Geo-Standort-Nachschlagedateien**

>[!NOTE]
>
>Alle [!DNL IP Geo-location]- oder [!DNL IP Geo-intelligence]-Datendateien müssen in den verfügbaren physischen Speicher Ihres Data Workbench-Servers passen.

1. Öffnen Sie den Ordner &quot;Suchen&quot;in der Datei [!DNL .zip], die Sie von der Adobe erhalten haben.
1. Kopieren Sie den Ordner &quot;IP Geo-Intelligence&quot;oder &quot;IP Geo-Location&quot;in den Ordner &quot;Lookups&quot;im Installationsordner des Data Workbench-Servers (Sie möchten am Ende eine ...\Lookups\IP Geo-intelligence or a ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example. Die Namen der anderen Ordner im Ordner &quot;Suchen&quot;unterscheiden sich möglicherweise von denen, die angezeigt werden.

   ![Schritt-Info](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >In regelmäßigen Abständen sendet Adobe Dateien mit aktualisierten [!DNL IP Geo-intelligence]- oder [!DNL IP Geo-location]-Nachschlagedateien. Wenn Sie diese Dateien erhalten, müssen Sie sie entsprechend der Adobe auf den Data Workbench-Server laden. Anweisungen finden Sie im folgenden Abschnitt.
