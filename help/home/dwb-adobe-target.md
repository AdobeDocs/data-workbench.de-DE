---
description: Integrieren der Data Workbench mit Adobe Target. Exportieren Sie Datensegmente und füllen Sie Exportdateien automatisch.
title: Zusammenarbeit zwischen Data Workbench und Adobe Target
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Zusammenarbeit zwischen Data Workbench und Adobe Target

Die Integration der Adobe-Data Workbench mit Adobe Target wurde durch Data Workbench-Funktionen zum Exportieren von Datensegmenten und automatischen Ausfüllen von Exportdateien vereinfacht.

Adobe Data Workbench bietet Closed-Loop-Integration mit Adobe Target für die gemeinsame Nutzung von Daten und die Erstellung von Berichten. Innerhalb der Data Workbench können Sie Populationen anhand aller verfügbaren Daten auf aussagekräftige Segmente analysieren, einschließlich Offline-Konversionen über Kanäle wie Telefon, Geschäft usw.

Beispiel: Ein Besucher sucht auf Ihrer Website nach Schuhen, konvertiert diese jedoch nicht. Stattdessen lädt der Besucher einen Gutschein zu 20 Prozent von seinem nächsten Kauf herunter und kauft dann ein Hemd in Ihrem Geschäft. Mithilfe von Data Workbench können Sie diese Daten erfassen und diese Profildaten dann zurück an Target senden, um anzuzeigen, dass der Besucher ein Hemd offline gekauft hat. Sie können dann eine Kampagne auswählen, die diesem Besucher eine Krawatte anbietet, wenn Target normalerweise versuchen könnte, diesem Besucher Schuhe erneut zu vermarkten.

## Einrichten der Data Workbench mit Adobe Target

1. Klicken Sie mit der rechten Maustaste auf die Kopfzeile im Fenster [!UICONTROL Detail Table] .

   ![](assets/insight-to-tnt.png)

1. Wählen Sie **[!UICONTROL New Target Export]** aus und geben Sie den Namen einer neuen Exportdatei unter dem Befehl **[!UICONTROL Save As]** im Menü ein.

1. Klicken Sie auf **[!UICONTROL Save Export File]**.

   Daraufhin wird ein Fenster mit einer Exportvorlage geöffnet.

   Alle Adobe Target-Informationen werden automatisch ausgefüllt. Sie erstellt die Parameterliste auf Grundlage des Inhalts des Segmentexports. Nach Abschluss des Vorgangs sendet Data Workbench die Daten an den Adobe Target-Server.

   **Hinweis:** Die Vorlagendatei sollte vom  [!UICONTROL Profile Architect]konfiguriert werden. Die Variablen [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host] und [!UICONTROL Mbox Name] müssen angegeben werden. Wenn Sie mehrere Sites haben, füllen Sie mehrere Vorlagen aus und speichern Sie sie auf dem Server. Die Vorlagen aus dem Profil-Manager befinden sich unter `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Geben Sie den Abfrageparameter [!UICONTROL mboxPC] an.

   Wenn der Name des Data Workbench-Attributs etwas Anderes als [!UICONTROL mboxPC] ist, müssen Sie den entsprechenden Abfrageparameter bearbeiten und ihn in _mboxPC_ umbenennen.

   ![](assets/insight-to-tnt2.png)

   Wenn Sie die Exportdatei auf dem Server speichern, beginnt der Export. Nach Abschluss des Vorgangs startet die Anwendung [!UICONTROL TnTSend.exe] und beginnt mit dem Senden von Daten an das Target-Konto.

## Konfigurieren der Data Workbench für Target

Führen Sie die folgenden Aufgaben in Adobe Target aus:

Data Workbench leitet Benutzerprofile an Adobe Target weiter. Um den Export in Target zu konfigurieren, müssen Sie die zugehörige API einrichten und aktivieren und die Parameter **[!UICONTROL clientname]** und **[!UICONTROL domain postfix]** für die Exportkonfigurationsdatei (`export.cfg`) angeben.

Eine neue boolesche Option namens **[!UICONTROL Oneshot]** wurde zu Segmentexportdateien hinzugefügt. Diese Option ist in der mit dem neuen Profil verteilten Vorlagendatei enthalten. Wenn [!UICONTROL Oneshot] auf _true_ gesetzt ist, wird die `.export`-Datei nach Abschluss des Exports in `.export.done-TIMESTAMP` umbenannt, um sicherzustellen, dass das Segment nie mehr als einmal exportiert wird. Dies ist beim Export in Adobe Target wichtig.

**Hinweis:** Ein Aufruf von Data Workbench an Adobe Target zählt als  [!UICONTROL mbox] Aufruf, sodass für jedes gesendete Profil ein Aufruf erforderlich ist. Folglich steigen die Kosten, wenn zwischen den beiden Lösungen mehrere Aufrufe erforderlich sind.

Bei einer unvollständigen Konfiguration wird die folgende Fehlermeldung im Protokoll ausgegeben:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Adobe Target für Data Workbench konfigurieren

In Adobe Target ist keine spezielle Konfiguration erforderlich, damit ein Kunde Profildaten senden kann. Die Profilinformationen für einen Benutzer werden in der Regel in der regulären [!UICONTROL mbox]-Anfrage übergeben. Die Server stellen die Profilparameter für eine zielgerichtete Kampagneneinrichtung als Standardfunktionalität zur Verfügung, ohne dass eine zusätzliche Einrichtung erforderlich ist.

Adobe Target verfügt über eine integrierte Data Workbench-Integration, die über die Seite &quot;Kundendetails für Superuser&quot;aktiviert werden kann. Durch Aktivierung der Option werden Segmente überdeckt, die von Data Workbench in Adobe Target freigegeben werden, um sie für das Targeting verfügbar zu machen.

## Festlegen von HTTP-Protokollberichten in ExportIntegration.exe

Reduzieren Sie die lange Berichterstellung auf [!UICONTROL HTTP.log], wenn Sie [!UICONTROL ExportIntegration.exe] zum Exportieren von Adobe Target-Integrationsdateien verwenden.

Mit einer neuen Konfigurationsdatei [!UICONTROL httpLoggingEI.cfg] (unter `server\Admin\Export\httpLoggingEI.cfg`) können Sie die ausführliche Protokollierung für den Datenexport mit [!UICONTROL ExportIntegration.exe] auf die Datei [!UICONTROL HTTP.log] reduzieren. Auf diese Weise können Sie die ausführliche Anfrage-/Antwortprotokollierung stoppen.

Die ausführliche Protokollierung wird bereits in [!UICONTROL TnTSend.log]-Dateien erfasst.

__ Die ausführliche Protokollierung in Truesets und  __ die ausführliche Protokollierung in  [!UICONTROL HTTP.log] Datei wird von Falsestopps unterbunden.

In der Einstellung False wird nur eine Warnmeldung an die Datei [!UICONTROL HTTP.log] gesendet (Info-Inhalt wird nicht gesendet).
