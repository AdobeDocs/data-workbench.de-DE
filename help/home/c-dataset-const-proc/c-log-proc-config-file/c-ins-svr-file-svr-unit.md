---
description: Informationen zu Insight Server-Dateiservereinheiten und dem Dateiserverkonfigurationsprozess.
title: Konfigurieren der Data Workbench File Server Unit
uuid: ccb65952-f017-4434-b2f8-74c274450834
exl-id: 19b8c08a-e9f2-47ab-ad9f-1fddfbd9d249
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 1%

---

# Konfigurieren der Data Workbench File Server Unit{#configuring-a-data-workbench-server-file-server-unit}

Informationen zu Insight Server-Dateiservereinheiten und dem Dateiserverkonfigurationsprozess.

<!--
c_abt_file_svr_units.xml
-->

Sie können den Data Workbench-Server (InsightServer64.exe) so konfigurieren, dass er als File Server Unit (FSU) ausgeführt wird, indem Sie die Parameter im Knoten **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** der Datei [!DNL Log Processing.cfg] ausfüllen. Wenn der Data Workbench-Server für die Ausführung als FSU konfiguriert ist, speichert er Quelldateien ( [!DNL .vsl]-Dateien, Textdateien oder XML-Dateien), auf die von mehreren Verarbeitungsservern (DPUs) schnell zugegriffen werden kann. Wenn die DPUs in einem Data Workbench-Servercluster auf das FSU zugreifen, um die Protokolldateien zu lesen, teilen sie die Protokolldateien unter sie auf und stellen sicher, dass dieselbe Datei nicht mehr als einmal verarbeitet wird.

>[!NOTE]
>
>Beim Einrichten einer FSU, die einen Data Workbench-Servercluster mit fünf bis zehn DPU bereitstellt, sollten Sie den Cluster-Übergeordnet-Server zur FSU machen.

Weitere Informationen zum Installieren eines Data Workbench-Serverclusters finden Sie im *Handbuch zur Installation und Verwaltung von Serverprodukten*.

<!--
c_file_svr_config_proc.xml
-->

Wenn der Speicherort ein Remote-Speicherort ist, stellt der Data Workbench-Servercomputer, der die Daten verarbeitet, eine Verbindung zum angegebenen Remotecomputer her, um die Protokolle zu lesen.

Auf dem Datenbasis-Servercomputer, der als FSU ausgeführt werden soll, können die DPUs mit der Datei [!DNL Access Control.cfg] eine Verbindung zum FSU herstellen, und die Datei [!DNL Communications.cfg] ordnet den Speicherort der Remote-Datendateien zu. Die Prozessschritte zum Konfigurieren eines FSU lauten wie folgt:

1. Geben Sie in der Datei [!DNL Log Processing.cfg] auf Ihrem Übergeordnet Data Workbench-Server den Typ der Datenquelle und den Speicherort der Quelle an. Siehe [Datenquelle angeben](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383).

1. Bearbeiten Sie in der Datei [!DNL Access Control.cfg] auf der FSU die Berechtigungen, damit die DPUs eine Verbindung mit der FSU herstellen können, um die Protokolldaten zu lesen. Siehe [Bearbeiten der Berechtigungen auf der Dateiservereinheit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef).

1. Bearbeiten Sie in der Datei [!DNL Communications.cfg] auf der FSU die Einstellungen für die Einträge [!DNL LoggingServer] und [!DNL FileServer], um den Speicherort der Protokolldateien anzugeben. Siehe [Angabe des Speicherorts der Protokolldateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0).

