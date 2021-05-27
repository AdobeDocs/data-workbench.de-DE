---
description: Informationen zur Datensatzüberwachung und zum Hinzufügen neuer Speicherorte für die Datensatzdatenspeicherung.
title: Überwachen des Festplattenspeichers für Datensatzdaten
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# Überwachen des Festplattenspeichers für Datensatzdaten{#monitoring-dataset-data-space}

Informationen zur Datensatzüberwachung und zum Hinzufügen neuer Speicherorte für die Datensatzdatenspeicherung.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Standardmäßig schreibt [!DNL Insight Server] seinen Datensatz in die Datei [!DNL temp.db] auf demselben Laufwerk wie die Programmdateien [!DNL Insight Server] in der Datenverarbeitungseinheit. Die Menge der Datensatzdaten pro Maschine [!DNL Insight Server] ist auf Folgendes beschränkt, je nachdem, was zuerst eintritt:

* 500 Millionen Datensätze zur Dateneingabe in diesen Datensatz
* 500 GB gespeicherte Datensatzdaten
* Eine (1) MB an Datensatzdaten, die pro Dimension auf der Stammebene gespeichert werden (z. B. 5.000 Datensätze pro Besucher bei durchschnittlich 200 Byte pro Datensatz)

Wenn [!DNL Insight Server] den Datensatz auf einem anderen Laufwerk speichern soll oder wenn die Menge der zu erfassenden Daten die Verwendung mehrerer Laufwerke erfordert, müssen Sie die Konfigurationsdatei für die Festplattendateien ( [!DNL Disk Files.cfg]) aktualisieren, um anzugeben, wo [!DNL Insight Server] die [!DNL temp.db]-Datei(en) schreiben soll. Die Datei [!DNL Disk Files.cfg] listet die Festplattendateien (ein Vektor von Zeichenfolgen) auf und gibt den Speicherort der Datensatzdaten an, die von [!DNL Insight Server] während der Wiederaufbereitung und des Vorgangs verwendet werden. Normalerweise gibt es eine Datei pro physischem Laufwerk.

>[!NOTE]
>
>Der Inhalt der Datei [!DNL Disk Files.cfg] wurde möglicherweise bei der Installation von [!DNL Insight Server] geändert. Weitere Informationen finden Sie unter [Konfigurieren des Speicherorts des Datensatzes (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Hinzufügen neuer Speicherorte für die Datenspeicherung von Datensätzen**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL Disk Files.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Disk Files.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Disk Files.cfg] wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im Fenster [!DNL Disk Files.cfg] auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.

   ![Schritt-Info](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Der Parameter &quot;Festplattenbeschädigung erkennen&quot;ist standardmäßig auf &quot;true&quot;gesetzt. Der Parameter Disk Cache Size (MB) steuert die Speichermenge, die [!DNL Insight Server] verwendet, um die Geschwindigkeit des Festplattenzugriffs zu erhöhen, und ist standardmäßig auf 128 eingestellt. Wenden Sie sich an die Adobe, bevor Sie einen dieser Parameter ändern.

1. Um die Festplattendateien auf dem Computer [!DNL Insight Server] zu ändern, klicken Sie mit der rechten Maustaste auf **[!UICONTROL Disk Files]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Um eine Disk-Datei zu löschen, klicken Sie mit der rechten Maustaste auf die Nummer der Disk-Datei und klicken Sie auf **[!UICONTROL Remove]**.

1. Geben Sie für die neue Disk-Datei das Verzeichnis und den Namen der Datei ein, die von [!DNL Insight Server] während der Wiederaufbereitung und des Vorgangs verwendet werden soll.

   ![Schritt-Info](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Der Parameter &quot;Festplattenbeschädigung erkennen&quot;ist standardmäßig auf &quot;true&quot;gesetzt. Der Parameter Disk Cache Size (MB) steuert die Speichermenge, die [!DNL Insight Server] verwendet, um die Geschwindigkeit des Festplattenzugriffs zu erhöhen, und ist standardmäßig auf 128 eingestellt. Wenden Sie sich an die Adobe, bevor Sie einen dieser Parameter ändern.

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
