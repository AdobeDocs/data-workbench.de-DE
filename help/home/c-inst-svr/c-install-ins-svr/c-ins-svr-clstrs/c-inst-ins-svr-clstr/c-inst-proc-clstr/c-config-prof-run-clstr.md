---
description: Wenn Sie ein DataSet-Profil für die Ausführung auf einem Insight Server-Cluster konfigurieren, verwenden alle Computer im Cluster alle DataSet-Konfigurationsdateien für dieses Profil.
solution: Analytics
title: Konfigurieren eines Profils für die Ausführung auf einem Cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---


# Konfigurieren eines Profils für die Ausführung auf einem Cluster{#configuring-a-profile-to-run-on-a-cluster}

Wenn Sie ein DataSet-Profil für die Ausführung auf einem Insight Server-Cluster konfigurieren, verwenden alle Computer im Cluster alle DataSet-Konfigurationsdateien für dieses Profil.

Daher müssen die Einträge für die Parameter in diesen Dateien für alle [!DNL Insight Servers] im Cluster gelten. Beispielsweise müssen die Speicherorte der zu lesenden Protokolldateien, die zu verwendenden Lookup-Dateien [!DNL Insight Server]und der Speicherort der Datenausgabe durch alle Computer im Cluster identisch sein [!DNL Insight Server] .

Sie führen alle Konfigurationseinstellungen auf dem Übergeordnete des Clusters durch [!DNL Insight Server]und verwenden [!DNL Insight Server] Sie diese zum Bearbeiten der Konfigurationsdateien. Alle auf dem Übergeordnete vorgenommenen Änderungen an der gespeicherten Konfigurationsdatei [!DNL Insight Server] werden automatisch mit den Dateien im Cluster synchronisiert, die auf der Verarbeitung [!DNL Insight Servers] im Cluster gespeichert sind.

Um ein DataSet-Profil auf einem [!DNL Insight Server] -Cluster auszuführen, müssen Sie die folgenden Vorgänge in der angegebenen Reihenfolge durchführen:

