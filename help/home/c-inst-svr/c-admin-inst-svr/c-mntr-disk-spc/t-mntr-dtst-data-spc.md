---
description: Informationen zur Datensatzüberwachung und zum Hinzufügen neuer Speicherorte für die Datensatzdatenspeicherung.
title: Überwachen des Festplattenspeichers für Datensatzdaten
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# Überwachen des Festplattenspeichers für Datensatzdaten{#monitoring-dataset-data-space}

{{eol}}

Informationen zur Datensatzüberwachung und zum Hinzufügen neuer Speicherorte für die Datensatzdatenspeicherung.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

Standardmäßig [!DNL Insight Server] schreibt seinen Datensatz in die [!DNL temp.db] Datei auf demselben Laufwerk wie der [!DNL Insight Server] Programmdateien in der Datenverarbeitungseinheit. Die Menge an Datensatzdaten pro [!DNL Insight Server] Maschine ist auf Folgendes beschränkt, je nachdem, was zuerst eintritt:

* 500 Millionen Datensätze zur Dateneingabe in diesen Datensatz
* 500 GB gespeicherte Datensatzdaten
* Eine (1) MB an Datensatzdaten, die pro Dimension auf der Stammebene gespeichert werden (z. B. 5.000 Datensätze pro Besucher bei durchschnittlich 200 Byte pro Datensatz)

Wenn Sie möchten [!DNL Insight Server] um den Datensatz auf einem anderen Laufwerk zu verwalten oder wenn die Menge der Daten, die Sie erwarten, zu erfassen, die Verwendung mehrerer Laufwerke erfordert, müssen Sie die Konfigurationsdatei für die Festplattendateien aktualisieren ( [!DNL Disk Files.cfg]), um anzugeben, wo Sie möchten [!DNL Insight Server] , um [!DNL temp.db] Datei(en). Die [!DNL Disk Files.cfg] -Datei listet die Festplattendateien (ein Zeichenfolgenvektor) auf und gibt den Speicherort der Datensatzdaten an, die von [!DNL Insight Server] während der Wiederaufbereitung und des Betriebs. Normalerweise gibt es eine Datei pro physischem Laufwerk.

>[!NOTE]
>
>Der Inhalt der [!DNL Disk Files.cfg] möglicherweise während der Installation [!DNL Insight Server]. Weitere Informationen finden Sie unter [Konfigurieren des Datensatzstandorts (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Hinzufügen neuer Speicherorte für die Datenspeicherung von Datensätzen**

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol der [!DNL Insight Server] Sie möchten konfigurieren und klicken Sie auf **[!UICONTROL Server Files]**.
1. Im [!DNL Server Files Manager]klicken **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die [!DNL Disk Files.cfg] -Datei befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* Spalte für [!DNL Disk Files.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. Ein Häkchen wird im [!DNL Temp] Spalte für [!DNL Disk Files.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Im [!DNL Disk Files.cfg] Fenster, klicken Sie auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.

   ![Schritt-Info](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Der Parameter &quot;Festplattenbeschädigung erkennen&quot;ist standardmäßig auf &quot;true&quot;gesetzt. Der Parameter Disk Cache Size (MB) steuert die Speichermenge, die [!DNL Insight Server] verwendet , um die Geschwindigkeit des Festplattenzugriffs zu erhöhen, und ist standardmäßig auf 128 eingestellt. Wenden Sie sich an die Adobe, bevor Sie einen dieser Parameter ändern.

1. So ändern Sie die Festplattendateien auf der [!DNL Insight Server] Machine, Rechtsklick **[!UICONTROL Disk Files]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Um eine Festplattendatei zu löschen, klicken Sie mit der rechten Maustaste auf die Nummer der Festplattendatei und klicken Sie auf **[!UICONTROL Remove]**.

1. Geben Sie für die neue Festplattendatei den Ordner und den Namen der Datei ein, die von [!DNL Insight Server] während der Wiederaufbereitung und des Betriebs.

   ![Schritt-Info](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Der Parameter &quot;Festplattenbeschädigung erkennen&quot;ist standardmäßig auf &quot;true&quot;gesetzt. Der Parameter Disk Cache Size (MB) steuert die Speichermenge, die [!DNL Insight Server] verwendet , um die Geschwindigkeit des Festplattenzugriffs zu erhöhen, und ist standardmäßig auf 128 eingestellt. Wenden Sie sich an die Adobe, bevor Sie einen dieser Parameter ändern.

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