1. Wenn Sie Ihr DataSet-Profil für die Ausführung auf einem Data Workbench-Servercluster konfigurieren, müssen Sie außerdem das Cluster-FSU zum Server machen, auf dem alle Dimensionen des Profils erstellt werden:
(Nur für Data Workbench-Server-Cluster) Fügen Sie in den Dateien [!DNL Communications.cfg] und [!DNL cluster.cfg] auf der FSU Einträge für einen &quot;Normalize-Server&quot;hinzu, um die FSU zum Server im Cluster zu machen, auf dem alle Dimensionen erstellt werden. Siehe [Erstellen eines zentralisierten Normalisierungsservers für einen Cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Anweisungen zum Konfigurieren eines DataSet-Profils, das von einem Data Workbench-Servercluster verarbeitet werden soll, finden Sie im *Handbuch zur Installation und Verwaltung von Serverprodukten*.

>[!NOTE]
>
>In den folgenden Anweisungen wird davon ausgegangen, dass sich alle Protokolldateien im Standardordner befinden. Wenn Sie Protokolle in einem anderen Ordner speichern oder mehrere Protokollpfade erstellen möchten, wenden Sie sich an Adobe Consulting Services, um Ihre spezifische Konfiguration zu besprechen.

## Datenquelle {#section-d2b545db7ab142ffb4be32e040395383} angeben

Bei der Angabe von Remote-Datenquellen für einen Datensatz müssen Sie den Typ der Datenquelle und den Speicherort der Protokolldateien auf Ihrem Übergeordnet Data Workbench-Server angeben.

**So legen Sie die Datenquelle und ihren Speicherort fest**

1. Öffnen Sie die Datei [!DNL Log Processing.cfg]. Siehe [Bearbeiten der Konfigurationsdatei für die Protokollverarbeitung](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

1. hinzufügen einer Protokolldatei oder XML-Datenquelle. [!DNL Sensor] Siehe [Protokolldateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Füllen Sie den Parameter &quot;Protokollpfade&quot;aus. Siehe [Sensordateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009), [Protokolldateien](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e) oder [XML-Protokollquellen](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887). Achten Sie darauf, einen gültigen URI anzugeben.

1. Führen Sie die in der folgenden Tabelle definierten Parameter für den Protokollserver aus:

<table id="table_5881B8DEFF984BC7A620CEEA3A637912"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Name, der den Remote-Dateiserver identifiziert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Server - Allgemeiner Name </td> 
   <td colname="col2"> <p> <span class="wintitle"> Server Common </span> Namelisted on the file server's SSL certificate. </p> <p> Dieser Parameter ist optional, wenn SSL</span> verwenden auf false eingestellt ist.<span class="wintitle"> </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> <p>Adresse des Dateiservercomputers. Kann leer gelassen werden, wenn <span class="wintitle"> Name</span> <span class="wintitle"> SSL-Server Allgemeiner Name</span> entspricht. </p> <p> Beispiel: <span class="filepath"> visual.mycompany.com</span> oder 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anschluss </td> 
   <td colname="col2"> Anschluss, über den der Data Workbench-Servercomputer mit dem Dateiserver kommuniziert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-Client-Zertifikat </td> 
   <td colname="col2"> Name der Datei <span class="wintitle"> SSL-Zertifikat</span> für den Data Workbench-Server (<span class="filepath"> server_cert.pem</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL verwenden </td> 
   <td colname="col2"> Wahr oder falsch. True bedeutet, dass der Dateiserver <span class="wintitle"> SSL</span> verwendet. </td> 
  </tr> 
 </tbody> 
</table>

Wenn ein Proxyserver erforderlich ist, damit die DPUs eine Verbindung zum FSU herstellen können, müssen Sie die folgenden Parameter ausführen:

| Parameter | Beschreibung |
|---|---|
| Proxy-Adresse | Die Adresse eines Proxyservers, die der Data Workbench-Server für den Zugriff auf den Dateiserver verwenden muss. |
| Proxy-Kennwort | Optional. Das Kennwort für den Proxyserver. |
| Proxyanschluss | Der Anschluss des Proxyservers. Die Standardeinstellung ist „8080“. |
| Proxy-Benutzername | Optional. Der Benutzername für den Proxyserver. |

Im Folgenden finden Sie ein Beispiel für ein definiertes [!DNL Log Server] in der Datei [!DNL Log Processing.cfg]. Protokollquelle Nr. 1 ist eine Protokolldatei-Quelle, die auf einen Ordner mit dem Namen Logs (beachten Sie den im Parameter Log Paths angegebenen URI) auf dem Computer mit dem Namen FSU01 verweist.

![](assets/cfg_LogProcessing_LogServer.png)

## Bearbeiten der Berechtigungen auf der Dateiservereinheit {#section-b4a54b591b4e4435a728a67f194057ef}

Im vorherigen Prozess haben Sie ein Profil für einen bestimmten Datensatz konfiguriert, um Protokolldateien eines FSU zu lesen. Jetzt müssen Sie die Berechtigungen für das FSU bearbeiten, um Verbindungen von den DPUs zuzulassen, die das Profil ausführen. Die folgenden Schritte führen Sie durch die Bearbeitung der Berechtigungsdatei [!DNL Access Control.cfg].

**So bearbeiten Sie Berechtigungen für das FSU**

1. Öffnen Sie das [!DNL Server Files Manager] für den Data Workbench-Servercomputer, den Sie als FSU einrichten, und klicken Sie auf **[!UICONTROL Access Control]**, um den Inhalt anzuzeigen.

   Informationen zum Öffnen und Arbeiten mit [!DNL Server Files Manager] finden Sie im *Data Workbench Benutzerhandbuch*.

1. Klicken Sie im Fenster [!DNL Server Files Manager] auf **[!UICONTROL Access Control]**, um den Inhalt anzuzeigen. Die Datei [!DNL Access Control.cfg] befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte Servername für [!DNL Access Control.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Access Control.cfg] wird ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen unter der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Klicken Sie im Fenster [!DNL Access Control] auf **[!UICONTROL Access Control Groups]**, um den Inhalt anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf die numerische Beschriftung für das letzte [!DNL AccessGroup] in der Liste und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Geben Sie ein [!DNL Name] für das neue [!DNL AccessGroup] ein. Beispiel: Server anschließen.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Member]** unter dem neuen [!DNL AccessGroup] und klicken Sie dann auf **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Geben Sie die IP-Adresse für die DPU des Data Workbench-Servers ein, die eine Verbindung zu diesem Dateiserver herstellt.
1. Wiederholen Sie die Schritte 4 und 5 für alle anderen Data Workbench-Server-DPUs, die eine Verbindung zu diesem FSU herstellen, einschließlich der Data Workbench-Server-DPUs in einem Cluster, das auf die Protokolldateien zugreifen muss.
1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Read-Only Access]** unter dem neuen [!DNL AccessGroup] und klicken Sie dann auf **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Geben Sie den Speicherort der gespeicherten Protokolldateien auf dem Dateiservercomputer ein. Verwenden Sie Schrägstriche (/) in der Pfadspezifikation. Der Standardspeicherort ist /Logs/.
1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und dann auf **[!UICONTROL Save]**.

1. Klicken Sie im Fenster [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Access Control.cfg] in der Spalte [!DNL Temp] und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL server name]**, um die lokal vorgenommenen Änderungen an der FSU des Data Workbench-Servers zu speichern.

## Speicherort der Protokolldateien {#section-f9a649bf1b2544feb10ad8820384edb0} angeben

Sie müssen die Datei [!DNL Communications.cfg] auf der FSU bearbeiten, um den Speicherort der Protokolldateien anzugeben.

**So legen Sie den Speicherort der Protokolldateien fest**

1. Klicken Sie im Fenster [!DNL Server Files Manager] auf **[!UICONTROL Components]**, um den Inhalt anzuzeigen. Die Datei [!DNL Communications.cfg] befindet sich in diesem Verzeichnis.

1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte Servername für [!DNL Communications.cfg] und klicken Sie dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Communications.cfg] wird ein Häkchen angezeigt.

