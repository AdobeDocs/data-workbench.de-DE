---
description: Die Konfigurationsdatei Transform Mode.cfg ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offline-Quellen anzugeben oder anzugeben, wie häufig der Data Workbench-Server, der die Umwandlungsfunktion durchführt, seine Statusdateien speichert.
title: Datei „Transform mode.cfg“
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 3%

---

# Datei „Transform mode.cfg“{#the-transform-mode-cfg-file}

{{eol}}

Die Konfigurationsdatei Transform Mode.cfg ermöglicht es Ihnen, die Verarbeitung von Daten in einem Datensatz anzuhalten, Offline-Quellen anzugeben oder anzugeben, wie häufig der Data Workbench-Server, der die Umwandlungsfunktion durchführt, seine Statusdateien speichert.

Änderungen an der [!DNL Transform Mode.cfg] -Datei, einschließlich Hinzufügen oder Entfernen von Quellen, führt nicht zur erneuten Verarbeitung der Daten.

**So bearbeiten Sie die Datei &quot;Transform Mode.cfg&quot;für ein Datensatzprofil**

1. Wenn Sie in dem Profil arbeiten, dessen Daten Sie exportieren möchten, öffnen Sie die [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]** um den Inhalt des Ordners anzuzeigen.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen neben [!DNL Transform Mode.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen für diese Datei wird im [!DNL User] Spalte.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Die [!DNL Transform Mode.cfg] angezeigt.
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
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Rechtsklick <span class="uicontrol"> Offline-Quellen</span> und klicken Sie auf <span class="uicontrol"> Neu hinzufügen</span> &gt; <span class="uicontrol"> Quelle</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> Geben Sie im Parameter für die neue Quelle die Maske der Protokollsequenz ein. Für Sensor-Protokollquellen mit Dateinamen des Formats <span class="filepath"> JJJJMMTT-SENSORID.vsl</span>, lautet die Maske <i>SENSORID.SENSORID</i> zwischen Groß- und Kleinschreibung unterschieden wird. Bei Protokollquellen für Protokolldateien ist die Maske die Zeichenfolge, die von der <span class="wintitle"> Maskenmuster</span> (siehe <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Protokolldateien</a>). </li> 
    </ul> <p> Hinzufügen oder Entfernen von Quellen aus <span class="wintitle"> Offline-Quellen</span> führt nicht zur erneuten Verarbeitung des Datensatzes. </p> <p> Ab der Zeit werden Messungen für die Verarbeitung der Online-Quellen des Profils durchgeführt. Wenn die Offline-Quelle wieder online ist, wird die Verarbeitung der eingehenden Protokolldateien für diese Quelle fortgesetzt. </p> <p> <p>Hinweis: Immer wenn eine Quelle wieder online geht, sollten Sie sie aus <span class="wintitle"> Offline-Quellen</span>. Andernfalls behandelt der Data Workbench-Server die Quelle als Online-Quelle und aktualisiert die Ausführungsdauer, solange die Quelle Daten sendet. Wenn die Quelle wieder offline geht, werden die Ausführungszeitmessungen angehalten. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> angehalten </td> 
    <td colname="col2"> True oder false. Wenn "true", werden neue Daten nicht in den Datensatz verarbeitet. Der Standardwert ist „false“. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Speicherintervall (Sek.) </td> 
    <td colname="col2"> <p>Häufigkeit, mit der der Data Workbench-Server, auf dem die Umwandlungsfunktion ausgeführt wird, seine Statusdateien speichert. Der Standardwert lautet 3600. </p> <p> <p>Hinweis: Sie sollten diesen Wert nicht ändern, ohne die Adobe zu konsultieren. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Beim Bearbeiten der [!DNL Transform Mode.cfg] -Datei in einem Data Workbench-Fenster verwenden, können Sie Tastaturbefehle für grundlegende Bearbeitungsfunktionen verwenden, z. B. Ausschneiden (Strg+x ), Kopieren (Strg+c) , Einfügen (Strg+V ), Rückgängigmachen (Strg+Z ), Wiederholen (Strg+Umschalt+Z ), Auswählen des Bereichs (Klicken+Ziehen) und Alle auswählen (Strg+A ). Darüber hinaus können Sie die Verknüpfungen verwenden, um Text aus einer Konfigurationsdatei zu kopieren und einzufügen ( [!DNL .cfg]) in eine andere.

1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.
1. Damit die lokal vorgenommenen Änderungen wirksam werden, finden Sie im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Data Workbench [!DNL Transform Mode.cfg] im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, wobei der Profilname der Name des Profils ist, für das Sie Daten exportieren. Die erneute Verarbeitung der Daten beginnt nach der Synchronisierung des Profils.

   Informationen zur erneuten Verarbeitung Ihrer Daten für den Export finden Sie unter [Wiederaufbereitung und erneute Umwandlung](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
