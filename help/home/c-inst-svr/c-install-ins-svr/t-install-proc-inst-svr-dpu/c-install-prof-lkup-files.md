---
description: Die Profile und Lookup-Dateien, die Adobe für Ihre jeweilige Anwendung entwickelt hat, sind interne Profile, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.
title: Installieren von Profilen und Lookup-Dateien
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 2%

---

# Installieren von Profilen und Lookup-Dateien{#installing-profiles-and-lookup-files}

{{eol}}

Die Profile und Lookup-Dateien, die Adobe für Ihre jeweilige Anwendung entwickelt hat, sind interne Profile, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.

Wie alle anderen von Adobe bereitgestellten internen Profile sollten diese Profile nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden.

Adobe verteilt die Profil- und Lookup-Dateien für Ihre Anwendung als [!DNL .zip] -Datei. Jede ZIP-Datei ist nach der Anwendung benannt, deren Profil- und Lookup-Dateien sie enthält. (Beispiel: [!DNL Site52.zip] enthält die Profildateien für Site v5.2.) Die [!DNL .zip] Datei enthält zwei Ordner ( [!DNL Lookups] und [!DNL Profiles]).

>[!NOTE]
>
>Wenn Sie noch nicht über die Installationsdatei mit den Profilen und Suchdateien für Ihre Anwendung verfügen, laden Sie sie vor dem Start von der Adobe-FTP-Site herunter.

Sie müssen das Profil und seine Lookup-Dateien auf der [!DNL Insight Server] Computer, auf dem Sie Ihr Datensatzprofil verarbeiten und ausführen. Wenn Sie eine [!DNL Insight Server] -Cluster, müssen Sie die Dateien auf dem Übergeordneten Server installieren. Informationen zu Datensatzprofilen finden Sie in der *Anleitung zur Datensatzkonfiguration*.

**So installieren Sie Profile für Ihre Adobe App**

1. Öffnen Sie die [!DNL Profiles] Ordner aus dem [!DNL .zip] -Datei, die Sie nach Adobe erhalten haben.

1. Kopieren Sie alle Ordner im [!DNL Profiles] im Ordner [!DNL .zip] in die [!DNL Profiles] Ordner in [!DNL Insight Server] Installationsverzeichnis. Sie möchten mit [!DNL ...\Profile\]*&lt; [!DNL internal profile name]>* Ordner in [!DNL Insight Server] wie im folgenden Beispiel gezeigt. Die tatsächlichen Profilnamen unterscheiden sich möglicherweise.

   ![](assets/win_installprofiles.png)

1. Navigieren Sie zum  [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* Ordner im Verzeichnis, in dem Sie installiert haben [!DNL Insight Server] und suchen Sie nach [!DNL profile.cfg] in diesem Verzeichnis.

   >[!NOTE]
   >
   >Wenn Sie zum ersten Mal Profile installieren, können Sie das bereitgestellte Beispielprofil als Ihr Datensatzprofil verwenden. Sie finden die [!DNL profile.cfg] -Datei (sie kann in etwa wie folgt benannt werden: [!DNL profile.cfg.offline]) für das Beispielprofil im [!DNL Profiles\Sample] Ordner in [!DNL Insight Server] Installationsverzeichnis.

1. Öffnen Sie die [!DNL profile.cfg] Datei mit einem Texteditor wie Notepad verwenden und folgende Schritte ausführen:

   1. Fügen Sie im Ordner-Vektor Einträge für die internen Profile hinzu. Die Profilnamen entsprechen den Namen der Ordner, die Sie in die [!DNL Profiles] Ordner auf [!DNL Insight Server] Maschine.

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
      >Die *serverCommonName* , den Sie für den allgemeinen Namen im [!DNL profile.cfg] -Datei entspricht dem allgemeinen Servernamen für die [!DNL Insight Server] Computer, auf dem Sie das Datensatzprofil verarbeiten und ausführen. Aktualisierungsanweisungen [!DNL profile.cfg] , damit das Datensatzprofil auf einem [!DNL Insight Server] Cluster, siehe [Insight Server-Cluster](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Speichern Sie die Datei. Achten Sie darauf, die Datei als [!DNL profile.cfg] , wenn sie anders benannt wurde.

**So installieren Sie die Lookup-Dateien für Ihre Adobe App**

1. Öffnen Sie die [!DNL Lookups] Ordner aus dem [!DNL .zip] -Datei, die Sie nach Adobe erhalten haben.

1. Kopieren Sie alle Ordner im [!DNL Lookups] im Ordner [!DNL .zip] in die [!DNL Lookups] Ordner in [!DNL Insight Server] Installationsverzeichnis. Sie möchten mit [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]>* Ordner in [!DNL Insight Server] wie im folgenden Beispiel gezeigt. Die tatsächlichen Profilnamen unterscheiden sich möglicherweise.

   ![](assets/win_installLookups.png)
