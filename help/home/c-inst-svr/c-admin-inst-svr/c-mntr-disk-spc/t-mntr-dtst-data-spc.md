---
description: Informationen zur Überwachung des Datensatzes und zum Hinzufügen neuer Speicherorte für die Datenspeicherung der Datensatzdaten.
solution: Analytics
title: Überwachen des Festplattenspeichers für Datensatzdaten
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---


# Überwachen des Festplattenspeichers für Datensatzdaten{#monitoring-dataset-data-space}

Informationen zur Überwachung des Datensatzes und zum Hinzufügen neuer Speicherorte für die Datenspeicherung der Datensatzdaten.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Standardmäßig [!DNL Insight Server] schreibt der Datensatz in die [!DNL temp.db] Datei auf demselben Laufwerk wie die [!DNL Insight Server] Videodateien in der Datenverarbeitungseinheit. Die Menge der Datensatzdaten pro [!DNL Insight Server] Computer ist auf Folgendes beschränkt, je nachdem, was zuerst eintritt:

* 500 Millionen Datensätze über die Dateneingabe zu diesem Datensatz
* 500 GB gespeicherte Datensatzdaten
* Eine (1) MB an Datensatzdaten, die pro Dimension einer Stammebene gespeichert werden (z. B. 5.000 Datensätze pro Besucher bei durchschnittlich 200 Byte pro Datensatz)

Wenn Sie den Datensatz auf einem anderen Laufwerk verwalten möchten oder wenn die zu erfassende Datenmenge die Verwendung mehrerer Laufwerke erfordert, müssen Sie die Konfigurationsdatei für die Disk-Dateien aktualisieren ( [!DNL Insight Server] ), um anzugeben, wo Sie die [!DNL Disk Files.cfg]Datei(en) [!DNL Insight Server] [!DNL temp.db] schreiben möchten. Die [!DNL Disk Files.cfg] Datei Liste die Festplattendateien (Zeichenfolgen-Vektor) und gibt den Speicherort der Datensatzdaten an, die bei der [!DNL Insight Server] Wiederaufbereitung und dem Vorgang verwendet werden. Es gibt normalerweise eine Datei pro Laufwerk.

>[!NOTE]
>
>Der Inhalt der [!DNL Disk Files.cfg] Datei wurde möglicherweise während der Installation geändert [!DNL Insight Server]. Weitere Informationen finden Sie unter [Speicherort des Datensatzes konfigurieren (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**So fügen Sie neue Speicherorte für die DataSet-Datenspeicherung hinzu**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] Objekts und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie im [!DNL Server Files Manager]Fenster auf , **[!UICONTROL Components]** um den Inhalt der Datei Ansicht. Die [!DNL Disk Files.cfg] Datei befindet sich in diesem Ordner.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Disk Files.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL Disk Files.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im [!DNL Disk Files.cfg] Fenster auf **[!UICONTROL component]** , um den Inhalt des Fensters Ansicht.

   ![Schritt-Info](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Der Parameter &quot;Festplattenbeschädigung erkennen&quot;ist standardmäßig auf &quot;true&quot;gesetzt. Der Parameter Disk Cache Size (MB) steuert die Speichergröße, die zur Erhöhung der Festplattenzugriffsgeschwindigkeit verwendet wird, und ist standardmäßig auf 128 eingestellt. [!DNL Insight Server] Bitte kontaktieren Sie die Adobe, bevor Sie einen dieser Parameter ändern.

1. Um die Festplattendateien auf dem [!DNL Insight Server] Computer zu ändern, klicken Sie mit der rechten Maustaste **[!UICONTROL Disk Files]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Um eine Disk-Datei zu löschen, klicken Sie mit der rechten Maustaste auf die Nummer der Disk-Datei und klicken Sie auf **[!UICONTROL Remove]**.

1. Geben Sie für die neue Disk-Datei den Ordner und den Namen der Datei ein, die bei der [!DNL Insight Server] Wiederaufbereitung und dem Vorgang verwendet werden soll.

   ![Schritt-Info](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Der Parameter &quot;Festplattenbeschädigung erkennen&quot;ist standardmäßig auf &quot;true&quot;gesetzt. Der Parameter Disk Cache Size (MB) steuert die Speichergröße, die zur Erhöhung der Festplattenzugriffsgeschwindigkeit verwendet wird, und ist standardmäßig auf 128 eingestellt. [!DNL Insight Server] Bitte kontaktieren Sie die Adobe, bevor Sie einen dieser Parameter ändern.

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Server Files Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei und wählen Sie [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

