---
description: In diesem Abschnitt wird das Skript Saint Scrubber erläutert.
title: Skripten für die SAINT-Navigationsleiste
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Skripten für die SAINT-Navigationsleiste{#scripting-for-the-saint-scrubber}

In diesem Abschnitt wird das Skript Saint Scrubber erläutert.

## Überblick über die SAINT-Klassifizierung {#section-b840a99f10684bb4b58e844a515d0d79}

Klassifizierung wird auch durch das Akronym SAINT für das SiteCatalyst Attributimport- und Namensgebungs-Tool bezeichnet.

Wenn wir eine SiteCatalyst-Variable &quot;klassifizieren&quot;, erstellen Sie eine Beziehung zwischen einer Variablen und Metadaten, die sich auf diese Variable beziehen. Klassifizierungen werden am häufigsten im Kampagnenbereich verwendet, damit ich sie anhand dieser Informationen erklären kann. Die meisten Kunden senden Kampagnen-Traffic mit einem Rückverfolgungscode an ihre Site. Dieser Rückverfolgungscode ist ein Bezeichner, der einen bestimmten Suchbegriff repräsentieren kann, der bei Google gekauft wurde, z. B. &quot;goog123&quot;. Dieser Bezeichner wird an die Variable s.campaigns übergeben, damit Sie sehen können, welche Site-Erfolgsereignisse stattfinden, nachdem Besucher über diesen Kampagnencode zu Ihrer Site gelangt sind.

Was aber, wenn Sie anstelle der Anzeige von Kampagnen nur nach dem Rückverfolgungscode die Kampagnenergebnisse nach Suchmaschine, Suchbegriff oder Kampagnenkanal anzeigen möchten? Müssen Sie eine neue Konversionsvariable für die Suchmaschine, eine andere für den Suchbegriff und eine weitere für den Kampagnenkanal erstellen? Wenn ja, würden Sie viele Ihrer 50 Variablen allein in Kampagnen verwenden! Zum Glück können Sie Klassifizierungen verwenden, um Ihr Leben zu erleichtern! Da jeder Rückverfolgungscode über eine Suchmaschine, einen Suchbegriff oder einen Kampagnenkanal verfügen könnte, können Sie einfach drei Klassifizierungen der Kampagnenvariablen erstellen, um jede zu repräsentieren. Sie teilen SiteCatalyst im Wesentlichen mit, dass eine direkte Beziehung zwischen der Kampagnenvariablen und diesen drei anderen &quot;Metadaten&quot;-Werten besteht. Auf diese Weise ermöglicht SiteCatalyst es Ihnen, die Site-Erfolgsereignisse ohne zusätzliches Tagging nach allen vier Variablen zu zerteilen und zu würfeln.

## SAINT-Scrubber-Skript in DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Dieses Skript wird verwendet, wenn Sie SAINT-Klassifizierungsdaten in DWB eintragen. Das Skript *SaintScrubber.dat* wird normalerweise im Ordner *\Scripts\Scripository* auf der FSU abgelegt.

Der Hauptzweck dieses Skripts ist es, die Kopfzeile in den `<discoiqbr>` SAINT-Klassifizierungsdateien zu entfernen. Außerdem wird die Zahl gezählt, wenn die in der Spaltenüberschrift erwähnte Spalte alle Datenzeilen überprüft. Wenn es Zeilen mit weniger oder mehr Spalten gibt, werden diese Zeilen aus der Datei entfernt.

Die Datei *SaintScrubber.dat* ruft intern das *saint_scautschuk.pl *script auf. Im Folgenden finden Sie die Details zu dieser Skriptdatei:

Pfad: *E:\Scripts\Scripository\Library\Perl*

Skriptargumente:

1. Eingabeordner (Obligatorisch): source_directory
1. Ausgabeordner (obligatorisch): destination_directory
1. Trennzeichen (obligatorisch): trennzeichen
1. Ablehnungsordner (optional)(Parameter kann leer gelassen oder in der Befehlszeile weggelassen werden)
1. Protokollordner (optional)(Parameter kann leer gelassen oder in der Befehlszeile weggelassen werden)

Schritte, die im Perl-Skript ausgeführt werden:

1. Ersetzen Sie Escaped-Formularfeeds, Zeilenumbrüche, Wagenrückgaben und Tabulatoren durch Leerzeichen.
1. Entfernen Sie die doppelten Bytes, die als Steuerzeichen in der UTF-8 BMP (einfache mehrsprachige Ebene) interpretiert werden, mit Ausnahme von:

   * 9 horizontale Registerkarte
   * 10-zeiliger Feed
   * 12 Formular-Feed
   * 13 Wagenrücklauf
   * Verwenden Sie das senkrechte Schlüsselwort als Trennzeichen für| z. B.: Trennzeichenrohr
   * Entfernen Sie andere problematische Zeichen
   * Nach dem obigen Scrubbing können Sie Zeilen mit einer Anzahl von Spalten ablegen, die von der ersten Datenzeile abweichen (nicht leer oder Kommentar)
   * Unterstützen Sie optionale Ablehnungsdateien, um abgelehnte Zeilen zu halten, anstatt sie einfach zu überspringen.
   * Unterstützung rekursiver Eingabeordner; Ausgabeordner derselben Struktur erstellen
   * Versetzen der verarbeiteten Eingabedateien in die verarbeiteten Unterordner, damit das Skript den Vorgang nicht wiederholt, wenn er erneut auf demselben vorhandenen Eingabeordner ausgeführt wird
   * Erkennen des Datums in den Workbench-Dateinamen; Sortieren Sie die Verarbeitung zuerst nach Datum und dann nach Alpha - unabhängig vom Ordnernamen. Dadurch wird sichergestellt, dass die Sequenz korrekt ist, unabhängig vom Workbench-Dateityp (ecom, non-ecom) oder der Report Suite-ID (wenn Sie mehrere Report Suites in einem einzigen Insight-Datensatz verarbeiten).
   * Support-E-Mail-Benachrichtigungen `<discoiqbr>`

