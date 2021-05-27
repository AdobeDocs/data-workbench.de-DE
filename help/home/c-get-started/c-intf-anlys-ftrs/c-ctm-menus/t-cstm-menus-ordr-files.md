---
description: Sie können das Erscheinungsbild jedes Menüs anpassen, indem Sie die mit diesem Menü verknüpfte Datei order.txt bearbeiten.
title: Anpassen von Menüs anhand von „order.txt“-Dateien
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
exl-id: 3803a56f-19b7-4792-a277-97f76c11ec0e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 2%

---

# Anpassen von Menüs anhand von „order.txt“-Dateien{#customize-a-menu-using-order-txt-files}

Sie können das Erscheinungsbild jedes Menüs anpassen, indem Sie die mit diesem Menü verknüpfte Datei order.txt bearbeiten.

Die Schritte in diesem Abschnitt gelten für alle Arten von Menüs.

**So bearbeiten Sie die Datei &quot;order.txt&quot;, um ein Menü anzupassen**

1. Klicken Sie in der Spalte [!DNL Profile Manager] in der Spalte *Profilname* mit der rechten Maustaste auf das Häkchen für die Datei [!DNL order.txt] und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL order.txt] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL order.txt] wird angezeigt.

   ![Schritt-Info](assets/cfg_ordertxt.png)

