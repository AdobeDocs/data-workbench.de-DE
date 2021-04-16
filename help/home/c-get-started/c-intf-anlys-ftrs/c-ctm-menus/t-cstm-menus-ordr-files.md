---
description: Sie können das Erscheinungsbild eines Menüs anpassen, indem Sie die Datei order.txt bearbeiten, die mit diesem Menü verknüpft ist.
title: Anpassen von Menüs anhand von „order.txt“-Dateien
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
exl-id: 3803a56f-19b7-4792-a277-97f76c11ec0e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 2%

---

# Anpassen von Menüs anhand von „order.txt“-Dateien{#customize-a-menu-using-order-txt-files}

Sie können das Erscheinungsbild eines Menüs anpassen, indem Sie die Datei order.txt bearbeiten, die mit diesem Menü verknüpft ist.

Die Schritte in diesem Abschnitt gelten für alle Arten von Menüs.

**So bearbeiten Sie die Datei &quot;order.txt&quot;, um ein Menü anzupassen**

1. Klicken Sie in der Spalte [!DNL Profile Manager] in der Spalte *Profil-Name* mit der rechten Maustaste auf das Häkchen für die [!DNL order.txt]-Datei und klicken Sie auf **[!UICONTROL Make Local]**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei [!DNL order.txt] in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Die Datei [!DNL order.txt] wird angezeigt.

   ![Schritt-Info](assets/cfg_ordertxt.png)

1. (Optional) Hinzufügen oder ändern Sie die Einstellung [Inclusive] oder [Exclusive] oben in der Datei, falls gewünscht. Diese Einstellung steuert, ob Elemente, die nicht in der Datei [!DNL order.txt] aufgeführt, aber in [!DNL Profile Manager] vorhanden sind, im Menü aufgeführt werden. Zu den Optionen gehören:

   * **[Inclusive]:** Dies ist die Standardeinstellung. Diese Einstellung führt dazu, dass Menüelemente, die nicht in der Datei [!DNL order.txt]angegeben sind, am unteren Rand des Menüs in alphabetischer Reihenfolge aufgeführt werden. Wenn das [!DNL Profile Manager] beispielsweise ein Profil-Element zusätzlich zu den oben aufgeführten enthält, wird unter &quot;Daten&quot;ein Profil angezeigt.[!DNL order.txt]

   * **[Exklusiv]:** Diese Einstellung führt dazu, dass Menüelemente, die nicht in der  [!DNL order.txt] Datei angegeben sind, aus dem Menü ausgeschlossen werden. Wenn das [!DNL Profile Manager] z. B. ein Profil zusätzlich zu den oben aufgeführten enthält, wird das Profil nirgendwo im Menü angezeigt.[!DNL order.txt]

   * **leer:** Wenn oben in der Datei weder  [] Einschließen noch  [] Ausschließen angezeigt wird, zeigt die Data Workbench die Menüelemente so an, als wäre die Einstellung  [Einbezogen].

