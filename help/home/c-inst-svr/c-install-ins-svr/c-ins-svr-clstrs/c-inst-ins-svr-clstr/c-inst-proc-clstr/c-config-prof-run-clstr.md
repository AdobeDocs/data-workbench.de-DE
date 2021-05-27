---
description: Wenn Sie ein Datensatzprofil für die Ausführung auf einem Insight Server-Cluster konfigurieren, teilen alle Computer im Cluster alle Datensatzkonfigurationsdateien für dieses Profil.
title: Konfigurieren eines Profils für die Ausführung auf einem Cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Konfigurieren eines Profils für die Ausführung auf einem Cluster{#configuring-a-profile-to-run-on-a-cluster}

Wenn Sie ein Datensatzprofil für die Ausführung auf einem Insight Server-Cluster konfigurieren, teilen alle Computer im Cluster alle Datensatzkonfigurationsdateien für dieses Profil.

Daher müssen die Einträge für die Parameter in diesen Dateien für alle [!DNL Insight Servers] im Cluster gelten. Beispielsweise müssen die Speicherorte der zu lesenden Protokolldateien, die von [!DNL Insight Server] zu verwendenden Lookup-Dateien und der Speicherort der Datenausgabe von [!DNL Insight Server] auf allen Computern im Cluster identisch sein.

Sie führen alle Konfigurationsaufgaben auf dem Übergeordneten [!DNL Insight Server] des Clusters aus, dem [!DNL Insight Server], mit dem Sie Ihre Konfigurationsdateien bearbeiten. Alle auf dem Übergeordneten [!DNL Insight Server] vorgenommenen Änderungen der gespeicherten Konfigurationsdatei werden automatisch mit den Dateien synchronisiert, die sich auf die Verarbeitung [!DNL Insight Servers] im Cluster beziehen.

Um ein Datensatzprofil auf einem [!DNL Insight Server]-Cluster auszuführen, müssen Sie die folgenden Prozesse in der angegebenen Reihenfolge durchführen:

1. [Bestimmen, welche Insight Server Ereignisdaten verarbeiten](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Festlegen der Verarbeitungsserver in Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Falls erforderlich) [Ändern der Datensatzkonfigurationsdateien für das Profil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Bestimmen, welche Insight Server Ereignisdaten verarbeiten {#section-59b8e3f2b34f49739d544c8740a62fba}

Es ist nicht erforderlich, dass alle [!DNL Insight Servers] im Cluster Ereignisdaten verarbeiten. Sie können einen [!DNL Insight Server] im Cluster als File Server Unit festlegen, der die Quelldateien (VSL- und Protokolldateien) speichert und die Dateien für alle Datenverarbeitungseinheiten (Verarbeitungsserver) im Cluster bereitstellt. Diese Einrichtung bietet den Vorteil eines einzelnen Ereignisdaten-Repositorys und nutzt die Verarbeitungsleistung aller Verarbeitungsserver im Cluster. Die Verarbeitungsserver teilen die Datendateien unter sie auf und stellen sicher, dass dieselbe Datei nicht mehrmals verarbeitet wird.

Weitere Informationen zum Benennen eines [!DNL Insight Server] für die Ausführung als Dateiservereinheit finden Sie im Kapitel &quot;Konfigurationsdatei für die Protokollverarbeitung&quot;im *Handbuch zur Datensatzkonfiguration*.

Wenn Sie Quelldatendateien auf jedem Verarbeitungsserver anstatt auf einer einzigen Dateiservereinheit speichern möchten, müssen Sie die Dateien gleichmäßig auf die Verarbeitungsserver aufteilen. Speichern Sie nicht alle Quelldateien des Datensatzes auf jedem Verarbeitungsserver. Wenn mehrere Kopien derselben Datei für mehrere Verarbeitungsserver verfügbar sind, werden die Daten mehrmals gelesen (einmal pro Computer) und verfälschen Ihre Daten.

Wenden Sie sich an Adobe Consulting, um herauszufinden, welche [!DNL Insight Servers] Protokolldateien verarbeiten soll.

## Festlegen der Verarbeitungsserver in Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

Geben Sie in der Datei [!DNL profile.cfg] die Verarbeitungsserver an, die die Daten für das Profil verarbeiten.

**So greifen Sie auf die Datei profile.cfg zu**

Sie greifen mithilfe von [!DNL Profile Manager] in [!DNL Insight] auf die Profilkonfigurationsdatei zu.

1. Öffnen Sie während der Arbeit mit Ihrem Datensatzprofil das [!DNL Profile Manager], indem Sie mit der rechten Maustaste in einen Arbeitsbereich klicken und **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** klicken oder indem Sie den Arbeitsbereich &quot;Profilverwaltung&quot;auf der Registerkarte [!DNL Admin] öffnen.

1. Klicken Sie in [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster zur Profilkonfiguration wird angezeigt.

**Hinzufügen der Verarbeitungsserver**

1. Klicken Sie in der Datei [!DNL profile.cfg] auf **[!UICONTROL Profile]** und dann auf **[!UICONTROL Processing Servers]** , um den Inhalt anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Processing Servers]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Geben Sie im Parameter &quot;Common Name&quot;den allgemeinen Namen für den ersten Verarbeitungsserver im Cluster ein. Beispiel: [!DNL server1.mycompany.com]
1. Wiederholen Sie die Schritte 2 und 3, bis Sie die allgemeinen Namen aller Verarbeitungsserver im Cluster hinzugefügt haben.

   >[!NOTE]
   >
   >Wenn das Übergeordnete [!DNL Insight Server] Daten verarbeitet, müssen Sie sie auch hinzufügen.

1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL User] neben [!DNL profile.cfg]. Klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Ändern der Datensatzkonfigurationsdateien für das Profil {#section-99bf9248e4e5483cb518f453b0a2f278}

**So ändern Sie die Datensatzkonfigurationsdateien**

Wenn Sie Änderungen an den Datensatzkonfigurationsdateien ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], Datensatzaufnahme-Dateien, [!DNL Log Processing Mode.cfg] usw.) vornehmen müssen, tun Sie dies nur bei Übergeordneten [!DNL Insight Server].

1. Greifen Sie auf die Dateien zu, die Sie ändern möchten:

   Anweisungen zum Zugriff auf die Dateien finden Sie im *Handbuch zur Datensatzkonfiguration*.
1. Nehmen Sie die gewünschten Änderungen vor. Weitere Informationen zu den Parametern in den Konfigurationsdateien finden Sie im *Handbuch zur Datensatzkonfiguration* .
1. Speichern Sie die Datei.

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL User] neben dem Dateinamen.
   1. Klicken Sie auf **[!UICONTROL Save to]** und wählen Sie das gewünschte Profil aus.

>[!NOTE]
>
>[!DNL Insight] -Benutzer, die auf ein Datensatzprofil zugreifen, das auf einem Cluster ausgeführt wird, identifizieren nur die Übergeordneten  [!DNL Insight Server] in der  [!DNL Insight] Konfigurationsdatei (  [!DNL insight.cfg]). Aus Sicht des Benutzers [!DNL Insight] ist das Profil nur für einen [!DNL Insight Server] (Übergeordneten [!DNL Insight Server]) zugänglich. Abfragen von Analysten können jedoch an beliebige [!DNL Insight Servers] im Cluster weitergeleitet werden.

Ein [!DNL Insight Server]-Cluster ermöglicht die zentrale Speicherung von [!DNL .vsl] Protokolldateien (von [!DNL Sensor]) auf einem einzelnen [!DNL Insight Server]-Computer, der als File Server Unit (FSU) bezeichnet wird. Informationen zum Installieren einer FSU finden Sie unter [Installationsverfahren für eine Insight Server-FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Informationen zum Konfigurieren einer FSU finden Sie im *Handbuch zur Datensatzkonfiguration*.
