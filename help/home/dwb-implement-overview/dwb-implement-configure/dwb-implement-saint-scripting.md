---
description: In diesem Abschnitt wird das Skript Saint Scrubber erläutert.
title: Skripterstellung für den SAINT-Scrubber
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
exl-id: 5f6d92b1-baaa-4d67-a1c2-ce7d51affb17
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 1%

---

# Skripterstellung für den SAINT-Scrubber{#scripting-for-the-saint-scrubber}

{{eol}}

In diesem Abschnitt wird das Skript Saint Scrubber erläutert.

## Übersicht über die SAINT-Klassifizierung {#section-b840a99f10684bb4b58e844a515d0d79}

Die Klassifizierung wird auch vom Akronym-SAINT für das SiteCatalyst-Attribut-Import- und Namensgebungs-Tool bekannt.

Wenn wir eine SiteCatalyst-Variable &quot;klassifizieren&quot;, stellen Sie eine Beziehung zwischen einer Variablen und Metadaten her, die mit dieser Variablen verbunden sind. Klassifizierungen werden am häufigsten im Kampagnenbereich verwendet, sodass ich sie anhand dieser Informationen erklären werde. Die meisten Kunden senden Kampagnen-Traffic mithilfe eines Trackingcodes an ihre Site. Dieser Trackingcode ist eine Kennung, die einen bestimmten, auf Google erworbenen Suchbegriff repräsentieren kann, z. B. &quot;goog123&quot;. Diese Kennung wird an die Variable s.campaigns übergeben, damit Sie sehen können, welche Site-Erfolgsereignisse stattfinden, nachdem Besucher aus diesem Kampagnencode auf Ihre Site gelangt sind.

Was ist jedoch, wenn Sie anstelle der Anzeige von Kampagnen nur anhand des Trackingcodes die Kampagnenergebnisse nach Suchmaschine, Keyword oder Kampagnenkanal sehen möchten? Müssen Sie eine neue Konversionsvariable für die Suchmaschine erstellen, eine andere für den Suchbegriff und eine andere für den Kampagnenkanal? Wenn ja, würden Sie viele Ihrer 50 Variablen allein in Kampagnen verwenden! Glücklicherweise können Sie Classifications verwenden, um Ihr Leben zu vereinfachen! Da jeder Trackingcode über eine Suchmaschine, einen Suchbegriff oder einen Kampagnenkanal verfügen kann, können Sie einfach drei Classifications der Kampagnenvariablen erstellen, die jeweils dargestellt werden. Sie teilen SiteCatalyst im Wesentlichen mit, dass eine direkte Beziehung zwischen der Kampagnenvariablen und diesen drei anderen &quot;Meta-Daten&quot;-Werten besteht. Auf diese Weise können Sie mit SiteCatalyst die Erfolgsereignisse der Site ohne zusätzliches Tagging nach allen vier Variablen sortieren und würfeln.

## SAINT Scrubber-Skript in DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Dieses Skript wird verwendet, wenn Sie SAINT Classification-Daten in DWB einbringen. Das Skript *SaintScrubber.dat* wird normalerweise unter der *\Scripts\Scripository* auf der FSU.

Der Hauptzweck dieses Skripts besteht darin, die -Kopfzeile im `<discoiqbr>` SAINT Classification-Dateien. Außerdem wird die Zahl gezählt, wenn die in der Spaltenüberschriftszeile erwähnte Spalte alle Datenzeilen überprüft. Wenn Zeilen mit einer geringeren oder mehr Spalten vorhanden sind, werden diese Zeilen aus der Datei entfernt.

Die *SaintScrubber.dat* intern ruft das Skript *saint_scautschuk.pl *auf. Im Folgenden finden Sie die Details für diese Skriptdatei:

Pfad: *E:\Scripts\Scripository\Library\Perl*

Skriptargumente:

1. Eingabeordner (erforderlich): source_directory
1. Ausgabeordner (erforderlich) : destination_directory
1. Trennzeichen (erforderlich) : delimiter
1. Ordner zurückweisen (optional)(Parameter können leer gelassen oder in der Befehlszeile weggelassen werden)
1. Protokollordner (optional)(Parameter können leer gelassen oder in der Befehlszeile weggelassen werden)

Schritte, die im Perl-Skript ausgeführt werden:

1. Ersetzen Sie maskierte Formular-Feeds, Zeilenumbrüche, Zeilenumbrüche, Tabs mit Leerzeichen.
1. Entfernen Sie die doppelten Bytes, die als Steuerzeichen im UTF-8-BMP (Basic Multilingual Plane) interpretiert werden, mit Ausnahme von:

   * 9 horizontale Registerkarte
   * 10 Zeilenvorschub
   * 12 Formular-Feed
   * 13 Wagenrücklauf
   * Verwenden Sie das senkrechte Keyword als Trennzeichen für | z. B.: Trennzeichen-Rohr
   * Entfernen Sie andere problematische Zeichen
   * Legen Sie nach dem obigen Scrubbing alle Zeilen mit einer Anzahl von Spalten ab, die von der ersten Datenzeile abweichen (nicht leer oder kommentieren)
   * Unterstützung optionaler Zurückweisungsdateien für zurückgewiesene Zeilen, anstatt sie einfach zu überspringen
   * Unterstützung rekursiver Eingabeordner; Ausgabeordner derselben Struktur generieren
   * Verschieben Sie verarbeitete Eingabedateien in verarbeitete Unterordner, sodass das Skript den Vorgang nicht wiederholt, wenn er erneut im selben vorhandenen Eingabeordner ausgeführt wird.
   * Erkennen des Datums in Workbench-Dateinamen; Sortieren Sie die Verarbeitung zuerst nach Datum und dann nach Alpha - unabhängig vom Ordnernamen. Dadurch wird sichergestellt, dass die Sequenz unabhängig vom Workbench-Dateityp (ecom, non-ecom) oder der Report Suite-ID korrekt ist (wenn Sie mehrere Report Suites in einem einzelnen Insight-Datensatz verarbeiten).
   * Support-E-Mail-Warnungen `<discoiqbr>`
