---
description: Wenn Sie ein Datensatzprofil für die Ausführung auf einem Insight Server-Cluster konfigurieren, teilen alle Computer im Cluster alle Datensatzkonfigurationsdateien für dieses Profil.
title: Konfigurieren eines Profils für die Ausführung auf einem Cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Konfigurieren eines Profils für die Ausführung auf einem Cluster{#configuring-a-profile-to-run-on-a-cluster}

{{eol}}

Wenn Sie ein Datensatzprofil für die Ausführung auf einem Insight Server-Cluster konfigurieren, teilen alle Computer im Cluster alle Datensatzkonfigurationsdateien für dieses Profil.

Daher müssen die Einträge für die Parameter in diesen Dateien für alle [!DNL Insight Servers] im Cluster. Beispielsweise die Speicherorte der zu lesenden Protokolldateien, die Lookup-Dateien, die von [!DNL Insight Server]und den Speicherort der Datenausgabe durch [!DNL Insight Server] muss auf allen Computern im Cluster gleich sein.

Sie führen alle Konfigurationsaufgaben auf dem Übergeordneten Cluster aus. [!DNL Insight Server], wobei [!DNL Insight Server] Sie verwenden , um Ihre Konfigurationsdateien zu bearbeiten. Alle Änderungen der gespeicherten Konfigurationsdatei, die an den Übergeordneten [!DNL Insight Server] automatisch mit den Dateien in der Verarbeitung synchronisiert werden [!DNL Insight Servers] im Cluster.

So führen Sie ein Datensatzprofil auf einem [!DNL Insight Server] Cluster, müssen Sie die folgenden Prozesse in der angegebenen Reihenfolge ausführen:

1. [Bestimmen, welche Insight Server Ereignisdaten verarbeiten](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Festlegen der Verarbeitungsserver in Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Falls erforderlich) [Ändern der Datensatzkonfigurationsdateien für das Profil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Bestimmen, welche Insight Server Ereignisdaten verarbeiten {#section-59b8e3f2b34f49739d544c8740a62fba}

Es ist nicht erforderlich, dass alle [!DNL Insight Servers] im Cluster Ereignisdaten verarbeiten. Sie können eine [!DNL Insight Server] im Cluster als File Server Unit, das die Quelldateien (VSL- und Protokolldateien) speichert und die Dateien für alle Datenverarbeitungseinheiten (Verarbeitungsserver) im Cluster bereitstellt. Diese Einrichtung bietet den Vorteil eines einzelnen Ereignisdaten-Repositorys und nutzt die Verarbeitungsleistung aller Verarbeitungsserver im Cluster. Die Verarbeitungsserver teilen die Datendateien unter sie auf und stellen sicher, dass dieselbe Datei nicht mehrmals verarbeitet wird.

Weitere Informationen zur Benennung eines [!DNL Insight Server] Informationen zum Ausführen als Dateiservereinheit finden Sie im Kapitel Konfigurationsdatei für die Protokollverarbeitung im Abschnitt *Anleitung zur Datensatzkonfiguration*.

Wenn Sie Quelldatendateien auf jedem Verarbeitungsserver anstatt auf einer einzigen Dateiservereinheit speichern möchten, müssen Sie die Dateien gleichmäßig auf die Verarbeitungsserver aufteilen. Speichern Sie nicht alle Quelldateien des Datensatzes auf jedem Verarbeitungsserver. Wenn mehrere Kopien derselben Datei für mehrere Verarbeitungsserver verfügbar sind, werden die Daten mehrmals gelesen (einmal pro Computer) und verfälschen Ihre Daten.

Hilfe bei der Bestimmung der [!DNL Insight Servers] sollten Protokolldateien verarbeiten, wenden Sie sich an Adobe Consulting.

## Festlegen der Verarbeitungsserver in Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

Im [!DNL profile.cfg] -Datei die Verarbeitungsserver angeben, die die Daten für das Profil verarbeiten.

**So greifen Sie auf die Datei profile.cfg zu**

Sie greifen auf die Profilkonfigurationsdatei zu, indem Sie die [!DNL Profile Manager] in [!DNL Insight].

1. Wenn Sie in Ihrem Datensatzprofil arbeiten, öffnen Sie die [!DNL Profile Manager] durch Rechtsklicken in einem Arbeitsbereich und Klicken auf **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** oder durch Öffnen des Arbeitsbereichs Profilverwaltung im [!DNL Admin] Registerkarte.

1. Im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL profile.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster zur Profilkonfiguration wird angezeigt.

**Hinzufügen der Verarbeitungsserver**

1. Im [!DNL profile.cfg] Datei, klicken Sie auf **[!UICONTROL Profile]** Klicken Sie auf **[!UICONTROL Processing Servers]** , um den Inhalt anzuzeigen.

1. Rechtsklick **[!UICONTROL Processing Servers]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Geben Sie im Parameter &quot;Common Name&quot;den allgemeinen Namen für den ersten Verarbeitungsserver im Cluster ein. Beispiel: [!DNL server1.mycompany.com]
1. Wiederholen Sie die Schritte 2 und 3, bis Sie die allgemeinen Namen aller Verarbeitungsserver im Cluster hinzugefügt haben.

   >[!NOTE]
   >
   >Wenn das Übergeordnete [!DNL Insight Server] Daten verarbeitet, müssen Sie sie auch hinzufügen.

1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen im [!DNL User] Spalte neben [!DNL profile.cfg]. Klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Ändern der Datensatzkonfigurationsdateien für das Profil {#section-99bf9248e4e5483cb518f453b0a2f278}

**So ändern Sie die Datensatzkonfigurationsdateien**

Wenn Sie Änderungen an den Datensatzkonfigurationsdateien vornehmen müssen ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], Datensatzaufnahme-Dateien, [!DNL Log Processing Mode.cfg]usw.) nur auf das Übergeordnete [!DNL Insight Server].

1. Greifen Sie auf die Dateien zu, die Sie ändern möchten:

   Anweisungen zum Zugriff auf die Dateien finden Sie unter *Anleitung zur Datensatzkonfiguration*.
1. Nehmen Sie die gewünschten Änderungen vor. Siehe *Anleitung zur Datensatzkonfiguration* für Details zu den Parametern in der(den) Konfigurationsdatei(en).
1. Speichern Sie die Datei.

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen im [!DNL User] neben dem Dateinamen.
   1. Klicken **[!UICONTROL Save to]** und wählen Sie das gewünschte Profil aus.

>[!NOTE]
>
>[!DNL Insight] Benutzer, die auf ein Datensatzprofil zugreifen, das auf einem Cluster ausgeführt wird, identifizieren nur die Übergeordneten [!DNL Insight Server] im [!DNL Insight] Konfigurationsdatei ( [!DNL insight.cfg]). Aus der Perspektive der [!DNL Insight] Benutzer, kann auf das Profil nur auf ein [!DNL Insight Server] (Übergeordnete [!DNL Insight Server]); Abfragen von Analysten können jedoch an eine der [!DNL Insight Servers] im Cluster.

Ein [!DNL Insight Server] Cluster ermöglicht die zentrale Speicherung von [!DNL .vsl] Protokolldateien (aus [!DNL Sensor]) in einem [!DNL Insight Server] Computer, bezeichnet als File Server Unit (FSU). Informationen zur Installation einer FSU finden Sie unter [Installationsverfahren für eine Insight Server-FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Informationen zum Konfigurieren einer FSU finden Sie unter *Anleitung zur Datensatzkonfiguration*.
