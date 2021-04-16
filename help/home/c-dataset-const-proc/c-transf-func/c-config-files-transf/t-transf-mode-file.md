---
description: Die Konfigurationsdatei Transform Mode.cfg ermöglicht es Ihnen, die Verarbeitung von Daten in ein Dataset anzuhalten, Offlinequellen anzugeben oder die Häufigkeit anzugeben, mit der der Datenbasis-Server, auf dem die Transformationsfunktion ausgeführt wird, seine Statusdateien speichert.
title: Datei „Transform mode.cfg“
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 4%

---

# Datei „Transform mode.cfg“{#the-transform-mode-cfg-file}

Die Konfigurationsdatei Transform Mode.cfg ermöglicht es Ihnen, die Verarbeitung von Daten in ein Dataset anzuhalten, Offlinequellen anzugeben oder die Häufigkeit anzugeben, mit der der Datenbasis-Server, auf dem die Transformationsfunktion ausgeführt wird, seine Statusdateien speichert.

Änderungen an der Datei [!DNL Transform Mode.cfg], einschließlich des Hinzufügens oder Entfernen von Quellen, führen nicht zur erneuten Verarbeitung der Daten.

**So bearbeiten Sie die Datei &quot;Transform Mode.cfg&quot;für ein DataSet-Profil**

1. Wenn Sie im Profil arbeiten, dessen Daten Sie exportieren möchten, öffnen Sie das [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]**, um den Ordnerinhalt anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Transform Mode.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL User] wird ein Häkchen für diese Datei angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Das Fenster [!DNL Transform Mode.cfg] wird angezeigt.
1. Bearbeiten Sie die Parameter in der Konfigurationsdatei mithilfe der folgenden Tabelle als Anleitung:

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parameter </th> 
    <th colname="col2" class="entry"> Beschreibung </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> Offline-Quellen </td> 
    <td colname="col2"> <p>Maske der Offline-Protokollquelle. </p> <p> So legen Sie eine Offline-Quelle fest: </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Offline Sources</span> und klicken Sie auf <span class="uicontrol"> Hinzufügen new</span> &gt; <span class="uicontrol"> Quelle</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> Geben Sie im Parameter für die neue Quelle die Maske der Protokollsequenz ein. Bei Sensor-Protokollquellen mit Dateinamen des Formats <span class="filepath"> YYYJMMTT-SENSORID.vsl</span> wird bei der Maske die Groß-/Kleinschreibung beachtet. <i></i> Bei Protokollquellen für Protokolldateien ist die Maske die Zeichenfolge, die von <span class="wintitle"> Maskenmuster</span> extrahiert wird (siehe <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Protokolldateien</a>). </li> 
    </ul> <p> Das Hinzufügen oder Entfernen von Quellen von <span class="wintitle"> Offline-Quellen</span> führt nicht zur erneuten Verarbeitung des Datensatzes. </p> <p> Die Zeitmessungen werden für die Verarbeitung der Online-Quellen des Profils beibehalten. Wenn die Offline-Quelle erneut online ist, wird die Verarbeitung eingehender Protokolldateien für diese Quelle fortgesetzt. </p> <p> <p>Hinweis: Wenn eine Quelle wieder online ist, sollten Sie sie aus den Offline-Quellen <span class="wintitle"> entfernen. </span> Andernfalls behandelt der Data Workbench-Server die Quelle als Online-Quelle und aktualisiert die Ausführungszeit, solange die Quelle Daten sendet. Wenn die Quelle wieder offline ist, werden die Zeitüberschreitungsmessungen beendet. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> angehalten </td> 
    <td colname="col2"> Wahr oder falsch. Wenn "true", werden neue Daten nicht in den Datensatz verarbeitet. Der Standardwert ist „false“. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Speicherintervall (s) </td> 
    <td colname="col2"> <p>Die Häufigkeit, mit der der Data Workbench-Server, auf dem die Transformationsfunktion ausgeführt wird, seine Statusdateien speichert. Der Standardwert lautet 3600. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Beim Bearbeiten der Datei [!DNL Transform Mode.cfg] in einem Data Workbench-Fenster können Sie Tastenkombinationen für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x), Kopieren (Strg+c), Einfügen (Strg+v), Rückgängigmachen (Strg+Z), Wiederholen (Strg+Umschalt+Z), Abschnitt (Klicken+Ziehen) und Alles auswählen (Strg+a). Darüber hinaus können Sie mithilfe der Tastaturbefehle Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere kopieren und einfügen.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.
1. Um die lokal vorgenommenen Änderungen zu übernehmen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datenbasis [!DNL Transform Mode.cfg] in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, wobei der Profil-Name der Name des Profils ist, für das Sie Daten exportieren. Die erneute Verarbeitung der Daten beginnt nach der Synchronisierung des Profils.

   Weitere Informationen zur erneuten Verarbeitung Ihrer Daten für den Export finden Sie unter [Wiederaufbereitung und Verarbeitung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
