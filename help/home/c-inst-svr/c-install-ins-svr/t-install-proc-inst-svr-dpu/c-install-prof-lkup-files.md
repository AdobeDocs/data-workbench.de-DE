---
description: Die Profil und Lookup-Dateien, die Adobe für Ihre Anwendung entwickelt hat, sind interne Profil, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.
title: Installieren von Profilen und Lookup-Dateien
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Installieren von Profilen und Lookup-Dateien{#installing-profiles-and-lookup-files}

Die Profil und Lookup-Dateien, die Adobe für Ihre Anwendung entwickelt hat, sind interne Profil, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.

Wie bei allen anderen internen Profilen der Adobe sollten diese Profil nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Adobe verteilt das Profil und die Lookup-Dateien für Ihre Anwendung als [!DNL .zip]-Datei. Jede ZIP-Datei ist nach der Anwendung benannt, deren Profil- und Nachschlagedateien sie enthält. (Zum Beispiel enthält [!DNL Site52.zip] die Profil-Dateien für Site v5.2.) Die Datei [!DNL .zip] enthält zwei Ordner ( [!DNL Lookups] und [!DNL Profiles]).

>[!NOTE]
>
>Wenn Sie noch nicht über die Installationsdatei mit den Profilen und Nachschlagedateien für Ihre Anwendung verfügen, laden Sie sie vor dem Start von der Adobe-FTP-Site herunter.

Sie müssen das Profil und seine Nachschlagedateien auf dem [!DNL Insight Server]-Computer installieren, auf dem Sie Ihr DataSet-Profil verarbeiten und ausführen. Wenn Sie einen [!DNL Insight Server]-Cluster ausführen, müssen Sie die Dateien auf dem Übergeordnet-Server installieren. Weitere Informationen zu DataSet-Profilen finden Sie im Handbuch *Konfiguration von DataSet*.

**So installieren Sie Profil für Ihre Adobe**

1. Öffnen Sie den Ordner [!DNL Profiles] aus der [!DNL .zip]-Datei, die Sie nach Adobe erhalten haben.

1. Kopieren Sie alle Ordner im Ordner [!DNL Profiles] in der Datei [!DNL .zip] in den Ordner [!DNL Profiles] im Installationsordner [!DNL Insight Server]. Sie möchten mit  [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]*-Ordnern auf [!DNL Insight Server] enden, wie im folgenden Beispiel gezeigt. Ihre tatsächlichen Profil können sich unterscheiden.

   ![](assets/win_installprofiles.png)

1. Navigieren Sie zum Ordner  [!DNL Profiles\]*&lt; [!DNL dataset profile name]* in dem Ordner, in dem Sie [!DNL Insight Server] installiert haben, und suchen Sie die [!DNL profile.cfg]-Datei in diesem Ordner.

   >[!NOTE]
   >
   >Wenn Sie Profil zum ersten Mal installieren, können Sie das bereitgestellte Beispiel-Profil als DataSet-Profil verwenden. Sie können die [!DNL profile.cfg]-Datei (sie kann etwa [!DNL profile.cfg.offline]) für das Beispielordner im [!DNL Profiles\Sample]-Profil im [!DNL Insight Server]-Installationsordner finden.

1. Öffnen Sie die Datei [!DNL profile.cfg] mit einem Texteditor wie Notepad und führen Sie die folgenden Schritte aus:

   1. hinzufügen Einträge für die internen Profil im Ordner-Vektor. Die Profil entsprechen den Ordnernamen, die Sie auf dem [!DNL Insight Server]-Computer in den Ordner [!DNL Profiles] kopiert haben.

   1. Aktualisieren Sie die Anzahl der Ordner entsprechend.
   1. hinzufügen Sie den allgemeinen Namen des Servers in die Zeile &quot;Allgemeiner Name&quot;in dieser Datei ein, wie nachfolgend hervorgehoben:

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
      >Der *serverCommonName*, den Sie für den Common Name in der [!DNL profile.cfg]-Datei angeben, entspricht dem gemeinsamen Servernamen für den [!DNL Insight Server]-Computer, auf dem Sie das DataSet-Profil verarbeiten und ausführen. Anweisungen zum Aktualisieren von [!DNL profile.cfg], sodass das DataSet-Profil auf einem [!DNL Insight Server]-Cluster ausgeführt wird, finden Sie unter [Insight Server-Cluster](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Speichern Sie die Datei. Achten Sie darauf, die Datei als [!DNL profile.cfg] zu speichern, wenn sie anders benannt wurde.

**So installieren Sie die Nachschlagedateien für Ihre Adobe**

1. Öffnen Sie den Ordner [!DNL Lookups] aus der [!DNL .zip]-Datei, die Sie nach Adobe erhalten haben.

1. Kopieren Sie alle Ordner im Ordner [!DNL Lookups] in der Datei [!DNL .zip] in den Ordner [!DNL Lookups] im Installationsordner [!DNL Insight Server]. Sie möchten mit  [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]*-Ordnern auf [!DNL Insight Server] enden, wie im folgenden Beispiel gezeigt. Ihre tatsächlichen Profil können sich unterscheiden.

   ![](assets/win_installLookups.png)
