---
description: Anweisungen zur Installation des Data Workbench-Überwachungsprofils.
title: Installieren des Überwachungsprofils
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# Installieren des Überwachungsprofils{#installing-the-monitoring-profile}

{{eol}}

Anweisungen zur Installation des Data Workbench-Überwachungsprofils.

## Installationsschritte {#section-d4355dbea8a447f48ab168db6ccff612}

1. Konfigurieren Sie eine neue Sensor-Instanz so, als ob sie für die Datenerfassung von getaggten Web-Seiten verwendet wird. Stellen Sie sicher, dass sich die Datei &quot;zig.gif&quot;im Dokumentenstamm des Sensor-Webservers befindet. Sensor kann auf demselben Host wie die Monitorprofile ausgeführt werden. (Dies ist kein Problem bei der Verwendung einer Textdatei zu diesem Zweck.)

   >[!NOTE]
   >
   >Diese Sensor-Instanz muss dafür ausgelegt sein, nur Traffic von den Überwachungsagenten zu empfangen. Außerdem kann der Sensor so konfiguriert werden, dass er an einem anderen Anschluss ausgeführt wird, wenn Sie einen Webserver für diese Sammlung wiederverwenden.

1. Im [!DNL txlogd.conf] -Datei gibt es die Standardzeile:

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Für die Data Workbench Monitoring Profile-Anwendung (oder eine beliebige &quot;getaggte&quot;Seitenimplementierung) muss der Bildtyp entfernt werden, um über eine GIF-Datei erfasst zu werden. Die aktualisierte Zeile lautet:

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. Kopieren Sie die [!DNL insight_monitor.zip/insight_monitor_agent] an einen temporären Speicherort.
1. Aktualisieren [!DNL insight_monitor_agent.cfg] -Datei für Ihre Umgebung. Befolgen Sie die Kommentare in der Konfigurationsdatei:

   **Die Konfigurationsdatei Überwachung :**

   ![](assets/monitor_agent_cfg_sensor.png)

   Definieren Sie, wo Sie alle Informationen sammeln, und geben Sie die URL-Adresse an. Dies muss ein spezieller Sensor sein und sollte außer dieser Anwendung keinen Traffic erhalten.

   ![](assets/monitor_agent_cfg_dump.png)

   Es gibt Pfade unter der Annahme, dass ein e vorhanden ist: Datenträger. Sie können diesen Pfad für Ihre Umgebung ändern.

   ![](assets/monitor_agent_cfg_quickcheck.png)

   Manchmal reagiert Data Workbench beim Ausführen eines Transform-Profils nicht. Mit diesem Wert können Sie eine Warnung senden, wenn der Prozess dreimal hintereinander nicht reagiert. So lassen sich falsch-positive Warnhinweise verringern.

   ![](assets/monitor_agent_cfg_groups.png)

   Hier legen Sie die Umgebungs- und Gruppendimensionen fest. Dies kann sich von Host zu Host unterscheiden.

   Dies ist w ![](assets/monitor_agent_cfg_debug.png)Hier können Sie genau sehen, was der Monitoragent tut, indem Sie Fehlerprotokolle in diesem Pfad anzeigen.

   ![](assets/monitor_agent_cfg_tempdb.png)

   Dies dient der internen Verwendung des temporären DB. Sie kann beim Erreichen der Kapazität gewarnt werden. Dies unterscheidet sich von der physischen Festplattenauslastung.

1. Kopieren Sie die *insight_monitor_agent* Ordner zu jedem DPU- und FSU-Host, der den Data Workbench-Server ausführt. Der in der Konfigurationsdatei angegebene Standardspeicherort lautet [!DNL e:\insight_monitor_agent] aber Sie können diesen Ort ändern.

1. Fügen Sie eine geplante Windows-Aufgabe hinzu, um den Agenten alle 10 Minuten aufzurufen (dieser Zeitraum wird in den Berechnungen der Verarbeitungsrate angenommen). Das Programm [!DNL e:insight_monitor/insight_monitor_agent.exe]. Das Argument ist config-file e:\insight_monitor\insight_monitor.cfg. Starten Sie in e:\insight_monitor. Der Benutzer, der die Aufgabe ausführt, muss über Lese-/Schreibrechte verfügen [!DNL e:\insight_monitor] und lesen Sie das Win32 OLE-Objekt [!DNL root\CIMV2] (erforderlich, um den Startmodus des Data Workbench-Server-Dienstes zu ermitteln und den Prozentsatz des Speicherplatzes auf lokalen Festplatten zu überprüfen)

1. Vergewissern Sie sich, dass die VSL mit der Akkumulation von Monitordatensätzen zunimmt. Dies wird einige Zeit in Anspruch nehmen, da das Traffic-Volumen in einer kleinen Installation extrem niedrig sein wird (alle 10 Minuten sendet der Agent nur einen Treffer für die hostspezifischen Daten sowie einen Treffer pro Verarbeitungsprofil).
1. Entpacken Sie die Datei insight_monitor.zip\profiles\Insight-Historie an einen temporären Speicherort.
1. Hostname aktualisieren in [!DNL profile.cfg], [!DNL dataset\cluster.cfg]und die [!DNL dataset\segment export.cfg].