1. (Optional) Fügen Sie bei Bedarf die Einstellung [Inclusive] oder [Exclusive] oben in der Datei hinzu oder ändern Sie sie. Diese Einstellung steuert, ob Elemente, die nicht in der Datei [!DNL order.txt] aufgeführt sind, aber in [!DNL Profile Manager] vorhanden sind, im Menü aufgeführt werden. Zu den Optionen gehören:

   * **[Inclusive]:** Dies ist die Standardeinstellung. Diese Einstellung führt dazu, dass Menüelemente, die nicht in der [!DNL order.txt]Datei angegeben sind, unten im Menü in alphabetischer Reihenfolge aufgelistet werden. Wenn das [!DNL Profile Manager] beispielsweise ein Profilelement zusätzlich zu den unter [!DNL order.txt] aufgeführten enthält, würde das Profil unter &quot;Daten&quot;angezeigt werden.

   * **[Exklusiv]:** Diese Einstellung führt dazu, dass Menüelemente, die nicht in der  [!DNL order.txt] Datei angegeben sind, aus dem Menü ausgeschlossen werden. Wenn das [!DNL Profile Manager] beispielsweise ein Profil -Element zusätzlich zu den unter [!DNL order.txt] aufgeführten enthält, wird das Profil nirgends im Menü angezeigt.

   * **leer:** Wenn weder  [] Einschließen noch  [] Ausschließen oben in der Datei angezeigt wird, zeigt Data Workbench die Menüelemente so an, als wäre die Einstellung  [Einbezogen].

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
    <td colname="col2"> <p>Geben Sie die Elementnamen in der Reihenfolge ein, in der sie in Data Workbench angezeigt werden sollen. </p> <p>Solange beispielsweise jeder Name des Menüelements mit dem zugehörigen Datei- oder Ordnernamen übereinstimmt, würde Folgendes dazu führen, dass <b> Tabelle</b> zuerst angezeigt wird, dann <b>Visualisierung hinzufügen</b>, <b>Legende hinzufügen</b> und <b>Notiz hinzufügen</b> zuletzt angezeigt werden. </p> <p><b>Tabelle hinzufügen  </b> </p> <p><b>Visualisierung hinzufügen  </b> </p> <p><b>Legende hinzufügen  </b> </p> <p><b>Notiz hinzufügen </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Umbenennen eines Menüelements </p> </td> 
    <td colname="col2"> <p>Benennen Sie die entsprechende Datei oder den Ordner im <span class="wintitle"> Profil-Manager</span> um und ändern Sie dann den Namen des Elements in der Datei <span class="filepath"> order.txt</span> . </p> <p>Um beispielsweise Anmerkung zu neuer Anmerkung hinzufügen umzubenennen, benennen Sie den Ordner Anmerkung hinzufügen im <span class="wintitle"> Profil-Manager</span> in Neue Anmerkung um und ändern Sie dann den Namen des Elements Anmerkung hinzufügen in der Datei <span class="filepath"> order.txt</span> in Neue Anmerkung. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ausblenden von Menüelementen </p> </td> 
    <td colname="col2"> <p>Um das Menüelement auszublenden, das Element jedoch nicht zu löschen, geben Sie am Anfang des Namens ein Minuszeichen (-) ein. </p> <p>Beispielsweise werden die folgenden Ergebnisse in <span class="wintitle"> Anmerkung hinzufügen</span> nicht im Menü angezeigt. </p> <p>Legende hinzufügen </p> <p>-Anmerkung hinzufügen </p> <p>Um das ausgeblendete Menüelement erneut anzuzeigen, entfernen Sie einfach das Minuszeichen (-) oder verwenden Sie den Parameter Alle einblenden in der Datei <span class="filepath"> Insight.cfg</span>, siehe <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight-Konfigurationsparameter</a>. </p> <p>Sie können Menüelemente auch mit den folgenden Methoden ausblenden: 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>Der Parameter Anzeigen in einer Datei <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span> oder <span class="filepath"> .dim</span> blendet Filter, abgeleitete Metriken und Dimensionen sowie erweiterte Dimensionen aus ihren jeweiligen Menüs aus. Bei Verwendung dieser Option wird das Element nicht im Menü aufgelistet, es befindet sich jedoch noch im Profil und kann verwendet werden. </p> <p>Um mithilfe dieses Parameters Filter und abgeleitete Metriken und Dimensionen auszublenden, fügen Sie die folgende Zeile am Ende der Datei <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span> oder <span class="filepath"> .filter</span> hinzu: </p> <p><span class="filepath"> show = bool: false</span> </p> <p>Um diesen Parameter zum Ausblenden erweiterter Dimensionen zu verwenden, finden Sie Anweisungen in Kapitel 10 des <i>Leitfadens zur Datensatzkonfiguration</i>. </p> <p>Sie können Elemente, die mit dieser Methode ausgeblendet werden, vorübergehend wieder einblenden, indem Sie den Parameter "Alle einblenden"in der Datei <span class="filepath"> Insight.cfg</span> festlegen. Weitere Informationen zu diesem Parameter finden Sie unter <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight-Konfigurationsparameter</a>. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">Der Parameter Ausgeblendet in der Datei <span class="filepath"> Transformation.cfg</span> oder in einer beliebigen Datensatzeinschlussdatei blendet erweiterte Dimensionen aus dem Dimensionsmenü aus. Bei Verwendung dieser Option wird das Element nicht im Menü aufgelistet, es befindet sich jedoch noch im Profil und kann verwendet werden. <p> <p>Hinweis:  Wenn Sie erweiterte Dimensionen mit dieser Methode ausblenden, müssen Sie den Datensatz umtransformieren, damit die Dimensionen ausgeblendet werden. </p> </p> <p>Sie können Elemente, die mit dieser Methode ausgeblendet werden, vorübergehend wieder einblenden, indem Sie den Parameter "Alle einblenden"in der Datei <span class="filepath"> Insight.cfg</span> festlegen. Weitere Informationen zu diesem Parameter finden Sie unter <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight-Konfigurationsparameter</a>. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Mit Nullbyte-Dateien werden alle Elementtypen in jedem Menü ausgeblendet. Bei Verwendung dieser Option wird durch eine leere (0-Byte-)Datei das Vorhandensein einer Datei mit demselben Namen, die Daten enthält, ausgeblendet. Data Workbench behandelt Nullbyte-Dateien so, als wären sie nicht vorhanden. Weitere Informationen finden Sie unter <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ausblenden von Dateien mit leeren (Null-Byte-)Dateien</a>. </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Löschen von Menüelementen </p> </td> 
    <td colname="col2"> <p>Wenn diese Datei so eingestellt ist, dass sie die Option [exklusiv] verwendet, können Sie das Menüelement einfach aus dieser Datei löschen. Das Element selbst befindet sich weiterhin im Profil, wird jedoch nicht im Menü aufgeführt. </p> <p>Wenn diese Datei so eingestellt ist, dass sie die Option [Inclusive] verwendet, müssen Sie den Menüelementnamen aus dieser Datei entfernen und entweder die entsprechende Datei löschen oder Nullbyte verwenden, um das Element aus dem Menü zu entfernen. </p> <p>Informationen zum Löschen von Dateien finden Sie unter <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> Löschen von Dateien aus Ihrem Arbeitsprofil</a>. Weitere Informationen zu Nullbyte-Dateien finden Sie unter <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ausblenden von Dateien mit leeren (Zero-Byte-)Dateien</a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Hinzufügen eines Gruppierungs-Headers </p> </td> 
    <td colname="col2"> <p>Geben Sie drei Bindestriche vor und nach dem Überschriftentext ein, der angezeigt werden soll. </p> <p>Beispielsweise würde Folgendes zu einer Kopfzeile zum Verwalten von Gruppen für eine Reihe verwandter Menüelemente führen. </p> <p>---Verwalten--- </p> <p>Profil </p> <p>Datensatz </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Hinzufügen einer Zeile zu separaten Abschnitten eines Menüs </p> </td> 
    <td colname="col2"> <p>Geben Sie drei Bindestriche an, an denen eine Linie angezeigt werden soll. </p> <p>Beispielsweise führt die folgende Zeile dazu, dass Anmerkung hinzufügen und Benutzerdefiniert hinzufügen getrennt werden. </p> <p>Anmerkung hinzufügen </p> <p>— </p> <p>Benutzerdefiniert hinzufügen </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Speichern und schließen Sie die Datei.
1. (Optional) Um die Änderungen für alle Benutzer des Arbeitsprofils verfügbar zu machen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für die Datei [!DNL order.txt] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
