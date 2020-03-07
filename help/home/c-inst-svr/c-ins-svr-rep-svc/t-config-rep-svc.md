---
description: Sie müssen den/die Insight-Zielserver so konfigurieren, dass Daten aus dem Repeater abgerufen werden, in dem die ursprünglichen Ereignisdaten gespeichert sind.
solution: Insight
title: Replizierungsdienst konfigurieren
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Replizierungsdienst konfigurieren{#configuring-the-replication-service}

Sie müssen den/die Insight-Zielserver so konfigurieren, dass Daten aus dem Repeater abgerufen werden, in dem die ursprünglichen Ereignisdaten gespeichert sind.

Um den Abruf von Daten von einem [!DNL Repeater] zu einem Ziel zu konfigurieren, müssen Sie die [!DNL Insight Server]Datei bearbeiten, die im [!DNL Replicate.cfg] Ordner auf dem Ziel bereitgestellt wird [!DNL Components] [!DNL Insight Server(s)] , wie im folgenden Verfahren beschrieben:

**So konfigurieren Sie die[!DNL Replication Service]auf dem Zielcomputer**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des Ziels, das [!DNL Insight Server] Sie konfigurieren möchten, und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie im [!DNL Server Files Manager]Fenster auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Replicate.cfg] Datei befindet sich in diesem Ordner.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Replicate.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL Replicate.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das [!DNL Replicate.cfg] Fenster wird geöffnet.
1. Klicken Sie im [!DNL Replicate.cfg] Fenster auf **[!UICONTROL Replicate.cfg]** und dann **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Bearbeiten Sie die Parameter mithilfe des folgenden Beispiels und der folgenden Tabelle als Hilfslinien:

   ![Schritt-Info](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Für diesen Parameter... </th> 
      <th colname="col2" class="entry"> Legen Sie... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Verzeichnisse </td> 
      <td colname="col2"> <p>Die Ordner im <span class="wintitle"> Repeater</span> , die in den Ziel- <span class="keyword"> Insight-Server</span>kopiert (repliziert) werden sollen. Der <span class="wintitle"> Replizierungsdienst</span> ermöglicht die Replizierung mehrerer Ordner aus einem einzigen <span class="wintitle"> Repeater</span>. </p> <p>Klicken Sie zum Hinzufügen eines neuen Ordners mit der rechten Maustaste auf <span class="uicontrol"> Verzeichnisse</span> und dann auf <span class="uicontrol"> Neue</span> hinzufügen &gt; <span class="uicontrol"> Verzeichnis</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Pfade reduzieren </td> 
      <td colname="col2"> <p>True oder false. Die durch die Einstellung dieses Parameters definierte Aktion hängt von der Einstellung des Parameters "Rekursiv"in dieser Datei ab: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Wenn "Rekursiv"den Wert "false"hat, hat "Reduzieren von Pfaden"keine Auswirkung. Es werden nur die Dateien auf der obersten Ebene des Ordners repliziert, der vom Remote-URI-Parameter angegeben wird. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Wenn "Rekursiv"den Wert "true"hat und "Flatten Paths"den Wert "false"hat, wird die Ordnerstruktur des Remote-Ordners (<span class="wintitle"> Repeater</span>) exakt im lokalen Pfad auf dem <span class="keyword"> Insight-Zielserver</span>dupliziert. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Wenn sowohl die Pfade "Rekursiv"als auch "Reduzieren"wahr sind, werden keine Unterordner im lokalen Pfad erstellt. Stattdessen werden alle Dateien aus der Verzeichnisstruktur des Remote-Ordners auf der obersten Ebene des lokalen Ordners abgelegt. </li>
      </ul></p> <p> <p>Hinweis: Wenn sowohl Reduzierte Pfade als auch Rekursive den Wert "true"haben und Dateien in den verschiedenen Unterordnern auf dem Remotecomputer denselben Namen haben, wird der <span class="wintitle"> Replizierungsdienst</span> möglicherweise beendet oder es kann zu einem anderen nicht definierten Verhalten kommen. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Lokaler Pfad </td> 
      <td colname="col2">Der Speicherort für die Dateien, die von <span class="wintitle"> Repeater</span>abgerufen werden. Der Pfad ist relativ zum Installationsordner des <span class="keyword"> Insight-Servers</span> . </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rekursiv </td> 
      <td colname="col2"> True oder false. Bei "false"werden nur die Dateien auf der obersten Ebene des Ordners repliziert, der vom Remote-URI-Parameter angegeben wird. Siehe Reduzieren von Pfaden in dieser Tabelle. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Remote-URI </td> 
      <td colname="col2">Der URI, einschließlich einer Dateimaske, um auf den Dateispeicher des <span class="wintitle"> Repeaters</span> zuzugreifen. Die Datei <span class="filepath"> Communications.cfg</span> im <span class="wintitle"> Repeater</span> sollte so konfiguriert sein, dass auf die Ereignisdaten mit diesem URI zugegriffen werden kann. Siehe <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Ereignisdatenraum</a>überwachen. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Server </td> 
      <td colname="col2">Parameter für den <span class="wintitle"> Repeater</span> , von dem der <span class="keyword"> Insight-Zielserver</span> Ereignisdatendateien abruft. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Name </td> 
      <td colname="col2">Optional. Der Name zum Identifizieren des <span class="wintitle"> Repeaters</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL-Server - Allgemeiner Name </td> 
      <td colname="col2">Nur erforderlich, wenn SSL verwenden auf true eingestellt ist. Allgemeiner Name des <span class="wintitle"> Repeaters</span> , in dem die Ereignisdaten gespeichert werden. Dieser Name muss mit dem im Kommunikationszertifikat für den Computer angegebenen gemeinsamen Namen übereinstimmen. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Adresse </td> 
      <td colname="col2">Hostname oder numerische IP-Adresse des <span class="wintitle"> Repeaters</span> , in dem die Ereignisdaten gespeichert werden. Der allgemeine Name des Servers ist kein gültiger Eintrag. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Anschluss </td> 
      <td colname="col2"> Für die Datenübertragung verwendeter Anschluss. Der Standardanschluss ist 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL-Client-Zertifikat </td> 
      <td colname="col2">Nur erforderlich, wenn SSL verwenden auf true eingestellt ist. Name des Lizenzzertifikats, das zum Herstellen einer Verbindung mit dem <span class="wintitle"> Repeater</span>verwendet wird. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL verwenden </td> 
      <td colname="col2"> <p>Bestimmt, ob SSL für die Datenübertragung verwendet wird. Die Optionen sind "true"oder "false", und der Standardwert ist "false". </p> <p> <p>Hinweis: Die Verwendung von SSL wird nicht empfohlen, da dies die Leistung beeinträchtigen kann. Beachten Sie, dass SSL nur dann erforderlich ist, wenn das Netzwerk, das den <span class="wintitle"> Repeater</span> mit den Zielcomputern verbindet, unsicher ist. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Endzeit, Startzeit </td> 
      <td colname="col2"> <p>(Optional) Beschränkt den Satz von Ereignisdatendateien, die in den Zielserver <span class="keyword"> Insight Server</span> kopiert wurden, auf die Dateien, die Daten im von Startzeit und Endzeit definierten Bereich enthalten. Wenn "Startzeit"festgelegt ist, werden Ereignisdatendateien, in denen alle Protokolleinträge aus einer früheren als der angegebenen Startzeit stammen, nicht kopiert. Wenn "Endzeit"festgelegt ist, werden Ereignisdatendateien, in die nicht alle Protokolleinträge aus der angegebenen oder späteren Zeit kopiert werden, nicht kopiert. Wenn nur ein Teil der Daten in einer Datei im angegebenen Bereich liegt, wird die gesamte Datei auf den Zielcomputer kopiert. </p> <p>Adobe empfiehlt die Verwendung eines der folgenden Formate: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1. Januar 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1. Januar 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Hinweis: Sie müssen eine Zeitzone angeben. Die Zeitzone wird nicht standardmäßig auf Systemzeit gesetzt, wenn sie nicht angegeben wird. Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechseln der Uhr implementieren möchten, müssen Sie die <span class="filepath"> .dst</span> -Datei mit den entsprechenden Regeln auf dem Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> -Computer speichern. Eine Liste der unterstützten Zeitzonenabkürzungen und Informationen zur Implementierung der Sommerzeit finden Sie unter <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Zeitzonencodes</a>. </p> </p> <p> <p>Hinweis:  Um diese Einstellungen zu verwenden, müssen die Namen der Ereignisdatendateien mit einem ISO-Datum (JJJJMMTT) beginnen und jede Datei muss Daten für den 24-Stunden-Zeitraum enthalten, der an diesem Datum um 12 Uhr GMT beginnt. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.
   1. Klicken Sie in der [!DNL Server Files Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei und wählen Sie [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

In diesem Beispiel wird veranschaulicht, wie Dateien kopiert werden, wenn sowohl die Parameter &quot;Reduzieren&quot;als auch &quot;Rekursiv&quot;auf &quot;true&quot;gesetzt sind.

Angenommen, der Remote-URI ist [!DNL /RemoteRoot/] und der lokale Pfad ist [!DNL E:\LocalRoot\]. Auf dem Remotecomputer ( [!DNL Repeater]) sind die Dateien wie folgt organisiert:

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Nach Abschluss der Replikation enthält der lokale Ordner die folgenden Dateien:

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

Im lokalen Ordner werden keine Unterordner erstellt, und alle Dateien aus dem Remote-Ordnerbaum werden auf der obersten Ebene des lokalen Ordners abgelegt.

>[!NOTE]
>
>Wenn Dateien in den verschiedenen Unterordnern auf dem Remotecomputer denselben Namen haben, kann das [!DNL Replication Service] Verhalten gestoppt oder ein anderes nicht definiertes Verhalten auftreten.
