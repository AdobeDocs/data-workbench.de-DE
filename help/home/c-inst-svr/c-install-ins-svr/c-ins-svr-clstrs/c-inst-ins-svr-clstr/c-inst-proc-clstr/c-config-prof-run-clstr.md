---
description: Wenn Sie ein DataSet-Profil für die Ausführung auf einem Insight Server-Cluster konfigurieren, verwenden alle Computer im Cluster alle DataSet-Konfigurationsdateien für dieses Profil.
title: Konfigurieren eines Profils für die Ausführung auf einem Cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Konfigurieren eines Profils für die Ausführung auf einem Cluster{#configuring-a-profile-to-run-on-a-cluster}

Wenn Sie ein DataSet-Profil für die Ausführung auf einem Insight Server-Cluster konfigurieren, verwenden alle Computer im Cluster alle DataSet-Konfigurationsdateien für dieses Profil.

Daher müssen die Einträge für die Parameter in diesen Dateien für alle [!DNL Insight Servers] im Cluster gelten. Beispielsweise müssen die Speicherorte der zu lesenden Protokolldateien, die von [!DNL Insight Server] zu verwendenden Lookup-Dateien und der Speicherort der Datenausgabe von [!DNL Insight Server] auf allen Computern im Cluster identisch sein.

Sie führen alle Konfigurationsdateien auf dem Übergeordnete [!DNL Insight Server] des Clusters aus, dem [!DNL Insight Server], mit dem Sie Ihre Konfigurationsdateien bearbeiten. Alle Änderungen an der gespeicherten Konfigurationsdatei, die an dem Übergeordnet [!DNL Insight Server] vorgenommen wurden, werden automatisch mit den Dateien auf dem Verarbeitungsmedium [!DNL Insight Servers] im Cluster synchronisiert.

Um ein DataSet-Profil auf einem [!DNL Insight Server]-Cluster auszuführen, müssen Sie die folgenden Vorgänge in der angegebenen Reihenfolge durchführen:

1. [Bestimmen, welche Insight-Server Ereignis-Daten verarbeiten](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Festlegen der Verarbeitungsserver in Profil.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Falls erforderlich) [Ändern der DataSet-Konfigurationsdateien für das Profil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Bestimmen, welche Insight-Server Ereignis-Daten verarbeiten {#section-59b8e3f2b34f49739d544c8740a62fba}

Es ist nicht erforderlich, dass alle [!DNL Insight Servers] im Cluster Ereignis-Daten verarbeiten. Sie können ein [!DNL Insight Server] im Cluster als Dateiservereinheit festlegen, die die Quelldateien (VSL- und Protokolldateien) speichert und die Dateien an alle Datenverarbeitungseinheiten (Verarbeitungsserver) im Cluster liefert. Dieses Setup bietet den Vorteil eines einzigen Ereignis-Datenspeichers und nutzt die Verarbeitungsleistung aller Verarbeitungsserver im Cluster. Die Verarbeitungsserver teilen die Datendateien untereinander auf und stellen sicher, dass dieselbe Datei nicht mehr als einmal verarbeitet wird.

Weitere Informationen zum Festlegen einer [!DNL Insight Server]-Einheit für die Ausführung als Dateiservereinheit finden Sie im Kapitel &quot;Konfigurationsdatei für die Protokollverarbeitung&quot;im Handbuch *Datenkonfiguration*.

Wenn Sie sich entscheiden, Quelldatendateien auf jedem der Verarbeitungsserver anstatt auf einer einzelnen Dateiservereinheit zu speichern, müssen Sie die Dateien gleichmäßig auf die Verarbeitungsserver aufteilen. Speichern Sie nicht alle Quelldateien des Datensatzes auf jedem der Verarbeitungsserver. Wenn mehrere Kopien derselben Datei auf mehreren Verarbeitungsservern verfügbar sind, werden die Daten mehrmals gelesen (einmal von jedem Computer) und verzerrt.

Wenden Sie sich an Adobe Consulting, um festzustellen, welche Protokolldateien verarbeitet werden sollen.[!DNL Insight Servers]

## Festlegen der Verarbeitungsserver in Profil.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

Geben Sie in der Datei [!DNL profile.cfg] die Verarbeitungsserver an, die die Daten für das Profil verarbeiten.

**So greifen Sie auf die Datei &quot;Profil.cfg&quot;zu**

Sie greifen auf die Konfigurationsdatei des Profils mit [!DNL Profile Manager] in [!DNL Insight] zu.

1. Öffnen Sie beim Arbeiten im DataSet-Profil das [!DNL Profile Manager], indem Sie mit der rechten Maustaste in einem Arbeitsbereich auf **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** klicken oder indem Sie den Arbeitsbereich &quot;Profil-Verwaltung&quot;auf der Registerkarte [!DNL Admin] öffnen.

1. Klicken Sie in [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster zur Konfiguration des Profils wird angezeigt.

**So fügen Sie Verarbeitungsserver hinzu**

1. Klicken Sie in der Datei [!DNL profile.cfg] auf **[!UICONTROL Profile]** und dann auf **[!UICONTROL Processing Servers]**, um den Inhalt anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Processing Servers]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Geben Sie im Parameter &quot;Common Name&quot;den allgemeinen Namen für den ersten Verarbeitungsserver im Cluster ein. Beispiel: [!DNL server1.mycompany.com]
1. Wiederholen Sie die Schritte 2 und 3, bis Sie die allgemeinen Namen aller Verarbeitungsserver im Cluster hinzugefügt haben.

   >[!NOTE]
   >
   >Wenn Übergeordnet [!DNL Insight Server] Daten verarbeitet, müssen Sie diese ebenfalls hinzufügen.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL User] neben [!DNL profile.cfg]. Klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Ändern der DataSet-Konfigurationsdateien für das Profil {#section-99bf9248e4e5483cb518f453b0a2f278}

**So ändern Sie die Datensatzkonfigurationsdateien**

Wenn Sie Änderungen an den Datenaset-Konfigurationsdateien ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], Datensatz enthält Dateien, [!DNL Log Processing Mode.cfg] usw.) vornehmen müssen, führen Sie dies nur bei Übergeordnet [!DNL Insight Server] durch.

1. Greifen Sie auf die Dateien zu, die Sie ändern möchten:

   Anweisungen zum Zugriff auf die Dateien finden Sie im Handbuch *Konfiguration von Datensätzen*.
1. Nehmen Sie die gewünschten Änderungen vor. Einzelheiten zu den Parametern in der/den Konfigurationsdatei(en) finden Sie im Handbuch *Datenkonfiguration*.
1. Speichern Sie die Datei.

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL User] neben dem Dateinamen.
   1. Klicken Sie auf **[!UICONTROL Save to]** und wählen Sie das gewünschte Profil aus.

>[!NOTE]
>
>[!DNL Insight] Benutzer, die auf ein DataSet-Profil zugreifen, das auf einem Cluster ausgeführt wird, identifizieren nur den Übergeordnete  [!DNL Insight Server] in der  [!DNL Insight] Konfigurationsdatei (  [!DNL insight.cfg]). Aus der Perspektive des [!DNL Insight]-Benutzers ist das Profil nur für ein [!DNL Insight Server] (das Übergeordnet [!DNL Insight Server]) verfügbar; Allerdings können Analystenanforderungen an Abfragen an beliebige [!DNL Insight Servers] im Cluster weitergeleitet werden.

Ein [!DNL Insight Server]-Cluster ermöglicht die zentralisierte Datenspeicherung von Protokolldateien (von [!DNL Sensor]) auf einem einzelnen [!DNL Insight Server]-Computer, der als Dateiservereinheit (FSU) bezeichnet wird. [!DNL .vsl] Informationen zum Installieren einer FSU finden Sie unter [Installationsanweisungen für eine Insight Server-FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Weitere Informationen zum Konfigurieren einer FSU finden Sie im Handbuch *Dataset Configuration Guide*.
