---
description: Die Verarbeitung von Protokolldateien als Protokollquellen erfordert die Definition eines Decoders in der Datensatzaufnahme-Datei zur Protokollverarbeitung, um Datenfelder aus den Protokolleinträgen zu extrahieren.
title: Textdatei-Decoder-Gruppen
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
exl-id: e9f6e02e-7150-455f-96f0-f34d98cc31b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Textdatei-Decoder-Gruppen{#text-file-decoder-groups}

{{eol}}

Die Verarbeitung von Protokolldateien als Protokollquellen erfordert die Definition eines Decoders in der Datensatzaufnahme-Datei zur Protokollverarbeitung, um Datenfelder aus den Protokolleinträgen zu extrahieren.

Die Definition von Textdatei-Decoder-Gruppen für Protokolldateiquellen erfordert Kenntnisse über die Struktur und den Inhalt der Protokolldatei, die zu extrahierenden Daten und die Felder, in denen diese Daten gespeichert werden. Dieser Abschnitt enthält grundlegende Beschreibungen der Parameter, die Sie für Decoder angeben können. Die Art und Weise, in der Sie Decoder verwenden, hängt jedoch von der Protokolldatei ab, die Ihre Quelldaten enthält.

Informationen zu den Formatanforderungen für Protokollquellen für Protokolldateien finden Sie unter [Protokolldateien](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e). Wenden Sie sich zur Unterstützung bei der Definition von Textdatei-Decodern an die Adobe.

Eine Textdatei-Decoder-Gruppe kann Folgendes umfassen:

* [Decoder für reguläre Ausdrücke](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [Getrennte Decoders](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## Decoder für reguläre Ausdrücke {#section-67aca2c1f008404da7f845a64abec97c}

Ein Decoder für reguläre Ausdrücke identifiziert komplexe Zeichenfolgenmuster in den Protokolleinträgen in einer Protokolldatei und extrahiert diese Muster als Datenfelder. Die Anzahl der Felder muss für jeden Decoder der Anzahl der erfassten Untermuster im regulären Ausdruck entsprechen. Der Teil der Zeile, der mit dem n. erfassten Untermuster übereinstimmt, wird dem n. Feld für diese Zeile zugewiesen.

**So fügen Sie einen Decoder für reguläre Ausdrücke zu einer Textdatei-Decoder-Gruppe hinzu**

1. Öffnen Sie die [!DNL Log Processing Dataset Include] Datei wie unter [Bearbeiten vorhandener Datensatzaufnahme-Dateien](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) und fügen Sie eine Textdatei-Decoder-Gruppe hinzu. Siehe Tabelleneintrag [Decoder-Gruppen](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Rechtsklick **[!UICONTROL Decoders]** Klicken Sie unter der neu erstellten Decoder-Gruppe auf **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. Geben Sie die folgenden Informationen an:

   * **Felder:** Liste der Felder in der Protokolldatei. Wenn eines der hier definierten Felder an die Umwandlungsphase der Datensatzerstellung übergeben werden soll, müssen diese Felder im Parameter Felder eines der [!DNL Log Processing Dataset Include] -Dateien für den Datensatz. Benutzerdefinierte Feldnamen müssen mit &quot;x-&quot;beginnen.

   * **Name:** Optionale Kennung für den Decoder.
   * **Regulärer Ausdruck:** Wird verwendet, um die gewünschten Felder aus jeder Zeile in der Datei zu extrahieren.

1. Wiederholen Sie die Schritte 4 und 5 für alle anderen Decoder, die Sie zur Gruppe hinzufügen möchten.
1. So speichern Sie die [!DNL Log Processing Dataset Include] Datei, Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, finden Sie im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] Spalte. Klicken **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme-Datei gehört.

Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

>[!NOTE]
>
>Eine Protokolldatei kann mehrere Decoder für reguläre Ausdrücke enthalten. Die Reihenfolge, in der Sie die Decoder definieren, ist wichtig: Der erste Decoder, der einer Zeile in der Protokolldatei entspricht, ist derjenige, der zum Dekodieren dieser Zeile verwendet wird.

Dieses Beispiel zeigt die Verwendung eines Decoders für reguläre Ausdrücke, um Datenfelder aus einer tabulatorgetrennten Textdatei zu extrahieren. Sie können dasselbe Ergebnis erzielen, indem Sie einen durch Trennzeichen getrennten Decoder mit einem Tabulatortrennzeichen definieren.

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

Weitere Informationen zu Decodern für reguläre Ausdrücke, einschließlich Terminologie und Syntax, finden Sie unter [Reguläre Ausdrücke](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

## Getrennte Decoders {#section-7e0a23decdbc4c75ae750a42446997a6}

Ein mit Trennzeichen versehener Decoder dekodiert eine Protokolldatei, deren Felder durch ein einzelnes Zeichen getrennt sind. Die Anzahl der Felder muss der Anzahl der Spalten in der durch Trennzeichen getrennten Datei entsprechen. Es müssen jedoch nicht alle Felder benannt werden. Wenn ein Feld leer gelassen wird, ist die Spalte weiterhin in der Protokolldatei erforderlich, aber der Decoder ignoriert sie.

**So fügen Sie einen durch Trennzeichen getrennten Decoder zu einer Textdatei-Decoder-Gruppe hinzu**

1. Öffnen Sie die [!DNL Log Processing Dataset Include] Datei wie unter [Bearbeiten vorhandener Datensatzaufnahme-Dateien](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) und fügen Sie eine Textdatei-Decoder-Gruppe hinzu. Siehe Tabelleneintrag [Decoder-Gruppen](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Rechtsklick **[!UICONTROL Decoders]** Klicken Sie unter der neu erstellten Decoder-Gruppe auf **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. Geben Sie die folgenden Informationen an:

   * **Felder:** Liste der Felder in der Protokolldatei. Wenn eines der hier definierten Felder an die Umwandlungsphase der Datensatzerstellung übergeben werden soll, müssen diese Felder im Parameter Felder eines der [!DNL Log Processing Dataset Include] -Dateien für den Datensatz. Benutzerdefinierte Feldnamen müssen mit &quot;x-&quot;beginnen.

   * **Trennzeichen:** Zeichen, das zum Trennen von Feldern in der Ausgabedatei verwendet wird.

1. Wiederholen Sie die Schritte 4 und 5 für alle anderen Decoder, die Sie zur Gruppe hinzufügen möchten.
1. So speichern Sie die [!DNL Log Processing Dataset Include] Datei, Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, finden Sie im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme-Datei gehört.

>[!NOTE]
>
>Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

Dieses Beispiel zeigt die Verwendung eines durch Trennzeichen getrennten Decoders zum Extrahieren von Datenfeldern aus einer kommagetrennten Textdatei mit Daten zu Filmen.

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)
