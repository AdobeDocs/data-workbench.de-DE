---
description: Die Versionshinweise zu Data Workbench 6.1 umfassen neue Funktionen, Aktualisierungsanforderungen, Fehlerbehebungen und bekannte Probleme.
title: Versionshinweise zu Data Workbench 6.1
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
exl-id: ed37a00f-b4cd-428e-abb7-7c52d5cfd2f9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 2%

---

# Versionshinweise zu Data Workbench 6.1{#data-workbench-release-notes}

Die Versionshinweise zu Data Workbench 6.1 umfassen neue Funktionen, Aktualisierungsanforderungen, Fehlerbehebungen und bekannte Probleme.

## Neue Funktionen {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.1 umfasst die folgenden neuen Funktionen:

| Funktionen | Beschreibung |
|--- |--- |
| 64-Bit-Windows-Aktualisierung | Die Komponenten für Data Workbench-Server, Berichtsserver und Client werden so aktualisiert, dass sie nur auf 64-Bit-Windows-Betriebssystemen ausgeführt werden. |
| Tendenzauswertung | Durch die Bewertung Ihrer Zielgruppe können Sie die Kundenloyalität identifizieren und statistisch feststellen, wer wahrscheinlich einen Verkauf konvertiert oder mit einer Geschichte oder Kampagne interagiert. Die Tendenzauswertung umfasst jetzt diese Visualisierungen, um Modelle anzuzeigen und die sich ändernde Korrelation ausgewählter Metriken anzuzeigen.<ul><li>Der Modell-Viewer untersucht ein logistisches Regressionsmodell, das mit der Tendenzauswertung generiert wurde und die Koeffizienten der einzelnen Eingabevariablen (einschließlich des konstanten Begriffs) und deren statistischen Fehlerbereich anzeigt. </li><li>Diagramme für Steigerung und Gewinn werden verwendet, um die potenzielle Steigerung eines bewerteten Datenmodells zu bewerten.</li><li>Die Konfusionsmatrix gibt vier Zählungen anhand der Kombination aus &quot;Tatsächlich positiv&quot;(AP), &quot;Aktiv Negativ&quot;(AN), &quot;Vorhersage positiv&quot;(PP) und &quot;Vorhersage negativ&quot;(PN).</li> <li>Ab v6.1 haben Sie jetzt eine Option zum Speichern von Tendenzwerten, die auf zwei Typen basieren: Dimensionen oder Dimensionen und Metriken.</li><li>Sie können jetzt auf Strg-Alt klicken und Elemente per Drag-and-Drop in die Tendenzauswertung und den Cluster-Builder einfügen. Bisher mussten Sie Tabellenelemente aus der Tabelle in das Feld &quot;Elemente&quot;ziehen.</li></ul> |
| Data Workbench jetzt auf Chinesisch | Data Workbench unterstützt jetzt vereinfachtes Chinesisch für die Clientanwendung. Data Workbench unterstützt auch den Eingabemethoden-Editor (IME) als Sekundärtext-Eingabeprozess für internationale Sprachen. |
| Mathematische Funktionen | Sie können jetzt mathematische Funktionen zu Metriken, Mathematiktransformationen und Arbeitsblattzellen hinzufügen, um Datensätze weiter zu berechnen. |
| Hinweise zu Statistiken | Tabellen bieten jetzt einen Zusammenfassungs-Aufruf für Metrikspalten. Der Abruf kann Mittelwert, Standardabweichung, Mindest- und Höchstwerte, Varianz und Gesamtanzahl für die Spalte anzeigen. Sie kann bei jeder Auswahl und Bewertung berücksichtigt werden. |
| Korrelationsmatrix-Filter | Die Korrelationsmatrix wurde mit einem Binärfilter aktualisiert, damit Sie Werte für eine oder beide korrelierte Metriken einschränken können, sodass Sie Ihren Vergleich besser fokussieren können. Außerdem können Sie jetzt Dimension-Elemente aus einer Dimension-Tabelle hinzufügen, indem Sie auf Strg + Alt klicken und Elemente in die auszuwertende Matrix-Spalte oder -Zeile ziehen. |
| Fallout-Beschriftung in Trichtervisualisierung ausblenden | Wechsel zwischen dem Anzeigen und Ausblenden von Fallout-Beschriftungen in einer Trichtervisualisierung durch Rechtsklick auf den Titel und Auswahl von Fallout ausblenden . |

## Sortieren von Tabellenspalten{#sorting-table-columns}

Sortieren Sie die Tabellenspalten alphabetisch oder durch Ordinale.

Um die Auswahl der Dimensionen in einer Tabelle zu erleichtern, können Sie die erste Spalte alphabetisch oder durch Ordinalzeichen sortieren, indem Sie die Menüoption **[!UICONTROL Sort]** auswählen.

Das Zeichen # wird angezeigt, wenn eine Spalte nach Ordnern sortiert ist (Standardeinstellung).

**Sortieroption auswählen**

Um die Sortieroptionen zwischen Ordinal und Alphabet zu ändern, klicken Sie mit der rechten Maustaste und wählen Sie **[!UICONTROL Sort]** aus. Klicken Sie auf den Pfeil, um die Reihenfolge umzukehren.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>Sie können andere Spalten durch Klicken auf den Spaltennamen in einer Ordinalfolge sortieren.

## Fallout-Beschriftungen im Trichter ausblenden

Umschalten, um Fallout-Beschriftungen in einer Trichtervisualisierung zu öffnen.

Die Trichtervisualisierung identifiziert, wo ein Kunde eine Marketing-Kampagne abbricht oder von einem definierten Konversionspfad abweicht, während er mit Ihrer Website oder Ihrer kanalübergreifenden Kampagne interagiert. Die linke Seite der Trichtervisualisierung zeigt die Ergebnisse eines Besuchs oder Besuchern an, während die rechte Seite die &quot;Trichteranalyse&quot;für diejenigen anzeigt, die einen bestimmten Pfad verlassen.

![](assets/c_funnel_hide_fallout.png)

In einer **[!UICONTROL Funnel]** -Visualisierung können Sie mit der rechten Maustaste auf den Titel klicken und **[!UICONTROL Hide Fallout]** aus dem Menü auswählen, um die Fallout-Beschriftungen auszublenden.

## Bekannte Probleme {#section-ff2180c6871c413480e15fa915c253b9}

* Beim Import eines Arbeitsbereichs wird eine Fehlermeldung angezeigt, auch wenn der Import erfolgreich war.

   Problemumgehung: Klicken Sie auf OK , um den Fehler zu ignorieren. Der Arbeitsbereich wurde erfolgreich importiert.

**Vereinfachtes Chinesisch-Lokalisierungsproblem**

* Der Dialogfeldtitel und die Meldung, die nach dem Klicken auf &quot;Senden&quot;angezeigt werden, wenn das Ziel in der Visualisierung Scoring festgelegt wird, sind unlesbar.

   Problemumgehung: Keine.
* Bei Verwendung von Wortumbrüchen in der Arbeitsblatt-Visualisierung werden lokalisierte Wörter nicht richtig eingeschlossen. Der Zeichenfolge werden zusätzliche Junk-Zeichen hinzugefügt.

   Problemumgehung: Keines
* [!DNL Insight.exe] kann nicht gestartet werden, wenn der Installationsordner mit nicht englischen Zeichen benannt ist.

   Problemumgehung: Behalten Sie Standardnamen bei oder benennen Sie sie im Ordnerpfad nur mit englischen Zeichen um, um ausführbare Dateien zu starten.
