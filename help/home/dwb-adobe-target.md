---
description: Data Workbench mit Adobe Target integrieren. Exportieren Sie Datensegmente und füllen Sie die Exportdateien automatisch aus.
title: Zusammenarbeit zwischen Data Workbench und Adobe Target
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Zusammenarbeit zwischen Data Workbench und Adobe Target

Die Integration der Adobe-Data Workbench mit Adobe Target wurde durch Funktionen zur Data Workbench von Datensegmenten und zum automatischen Ausfüllen von Exportdateien erleichtert.

Adobe Data Workbench bietet eine Closed-Loop-Integration mit Adobe Target, um Daten freizugeben und Berichte zu erstellen. Innerhalb der Data Workbench können Sie Populationen anhand aller verfügbaren Daten auf aussagekräftige Segmente analysieren, einschließlich Offline-Konversionen über Kanal wie Telefon, Store usw.

Ein Besucher sucht beispielsweise nach Schuhen auf Ihrer Website, konvertiert diese jedoch nicht. Stattdessen lädt der Besucher einen Gutschein für 20 Prozent seines nächsten Kaufs herunter und kauft dann ein Hemd in Ihrem Geschäft. Mithilfe der Data Workbench können Sie diese Daten erfassen und dann die Daten des Profils zurück in die Zielgruppe verschieben, um zu zeigen, dass der Besucher ein Hemd offline gekauft hat. Sie können dann eine Kampagne, die diesem Besucher eine Krawatte anbietet, Zielgruppe geben, wenn Zielgruppe normalerweise versuchen könnte, Schuhe an diesen Besucher zu vermarkten.

## Einrichten der Data Workbench mit Adobe Target

1. Klicken Sie mit der rechten Maustaste auf die Kopfzeile im Fenster [!UICONTROL Detail Table].

   ![](assets/insight-to-tnt.png)

1. Wählen Sie **[!UICONTROL New Target Export]** und geben Sie den Namen einer neuen Exportdatei unter dem Befehl **[!UICONTROL Save As]** im Menü ein.

1. Klicken Sie auf **[!UICONTROL Save Export File]**.

   Daraufhin wird ein Fenster mit der Exportvorlage geöffnet.

   Alle Adobe Target-Informationen werden automatisch ausgefüllt. Es erstellt die Parameter-Liste basierend auf dem, was Sie im Segmentexport angegeben haben. Nach Abschluss der Data Workbench werden die Daten an den Adobe Target-Server gesendet.

   **Hinweis:** Die Vorlagendatei sollte vom  [!UICONTROL Profile Architect]Operator konfiguriert werden. Die Variablen [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host] und [!UICONTROL Mbox Name] müssen eingegeben werden. Wenn Sie mehrere Sites haben, füllen Sie mehrere Vorlagen aus und speichern Sie sie auf dem Server. Die Vorlagen aus dem Profil-Manager befinden sich unter `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Geben Sie den Parameter [!UICONTROL mboxPC] Abfrage an.

   Wenn der Name des Attributs &quot;Data Workbench&quot;etwas Anderes als [!UICONTROL mboxPC] ist, müssen Sie den entsprechenden Abfrage-Parameter bearbeiten und in _mboxPC_ umbenennen.

   ![](assets/insight-to-tnt2.png)

   Wenn Sie die Exportdatei auf dem Server speichern, beginnt der Export. Nach Abschluss des Vorgangs wird der Antrag gestartet und beginnt mit dem Senden der Daten an das Zielgruppen-Konto.[!UICONTROL TnTSend.exe]

## Data Workbench für Zielgruppe konfigurieren

Führen Sie die folgenden Aufgaben in Adobe Target aus:

Data Workbench übergibt Profil an Adobe Target. Um den Export in die Zielgruppe zu konfigurieren, müssen Sie die zugehörige API einrichten und aktivieren und die Parameter **[!UICONTROL clientname]** und **[!UICONTROL domain postfix]** für die Exportkonfigurationsdatei (`export.cfg`) angeben.

Eine neue boolesche Option mit dem Namen **[!UICONTROL Oneshot]** wurde Segmentexportdateien hinzugefügt. Diese Option ist in der mit dem neuen Profil verteilten Vorlagendatei enthalten. Wenn [!UICONTROL Oneshot] auf _true_ eingestellt ist, wird die `.export`-Datei nach Abschluss des Exports in `.export.done-TIMESTAMP` umbenannt, um sicherzustellen, dass das Segment nie mehr als einmal exportiert wird. Dies ist beim Export nach Adobe Target wichtig.

**Hinweis:** Ein Anruf von der Data Workbench nach Adobe Target zählt als  [!UICONTROL mbox] Anruf und erfordert einen Aufruf für jedes gesendete Profil. Folglich steigen die Kosten, wenn zwischen den beiden Lösungen mehrere Aufrufe erforderlich sind.

Bei einer unvollständigen Konfiguration wird folgende Fehlermeldung im Protokoll ausgegeben:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Adobe Target für Data Workbench konfigurieren

Innerhalb von Adobe Target ist keine spezielle Konfiguration erforderlich, damit ein Kunde Profil-Daten senden kann. Die Benutzerinformationen werden in der Regel in der regulären [!UICONTROL mbox]-Anforderung weitergegeben. Die Server stellen die Profil-Parameter für eine zielgerichtete Kampagne-Einrichtung als Standardfunktion ohne zusätzliche Einstellungen zur Verfügung.

Adobe Target verfügt über eine integrierte Data Workbench-Integration, die über die Seite mit den Kundendetails des Super-Benutzers aktiviert werden kann. Wenn Sie diese Option aktivieren, werden Segmente überdeckt, die von der Data Workbench innerhalb von Adobe Target freigegeben werden, um sie für das Targeting verfügbar zu machen.

## HTTP-Protokoll-Berichte in ExportIntegration.exe festlegen

Verringern Sie den Berichte auf [!UICONTROL HTTP.log], wenn Sie [!UICONTROL ExportIntegration.exe] verwenden, um Adobe Target-Integrationsdateien zu exportieren.

Mit einer neuen Konfigurationsdatei (die sich unter `server\Admin\Export\httpLoggingEI.cfg` befindet) können Sie die ausführliche Protokollierung der [!UICONTROL HTTP.log]-Datei beim Exportieren von Daten mit [!UICONTROL ExportIntegration.exe] reduzieren. [!UICONTROL httpLoggingEI.cfg] Auf diese Weise können Sie die ausführliche Anfrage-/Antwortprotokollierung stoppen.

Die Verbose-Protokollierung wird bereits in [!UICONTROL TnTSend.log]-Dateien erfasst.

_Die_ Truesets bieten ausführliche Protokollierung und  __ Falsestopps ausführliche Protokollierung in  [!UICONTROL HTTP.log] Dateien.

Bei der Einstellung &quot;False&quot;wird nur eine Warnmeldung an die Datei [!UICONTROL HTTP.log] gesendet (Infoinhalt wird nicht gesendet).
