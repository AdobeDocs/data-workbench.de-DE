---
description: Die Konfigurationsdatei Transform Mode.cfg ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offline-Quellen anzugeben oder anzugeben, wie häufig der Data Workbench-Server, der die Umwandlungsfunktion durchführt, seine Statusdateien speichert.
title: Datei „Transform mode.cfg“
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 4%

---

# Datei „Transform mode.cfg“{#the-transform-mode-cfg-file}

Die Konfigurationsdatei Transform Mode.cfg ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offline-Quellen anzugeben oder anzugeben, wie häufig der Data Workbench-Server, der die Umwandlungsfunktion durchführt, seine Statusdateien speichert.

Änderungen an der [!DNL Transform Mode.cfg]-Datei, einschließlich Hinzufügen oder Entfernen von Quellen, führen nicht zur erneuten Verarbeitung der Daten.

**So bearbeiten Sie die Datei &quot;Transform Mode.cfg&quot;für ein Datensatzprofil**

1. Öffnen Sie bei der Arbeit mit dem Profil, dessen Daten Sie exportieren möchten, [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** , um den Inhalt des Ordners anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Transform Mode.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird in der Spalte [!DNL User] angezeigt.
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
    <td colname="col2"> <p>Maske der Offline-Protokollquelle. </p> <p> So geben Sie eine Offline-Quelle an: </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> Offline-Quellen</span> und klicken Sie auf <span class="uicontrol"> Hinzufügen neuer</span> &gt; <span class="uicontrol"> Quelle</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> Geben Sie im Parameter für die neue Quelle die Maske der Protokollsequenz ein. Bei Sensor-Protokollquellen mit Dateinamen im Format <span class="filepath"> JJJMMTT-SENSORID.vsl</span> wird bei der Maske <i>SENSORID.SENSORID</i> zwischen Groß- und Kleinschreibung unterschieden. Bei Protokolldateiquellen ist die Maske die Zeichenfolge, die vom <span class="wintitle"> Maskenmuster</span> extrahiert wird (siehe <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Protokolldateien</a>). </li> 
    </ul> <p> Das Hinzufügen oder Entfernen von Quellen aus <span class="wintitle"> Offline-Quellen</span> führt nicht zur erneuten Verarbeitung des Datensatzes. </p> <p> Ab der Zeit werden Messungen für die Verarbeitung der Online-Quellen des Profils durchgeführt. Wenn die Offline-Quelle wieder online ist, wird die Verarbeitung der eingehenden Protokolldateien für diese Quelle fortgesetzt. </p> <p> <p>Hinweis: Immer wenn eine Quelle wieder online geht, sollten Sie sie aus <span class="wintitle"> Offline-Quellen</span> entfernen. Andernfalls behandelt der Data Workbench-Server die Quelle als Online-Quelle und aktualisiert die Ausführungsdauer, solange die Quelle Daten sendet. Wenn die Quelle wieder offline geht, werden die Ausführungszeitmessungen angehalten. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> angehalten </td> 
    <td colname="col2"> Wahr oder falsch. Wenn "true", werden neue Daten nicht in den Datensatz verarbeitet. Der Standardwert ist „false“. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Speicherintervall (Sek.) </td> 
    <td colname="col2"> <p>Häufigkeit, mit der der Data Workbench-Server, auf dem die Umwandlungsfunktion ausgeführt wird, seine Statusdateien speichert. Der Standardwert lautet 3600. </p> <p> <p>Hinweis:  Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Beim Bearbeiten der Datei [!DNL Transform Mode.cfg] in einem Data Workbench-Fenster können Sie Tastaturbefehle für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x ), Kopieren (Strg+C), Einfügen (Strg+V ), Rückgängigmachen (Strg+Z ), Wiederholen (Strg+Umschalt+Z ), Auswahl des Bereichs (Klicken+Ziehen) und Auswahl aller Elemente (Strg+A ). Darüber hinaus können Sie die Verknüpfungen verwenden, um Text aus einer Konfigurationsdatei ( [!DNL .cfg]) in eine andere einzufügen.

1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.
1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Data Workbench [!DNL Transform Mode.cfg] in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, wobei der Profilname der Name des Profils ist, für das Sie Daten exportieren. Die erneute Verarbeitung der Daten beginnt nach der Synchronisierung des Profils.

   Informationen zur erneuten Verarbeitung Ihrer Daten für den Export finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