1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen unter der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. Klicken Sie im Fenster [!DNL Communications.cfg] auf **[!UICONTROL component]**, um den Inhalt anzuzeigen.

1. Klicken Sie im Fenster [!DNL Communications.cfg] auf **[!UICONTROL Servers]**, um den Inhalt anzuzeigen. Es können mehrere Server angezeigt werden: Dateiserver, Protokollierungsserver, Initserver, Statusserver, Senden-Server oder Replizieren von Servern.

1. (Nur für [!DNL Sensor]-Protokollquellen) Suchen Sie die [!DNL LoggingServer]-Variable, bei der [!DNL Sensor] die Protokolldateien schreibt, die vom Data Workbench-Server verarbeitet werden sollen, und klicken Sie dann auf die entsprechende Nummer, um das Menü Ansicht. Bearbeiten Sie den Parameter Protokollverzeichnis, um den gewünschten Speicherort der Protokolldateien anzuzeigen. Der Standardprotokollordner ist der Ordner &quot;Protokolle&quot;im Installationsordner des Data Workbench-Servers.

   Ändern Sie keine anderen Parameter für [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Suchen Sie den FileServer, der den Speicherort der Protokolldateien angibt. Unter &quot;Server&quot;werden möglicherweise mehrere Dateiserver aufgelistet. Daher müssen Sie die Inhalte für viele dieser Server (durch Klicken auf die Servernummer) ggf. Ansicht haben, um den gewünschten Server zu finden.
1. Bearbeiten Sie die Parameter [!DNL Local Path] und URI für FileServer, um den Speicherort der Protokolldateien anzuzeigen. Das folgende Beispiel zeigt, dass sich die Protokolldateien im Ordner &quot;Protokolle&quot;im Installationsordner des Data Workbench-Servers befinden:

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Wenn die Parameter [!DNL Local Path] und URI wie gezeigt aufgefüllt werden, können Sie von jedem Data Workbench-Server aus auf die Protokolldateien im FSU zugreifen, indem Sie im [!DNL Server Files Manager] auf [!DNL Logs] klicken.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Konfigurationsfenster und dann auf **[!UICONTROL Save]**.

1. Klicken Sie im Fenster [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Communications.cfg] in der Spalte [!DNL Temp] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***, um die lokal vorgenommenen Änderungen im FSU des Data Workbench-Servers zu speichern.

## Erstellen eines zentralisierten Normalisierungsservers für einen Cluster {#section-2c1f57b683f94cc193bc069e886bba28}

Wenn Sie Ihr DataSet-Profil für die Ausführung auf einem Data Workbench-Servercluster konfigurieren, sollten Sie das Cluster-FSU zum Server machen, auf dem alle Dimensionen des Profils erstellt werden.

Adobe empfiehlt dringend, dass die FSU des Clusters als Übergeordnet-Server des Clusters und dessen zentralisierten Normalisierungsserver dient.

Um die FSU zum zentralisierten Normalisierungsserver zu machen, müssen Sie die Dateien [!DNL Communications.cfg] und [!DNL Cluster.cfg] auf der FSU öffnen und bearbeiten.

**So machen Sie das FSU zum zentralisierten Normalisierungsserver**

1. hinzufügen Sie einen [!DNL NormalizeServer]-Eintrag in die [!DNL Communications.cfg]-Datei in der FSU.

   >[!NOTE]
   >
   >Wenn Sie das vollständige Release-Paket für den Data Workbench-Server Version 5.0 oder höher installiert haben, sollte die [!DNL Communications.cfg]-Datei in Ihrer FSU bereits einen [!DNL NormalizeServer]-Eintrag enthalten. Gehen Sie wie folgt vor, um zu bestätigen, dass der Eintrag vorhanden ist.

   1. Öffnen Sie die Datei [!DNL Communications.cfg] in Data Workbench, wie unter [Speicherort der Protokolldateien](#section-f9a649bf1b2544feb10ad8820384edb0) angegeben.

   1. Klicken Sie auf **[!UICONTROL component]**, um den Inhalt anzuzeigen.
   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Servers]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. Geben Sie im URI-Parameter für [!DNL NormalizeServer] [!DNL /Cluster/] ein.

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie im Fenster [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Communications.cfg] in der Spalte [!DNL Temp] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>*, um die lokal vorgenommenen Änderungen am Data Workbench-Server-FSU zu speichern.

1. Definieren Sie den zentralisierten Normalisierungsserver in der Datei [!DNL Cluster.cfg] auf dem Übergeordnet-Server im Data Workbench-Servercluster.

   >[!NOTE]
   >
   >Wenn die FSU, auf der Sie den zentralisierten Normalisierungsserver einrichten, nicht der Übergeordnet Data Workbench-Server im Cluster ist, müssen Sie die IP-Adressen der DPUs im Cluster zur Zugriffsgruppe [!DNL Cluster Servers] in der FSU-Datei [!DNL Access Control.cfg] hinzufügen. Anweisungen zum Hinzufügen von Servern zur Gruppe [!DNL Cluster Servers] finden Sie im Abschnitt Aktualisieren der Clusterdatei im *Handbuch zur Installation und Verwaltung von Serverprodukten.*

   1. Öffnen Sie das [!DNL Profile Manager] in Ihrem DataSet-Profil und klicken Sie dann auf **[!UICONTROL Dataset]**, um den Inhalt anzuzeigen. Die Datei [!DNL Cluster.cfg] befindet sich in diesem Verzeichnis.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Cluster.cfg] und dann auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.

   1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.

   1. hinzufügen Sie den Text, der im folgenden Dateifragment hervorgehoben wird:

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >Wenn Sie den allgemeinen Namen von FSU für den Parameter SSL Server Common Name eingeben, verwendet das FSU seine [!DNL .address]-Datei, um den gemeinsamen Namen aufzulösen. Weitere Informationen zur Datei [!DNL .address] finden Sie im *Server Products Installations- und Administrationshandbuch*.

   1. Speichern Sie die Datei.
   1. Klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für [!DNL Cluster.cfg] in der Spalte [!DNL User] und dann auf **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]***, um die lokal vorgenommenen Änderungen am DataSet-Profil zu speichern.
