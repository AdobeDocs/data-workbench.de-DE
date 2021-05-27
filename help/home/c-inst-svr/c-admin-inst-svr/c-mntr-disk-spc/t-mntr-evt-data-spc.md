---
description: Informationen zur Überwachung des Ereignisdatenspeichers und zum Ändern des Protokollverzeichnisses für Sensor-Daten.
title: Überwachen des Festplattenspeichers für Ereignisdaten
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Überwachen des Festplattenspeichers für Ereignisdaten{#monitoring-event-data-space}

Informationen zur Überwachung des Ereignisdatenspeichers und zum Ändern des Protokollverzeichnisses für Sensor-Daten.

**Empfohlene Häufigkeit:** Alle 5-10 Minuten

[!DNL Insight Server] speichert je nach Konfiguration eine Protokolldatei  [!DNL Sensor] pro Tag entweder in der Datenverarbeitungseinheit oder in der File Server Unit. Die Größe der Protokolldateien und der für sie erforderliche Datenspeicherplatz hängen von vielen Variablen ab, z. B. von der Anzahl der protokollierten Websites und der Anzahl der Anfragen, die Ihre Webserver pro Sekunde erhalten.

Eine typische Installation von [!DNL Insight Server] (oder einem [!DNL Insight Server]-Cluster) kann mehrere Terabyte von Daten speichern, vorausgesetzt, die Implementierung verwendet die von Adobe empfohlene Hardware für die [!DNL Insight Server]-Computer.

In der Regel bleiben alle Protokolldaten auf dem Computer [!DNL Insight Server] vorhanden. Wenn es erforderlich wird, mehr Datenspeicherplatz auf dem Computer verfügbar zu machen, können Sie alle Protokolldateien des aktuellen Tages auf einen anderen Computer oder ein Datenspeichermedium verschieben (ZIP-Laufwerk, Band usw.). Zum Verschieben der Daten ist es nicht erforderlich, [!DNL Insight Server] anzuhalten. Außerdem hat dies keine Auswirkungen auf die in [!DNL Insights] verfügbaren Funktionen, die mit [!DNL Insight Server] verbunden sein können und mit kontinuierlichen Daten arbeiten. Sofern Sie einen Analysedatensatz nicht verarbeiten oder erneut verarbeiten, behalten Sie den Zugriff auf alle vorherigen Daten bei und neue Daten sind weiterhin in [!DNL Insight] verfügbar. Wenn Sie einen Analysedatensatz verarbeiten oder erneut verarbeiten, können Sie erst nach Abschluss der Verarbeitung auf die Daten zugreifen.

Standardmäßig werden Ereignisdaten, die von [!DNL Sensor] erzeugt und an [!DNL Insight Server] übertragen werden, im Ordner [!DNL Logs] im Installationsverzeichnis von [!DNL Insight Server] gespeichert. Die Konfigurationsdatei für die Kommunikation [!DNL Communications.cfg] gibt den Speicherort der Ereignisdatenprotokolldateien an, die von [!DNL Insight Server] gelesen werden.

**So ändern Sie den Protokollordner für  [!DNL Sensor] Daten**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.
1. Klicken Sie mit der rechten Maustaste auf das Symbol des zu konfigurierenden [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.
1. Klicken Sie in [!DNL Server Files Manager] auf **[!UICONTROL Components]** , um den Inhalt anzuzeigen. Die Datei [!DNL Communications.cfg] befindet sich in diesem Verzeichnis.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* für [!DNL Communications.cfg] und klicken Sie auf **[!UICONTROL Make Local]**. In der Spalte [!DNL Temp] für [!DNL Communications.cfg] wird ein Häkchen angezeigt.
1. Klicken Sie mit der rechten Maustaste auf das neu erstellte Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicken Sie im Fenster [!DNL Communications.cfg] auf **[!UICONTROL component]** , um den Inhalt anzuzeigen.
1. Klicken Sie im Fenster [!DNL Communications.cfg] auf **[!UICONTROL Servers]** , um den Inhalt anzuzeigen. Es können verschiedene Servertypen auftreten: Dateiserver, Protokollierungsserver, Init-Server, Statusserver, Sendeserver oder Replizierungsserver.
1. Suchen Sie nach dem LoggingServer, wo [!DNL Sensor] seine Protokolldateien zur Verarbeitung durch [!DNL Insight Server] schreibt, und klicken Sie auf die zugehörige Nummer, um das Menü anzuzeigen.

   ![Schritt-Info](assets/cfg_communications_examplevalues_logging.png)

   Der standardmäßige Protokollordner ist der Ordner [!DNL Logs] im Installationsordner von [!DNL Insight Server].

1. Bearbeiten Sie den Parameter Protokollverzeichnis , um den gewünschten Speicherort der Protokolldateien anzuzeigen.

   >[!NOTE]
   >
   >Ändern Sie keine anderen Parameter für den LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Mehrere FileServer-Server können unter dem Server-Knoten aufgelistet werden. Daher müssen Sie möglicherweise den Inhalt vieler dieser Server anzeigen (indem Sie auf ihre Nummern in der Liste [!DNL Servers] klicken), um den Server mit einem lokalen Pfad von Protokollen zu finden, der geändert werden soll.

1. Bearbeiten Sie den lokalen Pfad, um den gewünschten Speicherort der [!DNL .vsl]-Dateien widerzuspiegeln.

   >[!NOTE]
   >
   >Ändern Sie keine anderen Parameter für den FileServer.

   Obwohl der Speicherort der Protokolldateien in der Datei [!DNL Communications.cfg] geändert wurde, können Sie diese Dateien dem Protokollverzeichnis von [!DNL Server Files Manager] zuordnen, indem Sie /Logs/ als URI für den FileServer angeben.

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
