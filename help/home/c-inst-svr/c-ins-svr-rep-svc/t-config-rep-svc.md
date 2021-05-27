---
description: Sie müssen die Insight Server-Zielgruppen konfigurieren, um Daten aus dem Repeater abzurufen, in dem die ursprünglichen Ereignisdaten gespeichert sind.
title: Konfigurieren des Replikations-Services
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 2%

---

# Konfigurieren des Replikations-Services{#configuring-the-replication-service}

Sie müssen die Insight Server-Zielgruppen konfigurieren, um Daten aus dem Repeater abzurufen, in dem die ursprünglichen Ereignisdaten gespeichert sind.

Um den Abruf von Daten von einem [!DNL Repeater] zu einem Ziel [!DNL Insight Server] zu konfigurieren, müssen Sie die [!DNL Replicate.cfg]-Datei bearbeiten, die im Ordner [!DNL Components] auf dem Ziel [!DNL Insight Server(s)] bereitgestellt wird, wie im folgenden Verfahren beschrieben:

**So konfigurieren Sie die  [!DNL Replication Service] auf dem Zielcomputer**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des Ziels [!DNL Insight Server], das Sie konfigurieren möchten, und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL Replicate.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Replicate.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Replicate.cfg] wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Das Fenster [!DNL Replicate.cfg] wird geöffnet.
1. Klicken Sie im Fenster [!DNL Replicate.cfg] auf **[!UICONTROL Replicate.cfg]** und dann auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.
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
      <td colname="col2"> <p>Die Ordner des <span class="wintitle"> Repeater</span>, die in das Ziel <span class="keyword"> Insight Server</span> kopiert (repliziert) werden sollen. Der <span class="wintitle"> Replikationsdienst</span> ermöglicht die Replikation mehrerer Ordner von einem einzelnen <span class="wintitle"> Repeater</span>. </p> <p>Um einen neuen Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Verzeichnisse</span> und klicken Sie auf <span class="uicontrol"> Hinzufügen neuer</span> &gt; <span class="uicontrol"> Verzeichnis</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reduzieren von Pfaden </td> 
      <td colname="col2"> <p>Wahr oder falsch. Die durch die Einstellung dieses Parameters definierte Aktion hängt von der Einstellung des Parameters Rekursiv in dieser Datei ab: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Wenn "Rekursiv"falsch ist, hat "Reduzieren von Pfaden"keine Auswirkungen. Nur die Dateien auf der obersten Ebene des Ordners, der durch den Parameter "Remote URI"angegeben wird, werden repliziert. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Wenn "Rekursiv"auf "true"gesetzt ist und "Flatten Paths"auf "false"gesetzt ist, wird die Verzeichnisstruktur des Remote-Ordners (<span class="wintitle"> Repeater</span>) exakt im lokalen Pfad des Ziels <span class="keyword"> "Insight Server</span>"dupliziert. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Wenn sowohl der rekursive als auch der reduzierte Pfad "true"sind, werden keine Unterverzeichnisse im lokalen Pfad erstellt. Stattdessen werden alle Dateien aus der Remote-Ordnerstruktur auf der obersten Ebene des lokalen Ordners abgelegt. </li>
      </ul></p> <p> <p>Hinweis: Wenn sowohl reduzierte Pfade als auch rekursive Pfade wahr sind und Dateien in den verschiedenen Unterverzeichnissen auf dem Remotecomputer denselben Namen haben, kann der <span class="wintitle"> Replikationsdienst</span> angehalten werden oder es kann zu einem anderen nicht definierten Verhalten kommen. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Lokaler Pfad </td> 
      <td colname="col2">Der Speicherort für die Dateien, die von <span class="wintitle"> Repeater</span> abgerufen werden. Der Pfad ist relativ zum Installationsordner von <span class="keyword"> Insight Server</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rekursiv </td> 
      <td colname="col2"> Wahr oder falsch. Wenn der Wert "false"ist, werden nur die Dateien auf der obersten Ebene des Ordners repliziert, der durch den Parameter "Remote URI"angegeben wird. Siehe Reduzieren von Pfaden in dieser Tabelle. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Remote URI </td> 
      <td colname="col2">Der URI, einschließlich einer Dateimaske, für den Zugriff auf den Dateispeicher <span class="wintitle"> "Repeater"</span>. Die Datei <span class="filepath"> Communications.cfg</span> im Ordner <span class="wintitle"> Repeater</span> sollte so konfiguriert werden, dass mit diesem URI auf die Ereignisdaten zugegriffen werden kann. Siehe <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Überwachen des Festplattenspeichers für Ereignisdaten</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Server </td> 
      <td colname="col2">Parameter für den <span class="wintitle"> Repeater</span>, aus dem das Ziel <span class="keyword"> Insight Server</span> Ereignisdatendateien abruft. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Name </td> 
      <td colname="col2">Optional. Der Name, der den <span class="wintitle"> Repeater</span> angibt. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Allgemeiner SSL-Server-Name </td> 
      <td colname="col2">Nur erforderlich, wenn SSL verwenden auf "true"gesetzt ist. Allgemeiner Name des <span class="wintitle"> Repeater</span>, in dem die Ereignisdaten gespeichert werden. Dieser Name muss mit dem allgemeinen Namen übereinstimmen, der im Kommunikationszertifikat für den Computer aufgeführt ist. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Adresse </td> 
      <td colname="col2">Hostname oder numerische IP-Adresse des <span class="wintitle"> Repeater</span>, in dem die Ereignisdaten gespeichert werden. Der allgemeine Name des Servers ist kein gültiger Eintrag. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Anschluss </td> 
      <td colname="col2"> Für die Datenübertragung verwendeter Anschluss. Der Standardanschluss ist 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL-Client-Zertifikat </td> 
      <td colname="col2">Nur erforderlich, wenn SSL verwenden auf "true"gesetzt ist. Name des Lizenzzertifikats, das für die Verbindung mit <span class="wintitle"> Repeater</span> verwendet wird. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL verwenden </td> 
      <td colname="col2"> <p>Bestimmt, ob SSL für die Datenübertragung verwendet wird. Die Optionen sind "true"oder "false", der Standardwert "false". </p> <p> <p>Hinweis: Die Verwendung von SSL wird nicht empfohlen, da dies die Leistung beeinträchtigen kann. Beachten Sie, dass SSL nur erforderlich ist, wenn das Netzwerk, das den <span class="wintitle"> Repeater</span> mit den Zielgeräten verbindet, unsicher ist. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Endzeit, Startzeit </td> 
      <td colname="col2"> <p>(Optional) Schränkt den Satz von Ereignisdatendateien, die in das Ziel <span class="keyword"> Insight Server</span> kopiert werden, auf jene ein, die Daten im von der Startzeit und Endzeit definierten Bereich enthalten. Wenn die Startzeit festgelegt ist, werden Ereignisdatendateien, in denen alle Protokolleinträge aus einer früheren als der angegebenen Startzeit stammen, nicht kopiert. Wenn die Endzeit festgelegt ist, werden Ereignisdatendateien, in die alle Protokolleinträge aus der angegebenen oder späteren Zeit nicht kopiert werden. Wenn nur ein Teil der Daten in einer Datei im angegebenen Bereich liegt, wird die gesamte Datei auf den Zielcomputer kopiert. </p> <p>Adobe empfiehlt die Verwendung eines der folgenden Zeitformate: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1. Januar 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1. Januar 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Hinweis: Sie müssen eine Zeitzone angeben. Wenn nicht angegeben, wird in der Zeitzone nicht standardmäßig Systemzeit verwendet. Wenn Sie die Sommerzeit oder eine ähnliche Richtlinie zum Wechsel der Uhr implementieren möchten, müssen Sie die Datei <span class="filepath"> .dst</span> mit den entsprechenden Regeln auf dem Computer Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> speichern. Eine Liste der unterstützten Zeitzonenabkürzungen und Informationen zur Implementierung der Sommerzeit finden Sie unter <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Zeitzonencodes</a>. </p> </p> <p> <p>Hinweis:  Um diese Einstellungen verwenden zu können, müssen die Namen der Ereignisdatendateien mit einem ISO-Datum (JJJMMTT) beginnen und jede Datei muss Daten für den 24-Stunden-Zeitraum enthalten, der an diesem Datum um 12 Uhr GMT beginnt. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.
   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Dieses Beispiel zeigt, wie Dateien kopiert werden, wenn sowohl die Parameter &quot;Reduzierte Pfade&quot;als auch &quot;Rekursiv&quot;auf &quot;true&quot;gesetzt sind.

Angenommen, der Remote-URI ist [!DNL /RemoteRoot/] und der lokale Pfad ist [!DNL E:\LocalRoot\]. Auf dem Remote-Computer ( [!DNL Repeater]) sind die Dateien wie folgt organisiert:

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
>Wenn Dateien in den verschiedenen Unterverzeichnissen auf dem Remotecomputer denselben Namen haben, kann [!DNL Replication Service] angehalten werden oder es kann zu einem anderen nicht definierten Verhalten kommen.
