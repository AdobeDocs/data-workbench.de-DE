---
description: Die Profil und Lookup-Dateien, die Adobe für Ihre Anwendung entwickelt hat, sind interne Profil, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.
solution: Analytics
title: Installieren von Profilen und Lookup-Dateien
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---


# Installieren von Profilen und Lookup-Dateien{#installing-profiles-and-lookup-files}

Die Profil und Lookup-Dateien, die Adobe für Ihre Anwendung entwickelt hat, sind interne Profil, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.

Wie bei allen anderen internen Profilen der Adobe sollten diese Profil nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Adobe verteilt das Profil und die Lookup-Dateien für Ihre Anwendung als [!DNL .zip] Datei. Jede ZIP-Datei ist nach der Anwendung benannt, deren Profil- und Nachschlagedateien sie enthält. ( [!DNL Site52.zip] enthält beispielsweise die Profil-Dateien für Site v5.2.) Die [!DNL .zip] Datei enthält zwei Ordner ( [!DNL Lookups] und [!DNL Profiles]).

>[!NOTE]
>
>Wenn Sie noch nicht über die Installationsdatei mit den Profilen und Nachschlagedateien für Ihre Anwendung verfügen, laden Sie sie vor dem Start von der Adobe-FTP-Site herunter.

Sie müssen das Profil und seine Nachschlagedateien auf dem [!DNL Insight Server] Computer installieren, auf dem Sie Ihr DataSet-Profil verarbeiten und ausführen. Wenn Sie einen [!DNL Insight Server] Cluster ausführen, müssen Sie die Dateien auf dem Übergeordnet-Server installieren. Weitere Informationen zu DataSet-Profilen finden Sie im Handbuch zur Konfiguration von *DataSet*.

**So installieren Sie Profil für Ihre Adobe**

1. Öffnen Sie den [!DNL Profiles] Ordner aus der [!DNL .zip] Datei, die Sie nach Adobe erhalten haben.

1. Kopieren Sie alle Ordner im [!DNL Profiles] Ordner der [!DNL .zip] Datei in den [!DNL Profiles] Ordner im [!DNL Insight Server] Installationsordner. Am Ende sollten Sie mit  [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>* Ordnern auf Ihrer Seite beginnen, wie im folgenden Beispiel gezeigt [!DNL Insight Server] . Ihre tatsächlichen Profil können sich unterscheiden.

   ![](assets/win_installprofiles.png)

1. Navigieren Sie zum  [!DNL Profiles\]*Ordner&lt;[!DNL dataset profile name]>* in dem Ordner, in dem Sie die Datei installiert haben, [!DNL Insight Server] und suchen Sie die [!DNL profile.cfg] Datei in diesem Ordner.

   >[!NOTE]
   >
   >Wenn Sie Profil zum ersten Mal installieren, können Sie das bereitgestellte Beispiel-Profil als DataSet-Profil verwenden. Sie können die [!DNL profile.cfg] Datei für das Beispiel-Profil im [!DNL profile.cfg.offline]Installationsordner (z. B. mit einem Namen wie [!DNL Profiles\Sample] ) suchen [!DNL Insight Server] .

1. Öffnen Sie die [!DNL profile.cfg] Datei mit einem Texteditor wie Notepad und führen Sie die folgenden Schritte aus:

   1. hinzufügen Einträge für die internen Profil im Ordner-Vektor. Die Namen der Profile entsprechen den Ordnernamen, die Sie in den [!DNL Profiles] Ordner auf dem [!DNL Insight Server] Computer kopiert haben.

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
      >Der *serverCommonName* , den Sie für den Common Name in der [!DNL profile.cfg] Datei angeben, entspricht dem gebräuchlichen Servernamen des [!DNL Insight Server] Computers, auf dem Sie das DataSet-Profil verarbeiten und ausführen. Anweisungen zum Aktualisieren, [!DNL profile.cfg] sodass das DataSet-Profil auf einem [!DNL Insight Server] Cluster ausgeführt wird, finden Sie unter [Insight Server-Cluster](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Speichern Sie die Datei. Achten Sie darauf, die Datei so zu speichern, als ob sie anders benannt [!DNL profile.cfg] wäre.

**So installieren Sie die Nachschlagedateien für Ihre Adobe**

1. Öffnen Sie den [!DNL Lookups] Ordner aus der [!DNL .zip] Datei, die Sie nach Adobe erhalten haben.

1. Kopieren Sie alle Ordner im [!DNL Lookups] Ordner der [!DNL .zip] Datei in den [!DNL Lookups] Ordner im [!DNL Insight Server] Installationsordner. Am Ende sollten Sie mit  [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>* Ordnern auf Ihrer Seite beginnen, wie im folgenden Beispiel gezeigt [!DNL Insight Server] . Ihre tatsächlichen Profil können sich unterscheiden.

   ![](assets/win_installLookups.png)

