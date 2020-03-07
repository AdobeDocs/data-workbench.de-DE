---
description: Integrieren von Data Workbench in Adobe Target Exportieren Sie Datensegmente und füllen Sie die Exportdateien automatisch aus.
solution: Analytics
title: Data Workbench-Integration mit Adobe Target
topic: Data workbench
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench-Integration mit Adobe Target

Die Integration von Adobe Data Workbench mit Adobe Target wurde durch Data Workbench-Funktionen zum Exportieren von Datensegmenten und automatischen Füllen von Exportdateien erleichtert.

Adobe Data Workbench ermöglicht die Integration in Adobe Target mit geschlossenen Schleifen zum Freigeben von Daten und Generieren von Berichten. In Data Workbench können Sie Populationen anhand aller verfügbaren Daten auf aussagekräftige Segmente analysieren, einschließlich Offline-Konversionen über Kanäle wie Telefon, Store usw.

Ein Besucher sucht beispielsweise nach Schuhen auf Ihrer Website, konvertiert diese jedoch nicht. Stattdessen lädt der Besucher einen Gutschein für 20 Prozent seines nächsten Kaufs herunter und kauft dann ein Hemd in Ihrem Geschäft. Mithilfe von Data Workbench können Sie diese Daten erfassen und diese Profildaten dann an Target zurücksenden, um anzuzeigen, dass der Besucher ein Hemd offline gekauft hat. Sie können dann eine Kampagne als Ziel auswählen, die diesem Besucher eine Krawatte anbietet, wenn Target normalerweise versuchen könnte, diesem Besucher Schuhe erneut zu vermarkten.

## Einrichten von Data Workbench mit Adobe Target

1. Klicken Sie mit der rechten Maustaste auf die Kopfzeile im [!UICONTROL Detail Table] Fenster.

   ![](assets/insight-to-tnt.png)

1. Wählen Sie **[!UICONTROL New Target Export]** und geben Sie den Namen einer neuen Exportdatei unter dem **[!UICONTROL Save As]** Befehl im Menü ein.

1. Klicken Sie auf **[!UICONTROL Save Export File]**.

   Daraufhin wird ein Fenster mit der Exportvorlage geöffnet.

   Alle Adobe Target-Informationen werden automatisch ausgefüllt. Die Parameterliste wird basierend auf den Angaben im Segmentexport erstellt. Nach Abschluss des Vorgangs sendet Data Workbench die Daten an den Adobe Target-Server.

   **Hinweis:** Die Vorlagendatei sollte vom [!UICONTROL Profile Architect]Operator konfiguriert werden. Die [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host]und [!UICONTROL Mbox Name] müssen eingegeben werden. Wenn Sie mehrere Sites haben, füllen Sie mehrere Vorlagen aus und speichern Sie sie auf dem Server. Die Vorlagen aus dem Profil-Manager befinden sich in `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Geben Sie den [!UICONTROL mboxPC] Abfrageparameter an.

   Wenn der Name des Data Workbench-Attributs etwas Anderes als [!UICONTROL mboxPC]ist, müssen Sie den entsprechenden Abfrageparameter bearbeiten und in _mboxPC_ umbenennen.

   ![](assets/insight-to-tnt2.png)

   Wenn Sie die Exportdatei auf dem Server speichern, beginnt der Export. Nach Abschluss des Vorgangs startet die [!UICONTROL TnTSend.exe] Anwendung und beginnt mit dem Senden der Daten an das Target-Konto.

## Data Workbench für Target konfigurieren

Führen Sie die folgenden Aufgaben in Adobe Target aus:

Data Workbench übergibt Benutzerprofile an Adobe Target. Um den Export in Target zu konfigurieren, müssen Sie die zugehörige API einrichten und aktivieren und die Parameter **[!UICONTROL clientname]** und Parameter für die Exportkonfigurationsdatei ( **[!UICONTROL domain postfix]**`export.cfg`) angeben.

Eine neue boolesche Option namens **[!UICONTROL Oneshot]** wurde zu Segmentexportdateien hinzugefügt. Diese Option ist in der mit dem neuen Profil verteilten Vorlagendatei enthalten. Wenn [!UICONTROL Oneshot] der Wert auf _true_ festgelegt ist, wird die `.export` `.export.done-TIMESTAMP` Datei nach Abschluss des Exports in umbenannt, um sicherzustellen, dass das Segment nie mehr als einmal exportiert wird. Dies ist beim Exportieren in Adobe Target wichtig.

**Hinweis:** Ein Aufruf von Data Workbench an Adobe Target zählt als [!UICONTROL mbox] Aufruf, der einen Aufruf für jedes gesendete Profil erfordert. Folglich steigen die Kosten, wenn zwischen den beiden Lösungen mehrere Aufrufe erforderlich sind.

Bei einer unvollständigen Konfiguration wird folgende Fehlermeldung im Protokoll ausgegeben:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Konfigurieren von Adobe Target für Data Workbench

Innerhalb von Adobe Target ist keine spezielle Konfiguration erforderlich, damit ein Kunde Profildaten senden kann. Die Profilinformationen für einen Benutzer werden in der Regel in der regulären [!UICONTROL mbox] Anforderung weitergeleitet, und die Server stellen die Profilparameter für eine zielgerichtete Kampagneneinrichtung als Standardfunktionalität ohne zusätzliche Einrichtung zur Verfügung.

In Adobe Target ist die Data Workbench-Integration integriert, die über die Seite &quot;Kundendetails für Super-Benutzer&quot;aktiviert werden kann. Durch Aktivierung dieser Option werden Segmente abgedeckt, die in Data Workbench in Adobe Target freigegeben werden, um sie für das Targeting verfügbar zu machen.

## HTTP-Protokollberichte in ExportIntegration.exe festlegen

Reduzieren Sie die lange Berichterstellung, [!UICONTROL HTTP.log] wenn Sie Adobe Target-Integrationsdateien exportieren [!UICONTROL ExportIntegration.exe] möchten.

Mit einer neuen [!UICONTROL httpLoggingEI.cfg] Konfigurationsdatei (unter `server\Admin\Export\httpLoggingEI.cfg`) können Sie die ausführliche Protokollierung in der [!UICONTROL HTTP.log] Datei reduzieren, wenn Sie Daten mit [!UICONTROL ExportIntegration.exe]exportieren. Auf diese Weise können Sie die ausführliche Anfrage-/Antwortprotokollierung stoppen.

Die Verbose-Protokollierung wird bereits in [!UICONTROL TnTSend.log] Dateien erfasst.

_True_ legt die ausführliche Protokollierung fest und _False_ stoppt die ausführliche Protokollierung der [!UICONTROL HTTP.log] Datei.

Bei der Einstellung &quot;False&quot;wird nur eine Warnmeldung an die [!UICONTROL HTTP.log] Datei gesendet (Infoinhalt wird nicht gesendet).