---
description: Sie können Berichte dynamisch für die Dimensionselemente generieren, die Sie in einer Lookup-Datei angeben, oder für eine bestimmte Anzahl von Dimensionselementen, z. B. für Benutzer mit der höchsten Reihenfolge von 10.
solution: Analytics
title: Dynamische Erstellung von Berichten
topic: Data workbench
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dynamische Erstellung von Berichten{#dynamically-generating-reports}

Sie können Berichte dynamisch für die Dimensionselemente generieren, die Sie in einer Lookup-Datei angeben, oder für eine bestimmte Anzahl von Dimensionselementen, z. B. für Benutzer mit der höchsten Reihenfolge von 10.

>[!NOTE]
>
>Adobe rät von der Erstellung dynamischer Berichtsätze für die tägliche (oder häufiger) Berichtgenerierung ab. Die dynamische Berichtgenerierung kann ressourcenintensiv sein, wenn Sie Berichte mit großen oder komplexen Abfragen konfigurieren.

* [Dimensionsberichte der Suchdatei](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Wichtigste Dimensionselementberichte](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Dimensionsberichte der Suchdatei {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Um einen Bericht zu konfigurieren, mit dem Berichte dynamisch generiert und (optional) für die Elemente einer in einer Abfragedatei angegebenen Dimension verteilt werden, geben Sie die folgenden Parameter in der [!DNL Report.cfg] Datei an:

* [!DNL Dimension Name]
* [!DNL Lookup File]

Ausführliche Beschreibungen dieser Parameter finden Sie unter [Report.cfg-Parameter](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**So erstellen Sie einen dynamischen Berichtsatz mithilfe einer Lookup-Datei**

1. Erstellen Sie eine zweispaltige Nachschlagedatei für eine bestimmte Dimension. Diese Datei muss zwei tabulatorgetrennte Spalten ohne Kopfzeile enthalten.

   * Spalte 1 sollte eine Liste der Dimensionselemente enthalten.
   * Spalte 2 sollte die E-Mail-Adressen der Berichtempfänger enthalten. Ein Bericht für ein bestimmtes Element in Spalte 1 wird an die E-Mail-Adresse(n) in derselben Zeile in Spalte 2 gesendet. Sie können mehrere E-Mail-Adressen eingeben, indem Sie sie durch Kommas (ohne Leerzeichen) trennen.

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Wenn Berichte nicht per E-Mail versandt werden sollen, kann Spalte 2 leer sein, muss aber vorhanden sein.
      >    * Diese Datei kann leere Zeilen enthalten.




1. Optional. Um die E-Mail-Versendung von Berichten zu aktivieren, müssen Sie im [!DNL Mail Report] Abschnitt der [!DNL Report.cfg] Datei für den jeweiligen Berichtssatz folgende Schritte ausführen:

   * Geben Sie im SMTP Server-Parameter den entsprechenden SMTP-Server an, der zum Verteilen von Berichten per E-Mail verwendet werden soll.
   * Geben Sie im Parameter Empfänger mindestens eine E-Mail-Adresse an, um die Verteilung der Berichte per E-Mail zu ermöglichen. Die Berichte werden nicht an die angegebene Adresse gesendet. Sie legen diesen Parameter nur so fest, dass die Berichte per E-Mail versandt werden können. Dies kann eine falsche Adresse sein, muss aber in einem zulässigen Format sein (z. B. [!DNL jsmith@company.com]).

1. Speichern Sie die Nachschlagedatei im Ordner des Berichtssatzes.
1. Öffnen Sie die [!DNL Report.cfg] Datei für den Berichtsatz.
1. Geben Sie im Parameter &quot;Dimensionsname&quot;den Namen der Dimension ein, für die Sie einen Bericht dynamisch erstellen möchten.
1. Geben Sie im Parameter &quot;Suchdatei&quot;den Speicherort und den Namen der Abfragedatei ein, die die Dimensionselemente enthält, die Sie im Bericht und die E-Mail-Adressen der Empfänger haben möchten.
1. Wiederholen Sie diese Schritte für weitere Berichtssätze.

>[!NOTE]
>
>Dynamische Berichte werden erst dann per E-Mail an Empfänger gesendet, wenn der gesamte Berichtssatz abgeschlossen ist.

## Wichtigste Dimensionselementberichte {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Geben Sie die folgenden Parameter in der [!DNL Report.cfg] Datei an, um einen Berichtssatz zu konfigurieren, mit dem Berichte für die Elemente der obersten Dimension dynamisch erstellt werden, wobei die angegebene Metrik berücksichtigt wird:

* Name der Dimension
* Top N-Metrik
* Top-N-Wert
* (Optional) Abfragefilter für Vorausladen

Ausführliche Beschreibungen dieser Parameter finden Sie unter [Report.cfg-Parameter](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**So erstellen Sie einen dynamischen Berichtsatz für die obersten Elemente**

1. Öffnen Sie die [!DNL Report.cfg] Datei des Berichtssatzes.
1. Geben Sie im Parameter &quot;Dimensionsname&quot;den Namen der Dimension ein, für die Sie einen Berichtssatz dynamisch erstellen möchten.
1. Geben Sie im Parameter Top N Metrik den Namen der Metrik ein, nach der die Dimension sortiert werden soll.
1. Geben Sie im Parameter Top-N-Wert die Anzahl der Dimensionselemente ein, die Sie in den Berichtsatz aufnehmen möchten.
1. (Optional) Geben Sie im Parameter &quot;Abfragefilter vorladen&quot;den Namen des gewünschten Filters ein.
1. Wiederholen Sie diese Schritte für weitere Berichtssätze.
1. Informationen zur Verwendung einer dynamischen Titelvisualisierung mit Ihrem Bericht finden Sie im *Data Workbench-Benutzerhandbuch*.

