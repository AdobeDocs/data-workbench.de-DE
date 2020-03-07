---
description: Sie können das Erscheinungsbild eines Menüs anpassen, indem Sie die Datei order.txt bearbeiten, die mit diesem Menü verknüpft ist.
solution: Analytics
title: Menüs mithilfe der Dateien order.txt anpassen
topic: Data workbench
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Menüs mithilfe der Dateien order.txt anpassen{#customize-a-menu-using-order-txt-files}

Sie können das Erscheinungsbild eines Menüs anpassen, indem Sie die Datei order.txt bearbeiten, die mit diesem Menü verknüpft ist.

Die Schritte in diesem Abschnitt gelten für alle Arten von Menüs.

**So bearbeiten Sie die Datei &quot;order.txt&quot;, um ein Menü anzupassen**

1. Klicken Sie in der Spalte [!DNL Profile Manager]des *Profilnamens* mit der rechten Maustaste auf das Häkchen für die [!DNL order.txt] Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die [!DNL order.txt] Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die [!DNL order.txt] Datei wird angezeigt.

   ![Schritt-Info](assets/cfg_ordertxt.png)

1. (Optional) Fügen Sie die Einstellung &quot; [Einschließen] &quot;oder &quot; [Ausschließen] &quot;oben in der Datei hinzu oder ändern Sie sie. Diese Einstellung steuert, ob Elemente, die nicht in der [!DNL order.txt] Datei aufgeführt, sondern im Menü vorhanden [!DNL Profile Manager] sind, im Menü aufgeführt werden. Zu den Optionen gehören:

   * **[Inklusiv]:**Dies ist die Standardeinstellung. Diese Einstellung führt dazu, dass Menüelemente, die nicht in der[!DNL order.txt]Datei angegeben sind, am unteren Rand des Menüs in alphabetischer Reihenfolge aufgeführt werden. Beispiel: Wenn das[!DNL Profile Manager]Profil ein Profilelement zusätzlich zu den im[!DNL order.txt]oben aufgeführten enthält, würde das Profil unter &quot;Daten&quot;angezeigt.

   * **[Exklusiv]:**Diese Einstellung führt dazu, dass Menüelemente, die nicht in der[!DNL order.txt]Datei angegeben sind, aus dem Menü ausgeschlossen werden. Wenn das Profil zum Beispiel ein[!DNL Profile Manager]Profilelement zusätzlich zu den im[!DNL order.txt]oben aufgeführten enthält, wird das Profil an keiner Stelle im Menü angezeigt.

   * **blank:** Wenn oben in der Datei weder &quot; [Einschließen] &quot;noch &quot; [Ausschließen] &quot;angezeigt wird, zeigt Data Workbench die Menüelemente so an, als ob die Einstellung &quot; [Einbezogen]&quot;wäre.

1. Führen Sie einen oder mehrere der folgenden Schritte aus:

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Um diese Aufgabe auszuführen... </th> 
    <th colname="col2" class="entry"> Gehen Sie folgendermaßen vor... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Menüelemente neu anordnen </p> </td> 
    <td colname="col2"> <p>Geben Sie die Elementnamen in der Reihenfolge ein, in der sie in Data Workbench angezeigt werden sollen. </p> <p>Solange beispielsweise jeder Name des Menüelements mit dem entsprechenden Datei- oder Ordnernamen übereinstimmt, würde Folgendes dazu führen<b> , dass zuerst Tabelle</b> hinzufügen angezeigt wird, dann Visualisierung <b></b>hinzufügen, Legende <b></b>hinzufügen und Notiz <b>hinzufügen</b> zuletzt angezeigt wird. </p> <p><b>Tabelle hinzufügen </b> </p> <p><b>Visualisierung hinzufügen </b> </p> <p><b>Legende hinzufügen </b> </p> <p><b>Notiz hinzufügen </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Menüelement umbenennen </p> </td> 
    <td colname="col2"> <p>Benennen Sie die entsprechende Datei oder den Ordner im <span class="wintitle"> Profile Manager</span>um und ändern Sie dann den Namen des Elements in der Datei " <span class="filepath"> order.txt</span> ". </p> <p>Um beispielsweise Anmerkung zu neuer Anmerkung hinzufügen umzubenennen, benennen Sie den Ordner Anmerkung hinzufügen im <span class="wintitle"> Profil-Manager</span> in Neue Anmerkung um und ändern Sie dann den Namen des Elements Anmerkung hinzufügen in der Datei " <span class="filepath"> order.txt</span> "in Neue Anmerkung. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Menüelemente ausblenden </p> </td> 
    <td colname="col2"> <p>Um das Menüelement auszublenden, das Element selbst jedoch nicht zu löschen, geben Sie ein Minuszeichen (-) am Anfang des Namens ein. </p> <p>Beispielsweise werden die folgenden Ergebnisse in <span class="wintitle"> Anmerkung</span> hinzufügen nicht im Menü angezeigt. </p> <p>Legende hinzufügen </p> <p>-Anmerkung hinzufügen </p> <p>Um das ausgeblendete Menüelement erneut anzuzeigen, entfernen Sie einfach das Minuszeichen (-) oder verwenden Sie den Parameter "Rückgängig: Alle"in der Datei " <span class="filepath"> Insight.cfg</span> ", siehe <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight-Konfigurationsparameter</a>. </p> <p>Sie können Menüelemente auch wie folgt ausblenden: 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>Der Parameter "Anzeigen"in einer <span class="filepath"> .filter</span>-, <span class="filepath"> .metric</span>- oder <span class="filepath"> .dim</span> -Datei blendet Filter, abgeleitete Metriken und Dimensionen sowie erweiterte Dimensionen aus ihren jeweiligen Menüs aus. Wenn Sie diese Option verwenden, wird das Element nicht im Menü aufgeführt, aber es befindet sich noch im Profil und kann verwendet werden. </p> <p>Um mit diesem Parameter Filter und abgeleitete Metriken und Dimensionen auszublenden, fügen Sie am Ende der <span class="filepath"> Datei .metric</span>, <span class="filepath"> .dim</span>oder <span class="filepath"> .filter</span> die folgende Zeile hinzu: </p> <p><span class="filepath"> show = bool: false</span> </p> <p>Anweisungen zum Ausblenden erweiterter Dimensionen mithilfe dieses Parameters finden Sie in Kapitel 10 des Handbuchs zur <i>Datenkonfiguration</i> . </p> <p>Sie können Elemente, die mit dieser Methode ausgeblendet werden, vorübergehend wieder einblenden, indem Sie den Parameter "Alle einblenden"in der Datei " <span class="filepath"> Insight.cfg</span> "festlegen. Weitere Informationen zu diesem Parameter finden Sie unter <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight-Konfigurationsparameter</a>. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">Der Parameter "Ausgeblendet"in der Datei " <span class="filepath"> Transformation.cfg</span> "oder in einem Datensatz "Include"blendet erweiterte Dimensionen im Menü "Dimension"aus. Wenn Sie diese Option verwenden, wird das Element nicht im Menü aufgeführt, aber es befindet sich noch im Profil und kann verwendet werden. <p> <p>Hinweis:  Wenn Sie erweiterte Dimensionen mit dieser Methode ausblenden, müssen Sie das Dataset neu transformieren, damit die Dimensionen ausgeblendet werden. </p> </p> <p>Sie können Elemente, die mit dieser Methode ausgeblendet werden, vorübergehend wieder einblenden, indem Sie den Parameter "Alle einblenden"in der Datei " <span class="filepath"> Insight.cfg</span> "festlegen. Weitere Informationen zu diesem Parameter finden Sie unter <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight-Konfigurationsparameter</a>. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Nullbyte-Dateien verbergen alle Elementtypen in jedem Menü. Bei Verwendung dieser Option wird durch eine leere (Null-Byte-)Datei das Vorhandensein einer Datei mit demselben Namen, die Daten enthält, ausgeblendet. Data Workbench behandelt Nullbyte-Dateien so, als wären sie nicht vorhanden. Weitere Informationen finden Sie unter <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ausblenden von Dateien mit leeren (Null-Byte-)Dateien</a>. </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Löschen eines Menüelements </p> </td> 
    <td colname="col2"> <p>Wenn diese Datei so eingestellt ist, dass sie die Option [Ausschließen] verwendet, können Sie das Menüelement einfach aus dieser Datei löschen. Das Element selbst befindet sich weiterhin im Profil, wird jedoch nicht im Menü aufgeführt. </p> <p>Wenn diese Datei so eingestellt ist, dass sie die Option "[Einschließen]"verwendet, müssen Sie den Namen des Menüelements aus dieser Datei entfernen und entweder die entsprechende Datei löschen oder Null-Byte verwenden, um das Element aus dem Menü zu entfernen. </p> <p>Informationen zum Löschen von Dateien finden Sie unter Löschen von Dateien aus Ihrem Arbeitsprofil <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"></a>. Informationen zu Nullbyte-Dateien finden Sie unter <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ausblenden von Dateien mit leeren (Null-Byte-)Dateien</a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Hinzufügen einer Gruppenüberschrift </p> </td> 
    <td colname="col2"> <p>Geben Sie drei Bindestriche vor und nach dem Überschriftentext ein, der angezeigt werden soll. </p> <p>Beispielsweise würde die folgende Tabelle zu einer Kopfzeile der Gruppe verwalten für eine Reihe verwandter Menüelemente führen. </p> <p>---Verwalten--- </p> <p>Profil </p> <p>Datensatz </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Hinzufügen einer Zeile zum Trennen von Abschnitten eines Menüs </p> </td> 
    <td colname="col2"> <p>Geben Sie drei Bindestriche ein, in denen eine Linie angezeigt werden soll. </p> <p>Die folgenden Ergebnisse ergeben beispielsweise eine Zeile zwischen "Anmerkung hinzufügen"und "Benutzerdefiniert hinzufügen". </p> <p>Anmerkung hinzufügen </p> <p>--- </p> <p>Benutzerdefiniert hinzufügen </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Speichern und schließen Sie die Datei.
1. (Optional) Um die Änderungen allen Benutzern des Arbeitsprofils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für die [!DNL order.txt] Datei in der [!DNL User] Spalte und klicken Sie auf **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
