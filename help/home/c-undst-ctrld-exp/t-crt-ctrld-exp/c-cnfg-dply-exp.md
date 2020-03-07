---
description: Nachdem Sie Ihre Ziel-, Hypothese- und Experimentdetails definiert und Ihre Testinhalte erstellt haben, müssen Sie Sensor konfigurieren, um das kontrollierte Experiment bereitzustellen.
solution: Insight,Analytics
title: Konfigurieren und Bereitstellen des Experiments
topic: Data workbench
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren und Bereitstellen des Experiments{#configuring-and-deploying-the-experiment}

Nachdem Sie Ihre Ziel-, Hypothese- und Experimentdetails definiert und Ihre Testinhalte erstellt haben, müssen Sie Sensor konfigurieren, um das kontrollierte Experiment bereitzustellen.

## Konfigurieren der Experimentkonfigurationsdatei {#section-037fe7dea9c94aee9cdc354dafdb7c03}

Um das Experiment zu konfigurieren, müssen Sie die von Adobe bereitgestellte Tabelle zur Experimentkonfiguration ( [!DNL TestExperiment.xls] standardmäßig benannt) ausfüllen. Diese Datei konfiguriert [!DNL Sensor] die Durchführung des Experiments und ist die Excel-Version der Textdatei, die Sie unter [Ändern des ExpFile-Parameters](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)angegeben haben.

Diese Datei kann Informationen über mehrere Experimente enthalten, die gleichzeitig oder zu unterschiedlichen Zeitpunkten ausgeführt werden können und verschiedene Gruppen und Prozentsätze verwenden. Diese Experimente werden jedoch in keiner Weise korreliert.

Benutzer werden für jedes Experiment in einer Gruppe platziert, das in der Datei aufgeführt ist, die für die Ausführung zu diesem Zeitpunkt konfiguriert ist.

>[!NOTE]
>
>Jedes Experiment ist unabhängig von allen anderen Experimenten. Änderungen, die Sie an einem Experiment vornehmen, wirken sich nicht auf ein anderes Experiment aus. Auch wenn sich Besucher möglicherweise in mehreren Experimenten befinden, beziehen sich die Ergebnisse nicht aufeinander. Wenn Sie glauben, dass eine Korrelation zwischen den Änderungen in mehreren Experimenten besteht, müssen Sie ein neues Experiment erstellen, das diese Änderungen zusammen testet.

**So konfigurieren Sie Ihr Experiment**

Sie sollten diese Datei vor Beginn des Experiments abschließen und die Informationen nicht ändern, während das Experiment ausgeführt wird.

>[!NOTE]
>
>Ein Experiment ist sofort ungültig, wenn sich die Definition des Experiments ändert, nachdem das Experiment begonnen hat.

1. Wenn Sie über Administratorzugriff auf Ihre Web- oder Anwendungsserver verfügen, navigieren Sie zum [!DNL Sensor] Installationsordner auf einem beliebigen [!DNL Sensor] Computer im Webcluster, um auf die [!DNL TestExperiment.xls] Datei zuzugreifen. Wenn Sie keinen Administratorzugriff haben, wenden Sie sich an Ihren Adobe-Kundenbetreuer, um die [!DNL TestExperiment.xls] Datei anzufordern.

1. Öffnen Sie die [!DNL TestExperiment.xls] Datei (Sie können diese Datei bei Bedarf umbenennen) und füllen Sie die folgenden Felder aus:

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Experiment </td> 
   <td colname="col2"> <p>Ein beschreibender Name für das Experiment. Jeder Experimentname muss eindeutig sein und darf keine Leerzeichen enthalten. </p> <p>Experimentnamen werden verwendet, wenn die Ergebnisse von Experimenten in <span class="keyword"> Insight angezeigt werden </span>. Die Namen werden in der ersten Hälfte der Elementnamen in der Dimension für kontrolliertes Experiment angezeigt. Die zweite Hälfte des Elementnamens ist der Gruppenname aus dem Feld Gruppe in dieser Datei. Jede Gruppe wird im folgenden Format mit dem Experimentnamen gefolgt vom Gruppennamen benannt: </p> <p><i>ExperimentName.Gruppenname</i> </p> <p>Beispiel: <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Start </td> 
   <td colname="col2"> <p>Datum und Uhrzeit des Beginns des Experiments. Wenn Sie keine Werte eingeben, beginnt das Experiment unmittelbar nach der Bereitstellung der Datei. </p> <p>Format: MM/TT/JJJJ H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">Wenn Sie die Start- und Stoppzeiten leer lassen, läuft das Experiment unbegrenzt. </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">Sie können Start- und Stoppzeiten frühzeitig festlegen. Daher können Sie alle Experimente für das nächste Jahr auf Wunsch gleichzeitig konfigurieren. </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">Start- und Stoppzeiten basieren auf der Systemzeit des Webservers. Ändert sich diese Uhr aus irgendeinem Grund, kann Ihr Experiment unerwartet starten oder anhalten. </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">Wenn Sie ein Experiment als Konfigurationsdateieintrag hinzufügen möchten, das Experiment jedoch in naher Zukunft nicht ausführen möchten, können Sie die Experimentinformationen mit dem Nummernzeichen "#"kommentieren oder die Start- und Stoppzeiten in der Vergangenheit definieren. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>Datum und Uhrzeit des Endes des Experiments. Wenn das Enddatum und die Uhrzeit eintreten, <span class="wintitle"> beendet Sensor </span> das Senden der als Testgruppe identifizierten Cookie-Werte an die Test-URIs und sendet alle Cookies an die Kontrollgruppe-URIs. </p> <p>Format: MM/TT/JJJJ H:MM </p> <p>Siehe Hinweise zum <span class="wintitle"> Start- </span> Feld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gruppe </td> 
   <td colname="col2"> <p>Ein beschreibender Name für jede Besuchergruppe im Experiment. Gruppennamen dürfen keine Leerzeichen enthalten. </p> <p>Gruppennamen werden verwendet, wenn die Ergebnisse von Experimenten in <span class="keyword"> Insight angezeigt werden </span>. Weitere Informationen finden Sie in der Beschreibung des Experimentfelds. </p> <p>Eine Kontrollgruppe kann implizit oder explizit definiert werden, basierend auf dem Wert, der im Feld Prozentsatz eingegeben wird. </p> <p> <p>Hinweis:  Um die Anzahl der Besucher zu erfüllen, die während des definierten Zeitraums für die statistische Gültigkeit des Experiments erforderlich sind, müssen Sie möglicherweise das Konfidenzniveau senken oder den Zeitraum erhöhen. Wenn Ihr Zeitraum z. B. fünf Tage beträgt, Ihr Konfidenzniveau bei 98 % liegt und Ihre Anzahl an Besuchern die für diesen Zeitraum erwartete Anzahl überschreitet, müssen Sie entweder den Zeitraum erhöhen oder das Konfidenzniveau verringern, bis die Anzahl der erwarteten Besucher die für die Durchführung eines statistisch gültigen Experiments erforderliche Anzahl übersteigt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prozentsatz </td> 
   <td colname="col2"> <p>Der Prozentsatz der Website-Besucher, die in jede definierte Gruppe einbezogen werden sollen. Diese Werte können entweder als Prozentwerte oder als Dezimalwerte ausgedrückt werden. Darüber hinaus müssen beide Werte größer oder kleiner als 1 sein. </p> <p>Beispiel: </p> <p>33,3 % und 66,7 % </p> <p>.99 und .01 </p> <p>Wenn die Summe für alle Gruppen kleiner als 100 ist, wird als nicht definierter Überschuss standardmäßig eine Kontrollgruppe verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ursprüngliche URL </td> 
   <td colname="col2"> <p>Der URI des zu entfernenden Inhalts, gefolgt von $. Bei diesem Wert wird zwischen Groß- und Kleinschreibung unterschieden. </p> <p>Format: index.asp$ </p> <p>Ursprüngliche URIs können mit einem Dollarzeichen ($) am Ende des URI angegeben werden, um anzugeben, dass eine exakte Übereinstimmung mit dem Dateinamen erforderlich ist. Der Ausdruck <span class="filepath"> /product/product_view.asp$ </span> stimmt beispielsweise nur mit der exakten Seite überein, während <span class="filepath"> /product mit jeder Seite im Ordner </span> /product <span class="filepath"> </span> übereinstimmt und verwendet werden könnte, um die gesamte Unterstruktur zu überordnen. Ursprüngliche URL-Einträge, die das $-Zeichen am Ende des Dateinamens nicht angeben, werden vom Experiment ignoriert, es sei denn, der Parameter ExpPartialMatch wurde auf "on"gesetzt. Weitere Informationen zu diesem Parameter finden Sie unter <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> Modifizieren des ExpPartialMatch-Parameters (Optional) </a>. </p> <p>Die Funktion für kontrolliertes Experiment ignoriert alle an den URI-Stamm angehängten Abfragezeichenfolgen. Die Seite </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 </span> ist kein gültiger URI, aber die Seite <span class="filepath"> /product/product_view.asp </span> ist ein gültiger URI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entfernte URL </td> 
   <td colname="col2"> <p>Der URI des alternativen Inhalts. </p> <p>Format: index2.asp </p> <p>Siehe Hinweise zum Feld "Ursprüngliche URL". </p> </td> 
  </tr> 
 </tbody> 
</table>

Die folgende Tabelle ist ein Beispiel für eine abgeschlossene [!DNL TextExperiment.xls] Tabelle:

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>Ändern Sie nicht die Spaltenpositionen im Arbeitsblatt.

Dieses Beispiel zeigt an, dass das Experiment &quot;New_Homepage&quot;am 1. Juni 2006 beginnt, am 30. Juni 2006 endet und eine Kontrollgruppe mit 50 % der Besucher sowie eine Testgruppe mit 50 % der Besucher enthält, die unterschiedliche Inhalte für einen URI sehen.

>[!NOTE]
>
>Obwohl die obige Beispieldatei eine explizite Kontrollgruppe definiert hat, ist es nicht notwendig, eine Kontrollgruppe explizit zu definieren — Das Experiment erstellt automatisch die Kontrollgruppe. Wenn die Summe der Prozentsätze für alle Gruppen in einem Experiment weniger als 100 % beträgt, wird eine implizite Kontrollgruppe Benutzern zugewiesen, die nicht in eine der expliziten Gruppen fallen.

1. Um Kommentare einzufügen, um weitere Informationen zu bestimmten Experimenten bereitzustellen, beginnen Sie die Zelle mit einem Nummernzeichen (#) und folgen Sie Ihren Kommentaren. Kommentare können an einer beliebigen Stelle in die Datei eingefügt werden.
1. Nachdem Sie die Variablen im Arbeitsblatt für die Experimentkonfiguration abgeschlossen haben, speichern Sie die Änderungen und speichern Sie die Datei dann im tabulatorgetrennten Textformat ( [!DNL *.txt]) unter dem Namen, den Sie im Parameter ExpFile in der [!DNL Sensor] Konfigurationsdatei angegeben haben. Siehe [Ändern des ExpFile-Parameters](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   Im Folgenden finden Sie ein Beispiel für eine Textdatei mit einer Experimentkonfiguration:

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >Bearbeiten Sie aufgrund der in dieser Datei erforderlichen Registerkarten die Text-Datei für die Experimentkonfiguration nicht manuell. Wenn Sie Änderungen an der Datei vornehmen müssen, nehmen Sie die Änderungen in der Excel-Experimentkonfigurationsdatei vor und speichern Sie die Datei erneut als tabulatorbegrenzte Textdatei.

Wenn Sie Start- und Stoppzeiten definiert haben, besteht kein Grund, ein Experiment jemals aus der Experimentkonfigurationsdatei zu löschen. Die Auflistung aller Experimente in der Experimentkonfigurationsdatei ist in der Tat eine gute Methode, um zu protokollieren, wie Sie die einzelnen Experimente definiert haben.

## Bereitstellen der Konfigurationsdatei und Testinhalte {#section-34ff29649f584b93bc6129b75084b37c}

Sie müssen die Experimentkonfigurationsdatei auf jedem Computer im Webcluster bereitstellen, auf dem ein [!DNL Sensor] und die an dem Experiment beteiligten Seiten bereitgestellt werden. Dazu verwenden Sie entweder ein manuelles Verfahren oder Ihr vorhandenes Content-Management-System.

**So stellen Sie Testinhalte bereit**

* Verwenden Sie auf jeder Anwendung oder jedem Webserver, auf [!DNL Sensor] der Seiten bereitgestellt werden, die am Experiment beteiligt sind, Ihren vorhandenen Veröffentlichungsprozess, um den Testinhalt am entsprechenden Speicherort bereitzustellen.

   Wenn Sie z. B. die Testgruppenseite [!DNL index2.asp] im Testordner Ihrer Website veröffentlichen möchten ( [!DNL mysite.com]), veröffentlichen Sie die Datei in [!DNL www.mysite.com/test].

   >[!NOTE]
   >
   >Verknüpfen Sie keine Ihrer Testdateien direkt von einer Seite Ihrer Website. Dadurch werden Ihre Testergebnisse und Ihre Indexwerte ungültig.

**So stellen Sie Ihr Experiment bereit**

* Platzieren Sie auf jeder Anwendung oder jedem Webserver, [!DNL Sensor] die bzw. der eine Seite bereitstellt, die am Experiment beteiligt ist, die Testkonfigurationstextdatei in dem Ordner, den Sie im Parameter ExpFile in der [!DNL Sensor] Konfigurationsdatei angegeben haben. Siehe [Ändern des ExpFile-Parameters](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

[!DNL Sensor] wählt nach dem Zufallsprinzip Website-Besucher für jede Gruppe basierend auf den Prozentwerten aus, die Sie in der Datei definiert haben, und stellt ihnen den Inhalt der Test- oder Kontrollgruppe entsprechend bereit.