1. Führen Sie einen oder mehrere der folgenden Schritte aus:

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Um diese Aufgabe durchzuführen... </th> 
    <th colname="col2" class="entry"> Gehen Sie folgendermaßen vor... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Menüelemente neu anordnen </p> </td> 
    <td colname="col2"> <p>Geben Sie die Elementnamen in der Reihenfolge ein, in der sie in der Data Workbench angezeigt werden sollen. </p> <p>Solange beispielsweise jeder Name des Menüelements mit dem entsprechenden Datei- oder Ordnernamen übereinstimmt, würde Folgendes dazu führen, dass zuerst <b> Hinzufügen Tabelle</b> angezeigt wird, dann <b>Hinzufügen Visualisierung</b>, <b>Hinzufügen Legende</b> und <b>Hinzufügen Hinweis</b> zuletzt angezeigt wird. </p> <p><b>hinzufügen  </b> </p> <p><b>hinzufügen  </b> </p> <p><b>hinzufügen Legende  </b> </p> <p><b>Notiz hinzufügen </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Menüelement umbenennen </p> </td> 
    <td colname="col2"> <p>Benennen Sie die entsprechende Datei bzw. den Ordner im <span class="wintitle"> Profil-Manager</span> um und ändern Sie dann den Namen des Elements in der Datei <span class="filepath"> order.txt</span>. </p> <p>Um beispielsweise Hinzufügen Anmerkung in Neue Anmerkung umzubenennen, benennen Sie den Ordner "Hinzufügen Anmerkung"im <span class="wintitle"> Profil-Manager</span> in "Neue Anmerkung"um und ändern Sie dann den Namen des Hinzufügen Anmerkungselements in der Datei <span class="filepath"> order.txt</span> in "Neue Anmerkung". </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Menüelemente ausblenden </p> </td> 
    <td colname="col2"> <p>Um das Menüelement auszublenden, das Element selbst jedoch nicht zu löschen, geben Sie ein Minuszeichen (-) am Anfang des Namens ein. </p> <p>Die folgenden Ergebnisse zeigen beispielsweise, dass <span class="wintitle"> Hinzufügen Anmerkung</span> nicht im Menü angezeigt wird. </p> <p>hinzufügen Legende </p> <p>-Hinzufügen </p> <p>Um das ausgeblendete Menüelement erneut anzuzeigen, entfernen Sie einfach das Minuszeichen (-) oder verwenden Sie den Parameter "Rückgängig: Alle"in der Datei <span class="filepath"> Insight.cfg</span>, siehe <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight-Konfigurationsparameter</a>. </p> <p>Sie können Menüelemente auch wie folgt ausblenden: 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>Der Parameter Anzeigen in einer Datei <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span> oder <span class="filepath"> .dim</span> blendet Filter, abgeleitete Metriken und Dimensionen sowie erweiterte Dimensionen aus ihren jeweiligen Menüs aus. Wenn Sie diese Option verwenden, wird das Element nicht im Menü aufgeführt, aber es befindet sich noch im Profil und kann verwendet werden. </p> <p>Um mit diesem Parameter Filter und abgeleitete Metriken und Dimensionen auszublenden, fügen Sie die folgende Zeile am Ende der Datei <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span> oder <span class="filepath"> .filter</span> hinzu: </p> <p><span class="filepath"> show = bool: false</span> </p> <p>Informationen zum Ausblenden erweiterter Dimensionen mit diesem Parameter finden Sie in Kapitel 10 des <i>Handbuch zur Datenkonfiguration</i>. </p> <p>Sie können Elemente, die mit dieser Methode ausgeblendet werden, vorübergehend wieder einblenden, indem Sie den Parameter "Alle einblenden"in der Datei <span class="filepath"> Insight.cfg</span> festlegen. Weitere Informationen zu diesem Parameter finden Sie unter <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight-Konfigurationsparameter</a>. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">Der Parameter "Ausgeblendet"in der Datei <span class="filepath"> Transformation.cfg</span> oder ein Datensatz enthält die Datei "Erweiterte Dimensionen einschließen"im Dimensionsmenü. Wenn Sie diese Option verwenden, wird das Element nicht im Menü aufgeführt, aber es befindet sich noch im Profil und kann verwendet werden. <p> <p>Hinweis:  Wenn Sie erweiterte Dimensionen mit dieser Methode ausblenden, müssen Sie das Dataset neu transformieren, damit die Dimensionen ausgeblendet werden. </p> </p> <p>Sie können Elemente, die mit dieser Methode ausgeblendet werden, vorübergehend wieder einblenden, indem Sie den Parameter "Alle einblenden"in der Datei <span class="filepath"> Insight.cfg</span> festlegen. Weitere Informationen zu diesem Parameter finden Sie unter <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight-Konfigurationsparameter</a>. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Nullbyte-Dateien verbergen alle Elementtypen in jedem Menü. Bei Verwendung dieser Option wird durch eine leere (Null-Byte-)Datei das Vorhandensein einer Datei mit demselben Namen, die Daten enthält, ausgeblendet. Data Workbench behandelt Nullbyte-Dateien so, als wären sie nicht vorhanden. Weitere Informationen finden Sie unter <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ausblenden von Dateien mit leeren (Zero-Byte-)Dateien</a>. </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Löschen eines Menüelements </p> </td> 
    <td colname="col2"> <p>Wenn diese Datei so eingestellt ist, dass sie die Option [Ausschließen] verwendet, können Sie das Menüelement einfach aus dieser Datei löschen. Das Element selbst befindet sich zwar noch im Profil, wird aber nicht im Menü aufgeführt. </p> <p>Wenn diese Datei so eingestellt ist, dass sie die Option "[Einschließen]"verwendet, müssen Sie den Namen des Menüelements aus dieser Datei entfernen und entweder die entsprechende Datei löschen oder Null-Byte verwenden, um das Element aus dem Menü zu entfernen. </p> <p>Informationen zum Löschen von Dateien finden Sie unter <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> Löschen von Profilen aus Ihrem Arbeitsblatt</a>. Weitere Informationen zu Nullbyte-Dateien finden Sie unter <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ausblenden von Dateien mit leeren (Null-Byte-)Dateien</a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>hinzufügen einer Gruppenüberschrift </p> </td> 
    <td colname="col2"> <p>Geben Sie drei Bindestriche vor und nach dem Überschriftentext ein, der angezeigt werden soll. </p> <p>Beispielsweise würde die folgende Tabelle zu einer Kopfzeile der Gruppe verwalten für eine Reihe verwandter Menüelemente führen. </p> <p>---Verwalten--- </p> <p>Profil </p> <p>Datensatz </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>hinzufügen einer Zeile zum Trennen von Menüabschnitten </p> </td> 
    <td colname="col2"> <p>Geben Sie drei Bindestriche ein, in denen eine Linie angezeigt werden soll. </p> <p>Die folgenden Ergebnisse ergeben beispielsweise eine Zeile, die Hinzufügen Anmerkung und Hinzufügen benutzerdefiniert trennt. </p> <p>hinzufügen </p> <p>— </p> <p>hinzufügen </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Speichern und schließen Sie die Datei.
1. (Optional) Um die Änderungen allen Benutzern des funktionierenden Profils zur Verfügung zu stellen, klicken Sie mit der rechten Maustaste auf das weiße Häkchen für die [!DNL order.txt]-Datei in der Spalte [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
