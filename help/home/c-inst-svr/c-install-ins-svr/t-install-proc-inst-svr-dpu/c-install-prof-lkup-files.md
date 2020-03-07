---
description: Die Profile und Lookup-Dateien, die Adobe für Ihre jeweilige Anwendung entwickelt hat, sind interne Profile, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.
solution: Insight
title: Installieren von Profilen und Suchdateien
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Installieren von Profilen und Suchdateien{#installing-profiles-and-lookup-files}

Die Profile und Lookup-Dateien, die Adobe für Ihre jeweilige Anwendung entwickelt hat, sind interne Profile, die die Metriken, Dimensionen und Arbeitsbereiche bereitstellen, die die Analyse Ihres Datensatzes ermöglichen.

Wie bei allen anderen von Adobe bereitgestellten internen Profilen sollten diese Profile nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz, in Ihren rollenspezifischen Profilen oder in anderen Profilen, die Sie erstellen, vorgenommen werden.

Adobe verteilt die Profil- und Lookup-Dateien für Ihre Anwendung als [!DNL .zip] Datei. Jede ZIP-Datei ist nach der Anwendung benannt, deren Profil- und Lookup-Dateien sie enthält. ( [!DNL Site52.zip] enthält beispielsweise die Profildateien für Site v5.2.) Die [!DNL .zip] Datei enthält zwei Ordner ( [!DNL Lookups] und [!DNL Profiles]).

>[!NOTE]
>
>Wenn Sie noch nicht über die Installationsdatei verfügen, die die Profile und Lookup-Dateien für Ihre Anwendung enthält, laden Sie diese von der Adobe FTP-Site herunter, bevor Sie beginnen.

Sie müssen das Profil und die zugehörigen Lookup-Dateien auf dem [!DNL Insight Server] Computer installieren, auf dem Sie Ihr DataSet-Profil verarbeiten und ausführen. Wenn Sie einen [!DNL Insight Server] Cluster ausführen, müssen Sie die Dateien auf dem Master-Server installieren. Weitere Informationen zu Datensatzprofilen finden Sie im Handbuch zur Konfiguration von *DataSet*.

**So installieren Sie Profile für Ihre Adobe-Anwendung**

1. Öffnen Sie den [!DNL Profiles] Ordner aus der [!DNL .zip] Datei, die Ihnen von Adobe bereitgestellt wird.

1. Kopieren Sie alle Ordner im [!DNL Profiles] Ordner der [!DNL .zip] Datei in den [!DNL Profiles] Ordner im [!DNL Insight Server] Installationsordner. Sie wollen am Ende mit [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>* Ordner auf Ihrer [!DNL Insight Server] Seite, wie im folgenden Beispiel gezeigt. Ihre tatsächlichen Profilnamen können sich unterscheiden.

   ![](assets/win_installprofiles.png)

1. Navigieren Sie zum Ordner [!DNL Profiles\]*&lt;[!DNL dataset profile name]>* in dem Ordner, in dem Sie die Datei installiert haben, [!DNL Insight Server] und suchen Sie die [!DNL profile.cfg] Datei in diesem Ordner.

   >[!NOTE]
   >
   >Wenn Sie Profile zum ersten Mal installieren, können Sie das bereitgestellte Musterprofil als Ihr Datenasetprofil verwenden. Sie können die [!DNL profile.cfg] Datei (sie kann ungefähr so benannt sein [!DNL profile.cfg.offline]) für das Beispielprofil im [!DNL Profiles\Sample] Ordner in Ihrem [!DNL Insight Server] Installationsverzeichnis suchen.

1. Öffnen Sie die [!DNL profile.cfg] Datei mit einem Texteditor wie Notepad und führen Sie die folgenden Schritte aus:

   1. Fügen Sie Einträge für die internen Profile im Ordner-Vektor hinzu. Die Profilnamen entsprechen den Namen der Ordner, die Sie in den [!DNL Profiles] Ordner auf dem [!DNL Insight Server] Computer kopiert haben.

   1. Aktualisieren Sie die Anzahl der Ordner entsprechend.
   1. Fügen Sie der Zeile &quot;Allgemeiner Name&quot;in dieser Datei den gemeinsamen Namen des Servers hinzu, wie nachfolgend hervorgehoben:

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
      >Der *serverCommonName* , den Sie für den Common Name in der [!DNL profile.cfg] -Datei angeben, entspricht dem gebräuchlichen Servernamen des [!DNL Insight Server] Computers, auf dem Sie das DataSet-Profil verarbeiten und ausführen. Anweisungen zum Aktualisieren, [!DNL profile.cfg] sodass das Datenset-Profil auf einem [!DNL Insight Server] Cluster ausgeführt wird, finden Sie unter [Insight Server-Cluster](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Speichern Sie die Datei. Achten Sie darauf, die Datei so zu speichern, als ob sie anders benannt [!DNL profile.cfg] wäre.

**So installieren Sie die Lookup-Dateien für Ihre Adobe-Anwendung**

1. Öffnen Sie den [!DNL Lookups] Ordner aus der [!DNL .zip] Datei, die Ihnen von Adobe bereitgestellt wird.

1. Kopieren Sie alle Ordner im [!DNL Lookups] Ordner der [!DNL .zip] Datei in den [!DNL Lookups] Ordner im [!DNL Insight Server] Installationsordner. Sie wollen am Ende mit [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>* Ordner auf Ihrer [!DNL Insight Server] Seite, wie im folgenden Beispiel gezeigt. Ihre tatsächlichen Profilnamen können sich unterscheiden.

   ![](assets/win_installLookups.png)

