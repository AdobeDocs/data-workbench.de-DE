---
description: Sie müssen die Insight Server-Zielgruppen konfigurieren, um Daten aus dem Repeater abzurufen, in dem die ursprünglichen Ereignisdaten gespeichert sind.
title: Konfigurieren des Replikations-Services
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# Konfigurieren des Replikations-Services{#configuring-the-replication-service}

{{eol}}

Sie müssen die Insight Server-Zielgruppen konfigurieren, um Daten aus dem Repeater abzurufen, in dem die ursprünglichen Ereignisdaten gespeichert sind.

So konfigurieren Sie den Abruf von Daten aus einer [!DNL Repeater] Zielgruppe [!DNL Insight Server], müssen Sie die [!DNL Replicate.cfg] -Datei, die im [!DNL Components] Ordner auf dem Zielordner [!DNL Insight Server(s)] wie im folgenden Verfahren beschrieben:

**So konfigurieren Sie die [!DNL Replication Service] auf dem Zielcomputer**

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol der Zielgruppe [!DNL Insight Server] Sie möchten konfigurieren und klicken Sie auf **[!UICONTROL Server Files]**.
1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Replicate.cfg] -Datei befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* Spalte für [!DNL Replicate.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Replicate.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Die [!DNL Replicate.cfg] geöffnet.
1. Im [!DNL Replicate.cfg] Fenster, klicken Sie auf **[!UICONTROL Replicate.cfg]**, dann **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Bearbeiten Sie die Parameter mithilfe des folgenden Beispiels und der folgenden Tabelle als Handbücher:

   ![Schritt-Info](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Für diesen Parameter ... </th> 
      <th colname="col2" class="entry"> Legen Sie... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Verzeichnisse </td> 
      <td colname="col2"> <p>Die Verzeichnisse im <span class="wintitle"> Repeater</span> die in die Zielgruppe kopiert (repliziert) werden sollen <span class="keyword"> Insight Server</span>. Die <span class="wintitle"> Replikationsdienst</span> ermöglicht die Replikation mehrerer Verzeichnisse aus einem <span class="wintitle"> Repeater</span>. </p> <p>Um einen neuen Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Verzeichnisse</span> und klicken Sie auf <span class="uicontrol"> Neu hinzufügen</span> &gt; <span class="uicontrol"> Verzeichnis</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reduzieren von Pfaden </td> 
      <td colname="col2"> <p>True oder false. Die durch die Einstellung dieses Parameters definierte Aktion hängt von der Einstellung des Parameters Rekursiv in dieser Datei ab: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Wenn "Rekursiv"falsch ist, hat "Reduzieren von Pfaden"keine Auswirkungen. Nur die Dateien auf der obersten Ebene des Ordners, der durch den Parameter "Remote URI"angegeben wird, werden repliziert. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Wenn "Rekursiv"auf "true"gesetzt ist und "Flatten Paths"auf "false"gesetzt ist, wird die Verzeichnisstruktur der Remote-Verbindung (<span class="wintitle"> Repeater</span>) genau im lokalen Pfad auf der Zielseite dupliziert wird <span class="keyword"> Insight Server</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Wenn sowohl der rekursive als auch der reduzierte Pfad "true"sind, werden keine Unterverzeichnisse im lokalen Pfad erstellt. Stattdessen werden alle Dateien aus der Remote-Ordnerstruktur auf der obersten Ebene des lokalen Ordners abgelegt. </li>
      </ul></p> <p> <p>Hinweis: Wenn sowohl reduzierte Pfade als auch rekursive Pfade wahr sind und Dateien in den verschiedenen Unterverzeichnissen auf dem Remotecomputer denselben Namen haben, wird der <span class="wintitle"> Replikationsdienst</span> kann stoppen oder ein anderes undefiniertes Verhalten auftreten. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Lokaler Pfad </td> 
      <td colname="col2">Der Speicherort für die Dateien, von denen abgerufen wird <span class="wintitle"> Repeater</span>. Der Pfad ist relativ zum <span class="keyword"> Insight Server</span> Installationsverzeichnis. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rekursiv </td> 
      <td colname="col2"> True oder false. Wenn der Wert "false"ist, werden nur die Dateien auf der obersten Ebene des Ordners repliziert, der durch den Parameter "Remote URI"angegeben wird. Siehe Reduzieren von Pfaden in dieser Tabelle. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Remote URI </td> 
      <td colname="col2">Der URI, einschließlich einer Dateimaske, um auf die <span class="wintitle"> Repeater’s</span> Dateispeicher. Die <span class="filepath"> Communications.cfg</span> -Datei auf <span class="wintitle"> Repeater</span> sollte so konfiguriert werden, dass auf die Ereignisdaten über diesen URI zugegriffen werden kann. Siehe <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Überwachen des Festplattenspeichers für Ereignisdaten</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Server </td> 
      <td colname="col2">Parameter für <span class="wintitle"> Repeater</span> von dem aus die Zielgruppe <span class="keyword"> Insight Server</span> ruft Ereignisdatendateien ab. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Name </td> 
      <td colname="col2">Optional. Der Name, der die <span class="wintitle"> Repeater</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Allgemeiner SSL-Server-Name </td> 
      <td colname="col2">Nur erforderlich, wenn SSL verwenden auf "true"gesetzt ist. Allgemeiner Name der <span class="wintitle"> Repeater</span> auf dem die Ereignisdaten gespeichert werden. Dieser Name muss mit dem allgemeinen Namen übereinstimmen, der im Kommunikationszertifikat für den Computer aufgeführt ist. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Adresse </td> 
      <td colname="col2">Hostname oder numerische IP-Adresse des <span class="wintitle"> Repeater</span> auf dem die Ereignisdaten gespeichert werden. Der allgemeine Name des Servers ist kein gültiger Eintrag. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> Für die Datenübertragung verwendeter Anschluss. Der Standardanschluss ist 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL-Client-Zertifikat </td> 
      <td colname="col2">Nur erforderlich, wenn SSL verwenden auf "true"gesetzt ist. Name des Lizenzzertifikats, mit dem die Verbindung zum <span class="wintitle"> Repeater</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL verwenden </td> 
      <td colname="col2"> <p>Bestimmt, ob SSL für die Datenübertragung verwendet wird. Die Optionen sind "true"oder "false", der Standardwert "false". </p> <p> <p>Hinweis: Die Verwendung von SSL wird nicht empfohlen, da dies die Leistung beeinträchtigen kann. Beachten Sie, dass SSL nur erforderlich ist, wenn das Netzwerk die <span class="wintitle"> Repeater</span> auf den Zielgeräten nicht sicher ist. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Endzeit, Startzeit </td> 
      <td colname="col2"> <p>(Optional) Beschränkt den Satz von Ereignisdatendateien, die in die Zielgruppe kopiert werden <span class="keyword"> Insight Server</span> zu denen gehören, die Daten im von Startzeit und Endzeit definierten Bereich enthalten. Wenn die Startzeit festgelegt ist, werden Ereignisdatendateien, in denen alle Protokolleinträge aus einer früheren als der angegebenen Startzeit stammen, nicht kopiert. Wenn die Endzeit festgelegt ist, werden Ereignisdatendateien, in die alle Protokolleinträge aus der angegebenen oder späteren Zeit nicht kopiert werden. Wenn nur ein Teil der Daten in einer Datei im angegebenen Bereich liegt, wird die gesamte Datei auf den Zielcomputer kopiert. </p> <p>Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1. Januar 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1. Januar 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Hinweis: Sie müssen eine Zeitzone angeben. Wenn nicht angegeben, wird in der Zeitzone nicht standardmäßig Systemzeit verwendet. Wenn Sie die Sommerzeit oder eine ähnliche Uhrzeitverschiebungspolitik implementieren möchten, müssen Sie die <span class="filepath"> .dst</span> -Datei mit den entsprechenden Regeln im Ordner "Base\Dataset\Timezone"auf der <span class="keyword"> Insight Server</span> Maschine. Eine Liste der unterstützten Zeitzonen-Abkürzungen und Informationen zur Implementierung der Sommerzeit finden Sie unter <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Zeitzonencodes</a>. </p> </p> <p> <p>Hinweis: Um diese Einstellungen verwenden zu können, müssen die Namen der Ereignisdatendateien mit einem ISO-Datum (JJJMMTT) beginnen und jede Datei muss Daten für den 24-Stunden-Zeitraum enthalten, der an diesem Datum um 12 Uhr GMT beginnt. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
   1. Im [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Dieses Beispiel zeigt, wie Dateien kopiert werden, wenn sowohl die Parameter &quot;Reduzierte Pfade&quot;als auch &quot;Rekursiv&quot;auf &quot;true&quot;gesetzt sind.

Angenommen, der Remote-URI ist [!DNL /RemoteRoot/] und der lokale Pfad lautet [!DNL E:\LocalRoot\]. Auf dem Remote-Standort ( [!DNL Repeater]), werden die Dateien wie folgt organisiert:

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Wenn die Replikation abgeschlossen ist, enthält das lokale Verzeichnis die folgenden Dateien:

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

Im lokalen Verzeichnis werden keine Unterverzeichnisse erstellt und alle Dateien aus der Remote-Ordnerstruktur werden auf der obersten Ebene des lokalen Ordners abgelegt.

>[!NOTE]
>
>Wenn Dateien in den verschiedenen Unterverzeichnissen auf dem Remotecomputer dieselben Namen haben, wird die [!DNL Replication Service] kann stoppen oder ein anderes undefiniertes Verhalten auftreten.
