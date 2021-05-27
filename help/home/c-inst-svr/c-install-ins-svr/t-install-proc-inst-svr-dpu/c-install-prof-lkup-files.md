---
description: Die Profile und Lookup-Dateien, die Adobe für Ihre jeweilige Anwendung entwickelt hat, sind interne Profile, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.
title: Installieren von Profilen und Lookup-Dateien
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Installieren von Profilen und Lookup-Dateien{#installing-profiles-and-lookup-files}

Die Profile und Lookup-Dateien, die Adobe für Ihre jeweilige Anwendung entwickelt hat, sind interne Profile, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.

Wie alle anderen von Adobe bereitgestellten internen Profile sollten diese Profile nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Adobe verteilt die Profil- und Lookup-Dateien für Ihre Anwendung als [!DNL .zip]-Datei. Jede ZIP-Datei ist nach der Anwendung benannt, deren Profil- und Lookup-Dateien sie enthält. (Beispielsweise enthält [!DNL Site52.zip] die Profildateien für Site v5.2.) Die Datei [!DNL .zip] enthält zwei Ordner ( [!DNL Lookups] und [!DNL Profiles]).

>[!NOTE]
>
>Wenn Sie noch nicht über die Installationsdatei mit den Profilen und Suchdateien für Ihre Anwendung verfügen, laden Sie sie vor dem Start von der Adobe-FTP-Site herunter.

Sie müssen das Profil und seine Lookup-Dateien auf dem Computer [!DNL Insight Server] installieren, auf dem Sie Ihr Datensatzprofil verarbeiten und ausführen. Wenn Sie einen [!DNL Insight Server]-Cluster ausführen, müssen Sie die Dateien auf dem Übergeordneten Server installieren. Informationen zu Datensatzprofilen finden Sie im *Handbuch zur Datensatzkonfiguration*.

**So installieren Sie Profile für Ihre Adobe App**

1. Öffnen Sie den Ordner [!DNL Profiles] aus der [!DNL .zip]-Datei, die Sie nach Adobe erhalten haben.

1. Kopieren Sie alle Ordner im Ordner [!DNL Profiles] in der Datei [!DNL .zip] in den Ordner [!DNL Profiles] im Installationsverzeichnis von [!DNL Insight Server]. Sie möchten  [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]>*-Ordner auf Ihren [!DNL Insight Server]-Ordnern einfügen, wie im folgenden Beispiel gezeigt. Die tatsächlichen Profilnamen unterscheiden sich möglicherweise.

   ![](assets/win_installprofiles.png)

1. Navigieren Sie zum Ordner  [!DNL Profiles\]*&lt; [!DNL dataset profile name]* in dem Verzeichnis, in dem Sie [!DNL Insight Server] installiert haben, und suchen Sie die Datei [!DNL profile.cfg] in diesem Verzeichnis.

   >[!NOTE]
   >
   >Wenn Sie zum ersten Mal Profile installieren, können Sie das bereitgestellte Beispielprofil als Ihr Datensatzprofil verwenden. Sie finden die Datei [!DNL profile.cfg] (sie kann etwa [!DNL profile.cfg.offline] genannt werden) für das Beispielprofil im Ordner [!DNL Profiles\Sample] im Installationsverzeichnis [!DNL Insight Server] .

1. Öffnen Sie die Datei [!DNL profile.cfg] mithilfe eines Texteditors wie Notepad und führen Sie die folgenden Schritte aus:

   1. Fügen Sie im Ordner-Vektor Einträge für die internen Profile hinzu. Die Profilnamen entsprechen den Namen der Ordner, die Sie in den Ordner [!DNL Profiles] auf dem Computer [!DNL Insight Server] kopiert haben.

   1. Aktualisieren Sie die Anzahl der Verzeichnisse entsprechend.
   1. Fügen Sie den allgemeinen Namen des Servers zur Zeile &quot;Common Name&quot;in dieser Datei hinzu, wie unten hervorgehoben:

      ```
      Profile = profileInfo: 
      Directories = vector: n+1 items
        0 = string: Base\\
        1 = string: internal profile name 1\\
        2 = string: internal profile name 2\\
      . . .
        n = string: internal profile name n\\
      Processing Servers = vector: 1 items
        0 = ProfileServerInfo: 
          Common Name = string: serverCommonName
          Server = string: 
      ```

      >[!NOTE]
      >
      >Der *serverCommonName*, den Sie für den allgemeinen Namen in der Datei [!DNL profile.cfg] angeben, entspricht dem allgemeinen Servernamen für den [!DNL Insight Server]-Computer, auf dem Sie das Datensatzprofil verarbeiten und ausführen. Anweisungen zum Aktualisieren von [!DNL profile.cfg], sodass das Datensatzprofil auf einem [!DNL Insight Server]-Cluster ausgeführt wird, finden Sie unter [Insight Server-Cluster](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Speichern Sie die Datei. Achten Sie darauf, die Datei als [!DNL profile.cfg] zu speichern, wenn sie anders benannt wurde.

**So installieren Sie die Lookup-Dateien für Ihre Adobe App**

1. Öffnen Sie den Ordner [!DNL Lookups] aus der [!DNL .zip]-Datei, die Sie nach Adobe erhalten haben.

1. Kopieren Sie alle Ordner im Ordner [!DNL Lookups] in der Datei [!DNL .zip] in den Ordner [!DNL Lookups] im Installationsverzeichnis von [!DNL Insight Server]. Sie möchten  [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]>*-Ordner auf Ihren [!DNL Insight Server]-Ordnern einfügen, wie im folgenden Beispiel gezeigt. Die tatsächlichen Profilnamen unterscheiden sich möglicherweise.

   ![](assets/win_installLookups.png)