1. Aktualisieren Sie die Dateien in das Profilverzeichnis der Data Workbench.
1. Aktualisieren des Protokollservers und des Pfads in [!DNL dataset\log processing.cfg] an den Ort, an dem sich der Sensor-VSL ansammelt.
1. [Optional] mit den Profilen [!DNL Insight Profile Status] und [!DNL Insight Server Status]. Außerdem sollten die Statusprofile nächtlich mit einem zweitägigen Nachverfolgungsfenster erneut verarbeitet werden. Hinzufügen einer geplanten Windows-Aufgabe: Das Programm [!DNL e:\insight_monitor\insight_reprocess.exe]. Das Argument lautet [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Urlaub [!DNL start in] leer. Hinzufügen einer weiteren geplanten Aufgabe für *&quot;Insight Server status&quot;*. *insight_reprocess.exe* erfordert Lese-/Schreibzugriff auf *log processing.cfg* um die Startzeit zu aktualisieren.

1. Außerdem sollten die Statusprofile nächtlich mit einem zweitägigen Nachverfolgungsfenster erneut verarbeitet werden. Hinzufügen einer geplanten Windows-Aufgabe: Das Programm *e:\insight_monitor\insight_reprocess.exe*. Das Argument lautet: [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Urlaub *Beginn in* leer. Hinzufügen einer weiteren geplanten Aufgabe für [!DNL "insight server status"]. [!DNL insight_reprocess.exe] erfordert Lese-/Schreibzugriff auf [!DNL log processing.cfg] um die Startzeit zu aktualisieren. Vergewissern Sie sich, dass jedes Profil die VSL liest, während sie sich ansammeln. Auch dies wird aufgrund des extrem niedrigen Volumens einige Zeit - wahrscheinlich Stunden - in Anspruch nehmen.

## Installationshinweise {#section-17722441ab0046fcbcb46b957d56230a}

* **Konfigurieren des Überwachungsprofils in einer lizenzierten Testumgebung**. Das Paket der Testumgebung ist in Ihrer Implementierung von Data Workbench enthalten, sodass Sie die Anwendung installieren und konfigurieren können. Bei einer Installation auf einem Produktions-FSU- oder DPU-Server müssen Sie den Server so konfigurieren, dass er auf einem separaten Port ausgeführt wird.
* **Bereitstellen eines neuen Sensors speziell für das Überwachungsprofil**. Sie müssen eine neue Instanz von Sensor auf dem Server installieren, auf dem das Überwachungsprofil ausgeführt wird. Dies erfolgt zusätzlich zur Produktionsinstanz von Sensor. (Für die Installation von Sensor auf einem Produktions- oder Nicht-Produktionsserver, speziell für das Überwachungsprofil, fallen keine zusätzlichen Gebühren an.)
* **Deaktivieren Sie den Monitoragenten während der Data Workbench-Wartung.**. Um eine Verschmutzung der Betriebszeit- und Leistungsmetriken zu vermeiden, können Sie den Dienststartmodus für den InsightServer-Dienst (Omniture Insight-Server) auf &quot;Manuell&quot;festlegen. Ein praktischer PowerShell-Befehl ist *set-service -name insightserver -startuptype manual*. Setzen Sie es nach der Wartung wieder auf automatisch: *set-service -name insightserver -startuptype automatisch*. Eine andere Möglichkeit besteht darin, die geplante Aufgabe des Überwachungsagenten vorübergehend zu deaktivieren.
* **Die Statusprofile benötigen ein nachstehendes Fenster** zum Ablegen alter Hosts und Profile sowie alter Host-Profil-Zuordnungen. Wenn die Anzahl der Ereignisdaten jedoch so gering ist, dass Data Workbench sie nicht puffert, müssen Sie die Fenstergröße möglicherweise etwas erweitern, um die Verarbeitung zu ermöglichen.
* **Der Agent erfasst den gesamten und ältesten Ausführungsstatus aus dem detaillierten Status von Data Workbench**, was in der lokalen Hostzeit gemeldet wird, vorausgesetzt, die Zeitstempel für die Ereignisdatenprotokolle befinden sich in UTC (wie in VSL Dateien). Wenn sich die Zeitstempel der Ereignisdaten in einer nicht-UTC-Zeitzone befinden, wird der Ausführungszeitpunkt im resultierenden Insight-Profilstatus-Profil versetzt. Wenn **all** der Zeitstempel Ihrer Ereignisdaten in derselben Zeitzone liegen, in der Sie diesen Versatz *Insight Profil Status\metrics\as of delay minutes.metric*.

* **Es wurden zwei neue Dimensionen eingeführt, um die Kundengruppe bei Servern mit unterschiedlichen Status zu unterstützen.**, wie Produktion, Staging, Testserver und Server in anderen Status. Wenn Sie z. B. nach &quot;uptime&quot;suchen, dann betrachten Sie Server nur im Produktionsmodus. Die Dimension &quot;Gruppe&quot;ist daher nur eine weitere Möglichkeit, Server beliebig nach Bedarf zu gruppieren. In der Konfigurationsdatei für die Überwachung können Sie beispielsweise festlegen, welchen Host Ihre Abteilung hat, z. B. Vorgänge, Entwicklung oder Marketing.
