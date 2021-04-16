---
description: Informationen zur Überwachung des Ereignis-Datenraums und zum Ändern des Protokollverzeichnisses für Sensor-Daten.
title: Überwachen des Festplattenspeichers für Ereignisdaten
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Überwachen des Festplattenspeichers für Ereignisdaten{#monitoring-event-data-space}

Informationen zur Überwachung des Ereignis-Datenraums und zum Ändern des Protokollverzeichnisses für Sensor-Daten.

**Empfohlene Häufigkeit:** alle 5-10 Minuten

[!DNL Insight Server] speichert je nach Konfiguration eine Protokolldatei pro  [!DNL Sensor] Tag entweder auf der Datenverarbeitungseinheit oder auf der Dateiservereinheit. Die Größe der Protokolldateien und der erforderliche Datenspeicherplatz für die Datenspeicherung hängen von vielen Variablen ab, beispielsweise von der Anzahl der protokollierten Websites und der Anzahl der Anfragen, die Ihre Webserver pro Sekunde erhalten.

Eine typische Installation von [!DNL Insight Server] (oder einem [!DNL Insight Server]-Cluster) kann mehrere Terabytes von Daten speichern, vorausgesetzt, die Implementierung verwendet die von der Adobe für [!DNL Insight Server]-Computer(e) empfohlene Hardware.

Normalerweise bleiben alle Protokolldaten auf dem [!DNL Insight Server]-Computer vorhanden. Wenn mehr Datenspeicherplatz auf dem Computer verfügbar gemacht werden muss, können Sie alle Protokolldateien bis auf den aktuellen Tag auf einen anderen Computer oder ein Datenmedium (Zip-Laufwerk, Datenspeicherung usw.) verschieben. Beim Verschieben der Daten ist es nicht erforderlich, [!DNL Insight Server] anzuhalten, und es hat keine Auswirkungen auf die Funktionalität von [!DNL Insights], die mit [!DNL Insight Server] verbunden sein kann und mit kontinuierlichen Daten arbeitet. Sofern Sie einen Analyse-Datensatz nicht verarbeiten oder erneut verarbeiten, behalten Sie den Zugriff auf alle vorherigen Daten bei und neue Daten stehen weiterhin unter [!DNL Insight] zur Verfügung. Wenn Sie einen Analyse-Datensatz verarbeiten oder erneut verarbeiten, können Sie erst nach Abschluss der Verarbeitung auf die Daten zugreifen.

Standardmäßig werden Ereignis-Daten, die von [!DNL Sensor] erzeugt und an [!DNL Insight Server] übertragen werden, im [!DNL Logs]-Ordner im [!DNL Insight Server]-Installationsordner gespeichert. Die Kommunikationskonfigurationsdatei [!DNL Communications.cfg] gibt den Speicherort der Ereignis-Datenprotokolldateien an, die von [!DNL Insight Server] gelesen werden.

**So ändern Sie den Protokollordner für  [!DNL Sensor] Daten**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]**, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]**, um den Inhalt Ansicht. Die Datei [!DNL Communications.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Communications.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Communications.cfg] wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im Fenster [!DNL Communications.cfg] auf **[!UICONTROL component]**, um den Inhalt Ansicht.
1. Klicken Sie im Fenster [!DNL Communications.cfg] auf **[!UICONTROL Servers]**, um den Inhalt Ansicht. Es können mehrere Servertypen auftreten: Dateiserver, Protokollierungsserver, Initserver, Statusserver, Senden-Server oder Replizieren von Servern.
1. Suchen Sie nach dem LoggingServer, bei dem [!DNL Sensor] die Protokolldateien schreibt, die von [!DNL Insight Server] verarbeitet werden sollen, und klicken Sie auf dessen Nummer, um das Menü Ansicht.

   ![Schritt-Info](assets/cfg_communications_examplevalues_logging.png)

   Der Standardprotokollordner ist der Ordner [!DNL Logs] im Installationsordner [!DNL Insight Server].

1. Bearbeiten Sie den Parameter Protokollverzeichnis, um den gewünschten Speicherort der Protokolldateien anzuzeigen.

   >[!NOTE]
   >
   >Ändern Sie keine anderen Parameter für den LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Mehrere FileServers werden möglicherweise unter dem Server-Knoten aufgelistet. Daher müssen Sie ggf. den Inhalt vieler dieser Server (durch Klicken auf ihre Nummern in der [!DNL Servers]-Liste) Ansicht haben, um den Server mit einem lokalen Pfad der Protokolle\ zu finden.

1. Bearbeiten Sie den lokalen Pfad, um den gewünschten Speicherort der [!DNL .vsl]-Dateien anzuzeigen.

   >[!NOTE]
   >
   >Ändern Sie keine anderen Parameter für FileServer.

   Obwohl der Speicherort der Protokolldateien in der Datei [!DNL Communications.cfg] geändert wurde, können Sie diese Dateien dem Protokollordner von [!DNL Server Files Manager] zuordnen, indem Sie /Logs/ als URI für den FileServer angeben.

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