1. [Bestimmen, welche Insight-Server Ereignis-Daten verarbeiten](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Festlegen der Verarbeitungsserver in Profil.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Falls erforderlich) [Ändern der Datensatzkonfigurationsdateien für das Profil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Bestimmen, welche Insight-Server Ereignis-Daten verarbeiten {#section-59b8e3f2b34f49739d544c8740a62fba}

Es ist nicht erforderlich, dass alle [!DNL Insight Servers] im Cluster Ereignis-Daten verarbeiten. Sie können eine Datei [!DNL Insight Server] im Cluster als File Server Unit festlegen, die die Quelldateien (VSL- und Protokolldateien) speichert und die Dateien an alle Datenverarbeitungseinheiten (Verarbeitungsserver) im Cluster weitergibt. Dieses Setup bietet den Vorteil eines einzigen Ereignis-Datenspeichers und nutzt die Verarbeitungsleistung aller Verarbeitungsserver im Cluster. Die Verarbeitungsserver teilen die Datendateien untereinander auf und stellen sicher, dass dieselbe Datei nicht mehr als einmal verarbeitet wird.

Weitere Informationen zum Festlegen einer [!DNL Insight Server] auszuführenden Datei als Dateiservereinheit finden Sie im Kapitel &quot;Konfigurationsdatei für die Protokollverarbeitung&quot;des *Dataset-Konfigurationsleitfadens*.

Wenn Sie sich entscheiden, Quelldatendateien auf jedem der Verarbeitungsserver anstatt auf einer einzelnen Dateiservereinheit zu speichern, müssen Sie die Dateien gleichmäßig auf die Verarbeitungsserver aufteilen. Speichern Sie nicht alle Quelldateien des Datensatzes auf jedem der Verarbeitungsserver. Wenn mehrere Kopien derselben Datei auf mehreren Verarbeitungsservern verfügbar sind, werden die Daten mehrmals gelesen (einmal von jedem Computer) und verzerrt.

Wenden Sie sich an Adobe Consulting, um festzustellen, welche Protokolldateien verarbeitet werden [!DNL Insight Servers] sollen.

## Festlegen der Verarbeitungsserver in Profil.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

Geben Sie in der [!DNL profile.cfg] Datei die Verarbeitungsserver an, die die Daten für das Profil verarbeiten.

**So greifen Sie auf die Datei &quot;Profil.cfg&quot;zu**

Sie können mit dem [!DNL Profile Manager] in auf die Profil-Konfigurationsdatei zugreifen [!DNL Insight].

1. Öffnen Sie beim Arbeiten im DataSet-Profil die Datei, [!DNL Profile Manager] indem Sie mit der rechten Maustaste auf einen Arbeitsbereich klicken und dann auf **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**> klicken oder indem Sie den Arbeitsbereich &quot;Profil-Verwaltung&quot;auf der [!DNL Admin] Registerkarte öffnen.

1. Klicken Sie im [!DNL Profile Manager]Kontextmenü mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der [!DNL User] Spalte angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster zur Konfiguration des Profils wird angezeigt.

**So fügen Sie Verarbeitungsserver hinzu**

1. Klicken Sie in der [!DNL profile.cfg] Datei auf **[!UICONTROL Profile]** und dann auf **[!UICONTROL Processing Servers]** , um deren Inhalt anzuzeigen.

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Processing Servers]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Geben Sie im Parameter &quot;Common Name&quot;den allgemeinen Namen für den ersten Verarbeitungsserver im Cluster ein. Beispiel: [!DNL server1.mycompany.com]
1. Wiederholen Sie die Schritte 2 und 3, bis Sie die allgemeinen Namen aller Verarbeitungsserver im Cluster hinzugefügt haben.

   >[!NOTE]
   >
   >Wenn die Daten von Übergeordnet [!DNL Insight Server] verarbeitet werden, müssen Sie sie ebenfalls hinzufügen.

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der [!DNL User] Spalte neben [!DNL profile.cfg]. Klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Ändern der DataSet-Konfigurationsdateien für das Profil {#section-99bf9248e4e5483cb518f453b0a2f278}

**So ändern Sie die Datensatzkonfigurationsdateien**

Wenn Sie Änderungen an den Datensatzkonfigurationsdateien vornehmen müssen ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], Datensatzeinschlussdateien [!DNL Log Processing Mode.cfg]usw.), tun Sie dies nur Übergeordnet [!DNL Insight Server].

1. Greifen Sie auf die Dateien zu, die Sie ändern möchten:

   Anweisungen zum Zugriff auf die Dateien finden Sie im Handbuch zur Konfiguration von *Datasets*.
1. Nehmen Sie die gewünschten Änderungen vor. Einzelheiten zu den Parametern in der/den Konfigurationsdatei(en) finden Sie im Handbuch *zur Konfiguration von* Datasets.
1. Speichern Sie die Datei.

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der [!DNL User] Spalte neben dem Dateinamen.
   1. Klicken Sie auf **[!UICONTROL Save to]** und wählen Sie das gewünschte Profil aus.

>[!NOTE]
>
>[!DNL Insight] Benutzer, die auf ein auf einem Cluster ausgeführtes DataSet-Profil zugreifen, identifizieren nur den Übergeordnete [!DNL Insight Server] in der [!DNL Insight] Konfigurationsdatei ( [!DNL insight.cfg]). Aus Sicht des [!DNL Insight] Benutzers ist das Profil nur auf einem [!DNL Insight Server] (dem Übergeordnet [!DNL Insight Server]) zugänglich. Allerdings können Analystenanforderungen an die Abfrage an einen beliebigen [!DNL Insight Servers] im Cluster weitergeleitet werden.

Ein [!DNL Insight Server] Cluster ermöglicht die zentralisierte Datenspeicherung von [!DNL .vsl] Protokolldateien (von [!DNL Sensor]) auf einem einzigen [!DNL Insight Server] Computer, dem so genannten File Server Unit (FSU). Informationen zum Installieren einer FSU finden Sie unter [Installationsanweisungen für eine Insight Server-FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Weitere Informationen zum Konfigurieren eines FSU finden Sie im Handbuch zur Konfiguration von *Datasets*.
