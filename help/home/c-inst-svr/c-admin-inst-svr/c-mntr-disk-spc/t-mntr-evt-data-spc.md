---
description: Informationen zur Überwachung des Ereignis-Datenraums und zum Ändern des Protokollverzeichnisses für Sensor-Daten.
solution: Analytics
title: Überwachen des Festplattenspeichers für Ereignisdaten
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---


# Überwachen des Festplattenspeichers für Ereignisdaten{#monitoring-event-data-space}

Informationen zur Überwachung des Ereignis-Datenraums und zum Ändern des Protokollverzeichnisses für Sensor-Daten.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

[!DNL Insight Server] speichert je nach Konfiguration eine Protokolldatei pro [!DNL Sensor] Tag entweder auf der Datenverarbeitungseinheit oder auf der Dateiservereinheit. Die Größe der Protokolldateien und der erforderliche Datenspeicherplatz für die Datenspeicherung hängen von vielen Variablen ab, beispielsweise von der Anzahl der protokollierten Websites und der Anzahl der Anfragen, die Ihre Webserver pro Sekunde erhalten.

Eine typische Installation von [!DNL Insight Server] (oder einem [!DNL Insight Server] -Cluster) kann mehrere Terabytes von Daten speichern, vorausgesetzt, die Implementierung verwendet die von der Adobe für den bzw. die [!DNL Insight Server] Computer empfohlene Hardware.

Normalerweise bleiben alle Protokolldaten auf dem [!DNL Insight Server] Computer vorhanden. Wenn mehr Datenspeicherplatz auf dem Computer verfügbar gemacht werden muss, können Sie alle Protokolldateien bis auf den aktuellen Tag auf einen anderen Computer oder ein Datenmedium (Zip-Laufwerk, Datenspeicherung usw.) verschieben. Beim Verschieben der Daten müssen Sie nicht anhalten [!DNL Insight Server], und es hat keine Auswirkungen auf die Funktionalität, die in [!DNL Insights] den mit kontinuierlichen Daten verbundenen [!DNL Insight Server] und damit arbeitenden Daten verfügbar ist. Sofern Sie einen Analyse-Datensatz nicht verarbeiten oder erneut verarbeiten, behalten Sie den Zugriff auf alle vorherigen Daten bei und neue Daten stehen weiterhin zur Verfügung in [!DNL Insight]. Wenn Sie einen Analyse-Datensatz verarbeiten oder erneut verarbeiten, können Sie erst nach Abschluss der Verarbeitung auf die Daten zugreifen.

Standardmäßig werden Ereignis-Daten, die erstellt [!DNL Sensor] und an [!DNL Insight Server] den Ordner übertragen werden, im [!DNL Logs] Installationsordner gespeichert [!DNL Insight Server] . Die Kommunikationskonfigurationsdatei gibt [!DNL Communications.cfg]den Speicherort der Ereignis-Datenprotokolldateien an, die von gelesen werden [!DNL Insight Server].

**So ändern Sie den Protokollordner für[!DNL Sensor]Daten**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] Objekts und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie im [!DNL Server Files Manager]Fenster auf , **[!UICONTROL Components]** um den Inhalt der Datei Ansicht. Die [!DNL Communications.cfg] Datei befindet sich in diesem Ordner.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Communications.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der [!DNL Temp] Spalte für wird ein Häkchen angezeigt [!DNL Communications.cfg].
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im [!DNL Communications.cfg] Fenster auf **[!UICONTROL component]** , um den Inhalt des Fensters Ansicht.
1. Klicken Sie im [!DNL Communications.cfg] Fenster auf **[!UICONTROL Servers]** , um den Inhalt des Fensters Ansicht. Es können mehrere Servertypen auftreten: Dateiserver, Protokollierungsserver, Initserver, Statusserver, Senden-Server oder Replizieren von Servern.
1. Suchen Sie nach dem LoggingServer, in dem die Protokolldateien zur Verarbeitung [!DNL Sensor] geschrieben werden, [!DNL Insight Server]und klicken Sie auf die entsprechende Nummer, um das Menü Ansicht.

   ![Schritt-Info](assets/cfg_communications_examplevalues_logging.png)

   Der Standardprotokollordner ist der [!DNL Logs] Ordner im [!DNL Insight Server] Installationsordner.

1. Bearbeiten Sie den Parameter Protokollverzeichnis, um den gewünschten Speicherort der Protokolldateien anzuzeigen.

   >[!NOTE]
   >
   >Ändern Sie keine anderen Parameter für den LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Mehrere FileServer-Instanzen werden unter dem Server-Knoten aufgelistet. Daher müssen Sie ggf. den Inhalt vieler dieser Server (durch Klicken auf die Nummern in der [!DNL Servers] Liste) Ansicht haben, um den Server mit einem lokalen Pfad der Protokolle zu finden, der geändert werden muss.

1. Bearbeiten Sie den lokalen Pfad, um den gewünschten Speicherort der [!DNL .vsl] Dateien anzuzeigen.

   >[!NOTE]
   >
   >Ändern Sie keine anderen Parameter für FileServer.

   Obwohl der Speicherort der Protokolldateien in der [!DNL Communications.cfg] Datei geändert wurde, können Sie diese Dateien dem Protokollordner des Ordners zuordnen, [!DNL Server Files Manager] indem Sie /Logs/ als URI für den FileServer angeben.

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Server Files Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei und wählen Sie [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

