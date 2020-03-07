---
description: Die Verarbeitung von Protokolldateien als Protokollquellen erfordert die Definition eines Decoders in der Datei "Log Processing DataSet Include", um Datenfelder aus den Protokolleinträgen zu extrahieren.
solution: Analytics
title: Textdatei-Decoder-Gruppen
topic: Data workbench
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Textdatei-Decoder-Gruppen{#text-file-decoder-groups}

Die Verarbeitung von Protokolldateien als Protokollquellen erfordert die Definition eines Decoders in der Datei &quot;Log Processing DataSet Include&quot;, um Datenfelder aus den Protokolleinträgen zu extrahieren.

Die Definition von Textdatei-Decoder-Gruppen für Protokollquellen für Protokolldateien erfordert Kenntnisse über die Struktur und den Inhalt der Protokolldatei, die zu extrahierenden Daten und die Felder, in denen diese Daten gespeichert werden. Dieser Abschnitt enthält grundlegende Beschreibungen der Parameter, die Sie für Decoder angeben können. Die Art und Weise, wie Sie Decoder verwenden, hängt jedoch von der Protokolldatei ab, die Ihre Quelldaten enthält.

Informationen zu den Formatanforderungen für Protokollquellen für Protokolldateien finden Sie unter [Protokolldateien](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e). Wenden Sie sich an Adobe, um Hilfe beim Definieren von Textdatei-Decoder zu erhalten.

Eine Textdatei-Decoder-Gruppe kann Folgendes umfassen:

* [Reguläre Ausdrucksdekoren](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [Getrennte Decoders](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## Reguläre Ausdrucksdekoren {#section-67aca2c1f008404da7f845a64abec97c}

Ein Dekoder für reguläre Ausdrücke identifiziert komplexe Zeichenfolgenmuster in den Protokolleinträgen in einer Protokolldatei und extrahiert diese Muster als Datenfelder. Für jeden Decoder muss die Anzahl der Felder der Anzahl der erfassten Untermuster im regulären Ausdruck entsprechen. Der Teil der Linie, der dem n. erfassten Untermuster entspricht, wird dem n. Feld für diese Zeile zugewiesen.

**So fügen Sie einer Textdatei-Dekodierergruppe einen Dekoder für reguläre Ausdrücke hinzu**

1. Öffnen Sie die [!DNL Log Processing Dataset Include] Datei, wie unter [Bearbeiten vorhandener DataSet-Include-Dateien](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) beschrieben, und fügen Sie eine Textdatei-Decoder-Gruppe hinzu. Siehe Tabelleneintrag [Decoder Groups](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Decoders]** unter der neu erstellten Decoder-Gruppe und klicken Sie dann auf **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. Geben Sie die folgenden Informationen an:

   * **Felder:** Liste der Felder in der Protokolldatei. Wenn eines der hier definierten Felder an die Umwandlungsphase der Datensatzkonstruktion übergeben werden soll, müssen diese Felder im Parameter &quot;Felder&quot;einer der [!DNL Log Processing Dataset Include] Dateien für den Datensatz aufgeführt werden. Benutzerdefinierte Feldnamen müssen mit &quot;x-&quot;beginnen.

   * **Name:** Optionale Kennung für den Decoder.
   * **Regulärer Ausdruck:** Dient zum Extrahieren der gewünschten Felder aus jeder Zeile in der Datei.

1. Wiederholen Sie die Schritte 4 und 5 für alle anderen Decoder, die Sie der Gruppe hinzufügen möchten.
1. Um die [!DNL Log Processing Dataset Include] Datei zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte. Klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei Profilname der Name des Datensatzprofils oder des geerbten Profils ist, zu dem die Datensatzeinschlussdatei gehört.

Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

>[!NOTE]
>
>Eine bestimmte Protokolldatei kann mehrere Dekodierer für reguläre Ausdrücke enthalten. Die Reihenfolge, in der Sie die Decoder definieren, ist wichtig: Der erste Decoder, der einer Zeile in der Protokolldatei entspricht, ist der, der zum Dekodieren dieser Zeile verwendet wird.

In diesem Beispiel wird die Verwendung eines Decoders für reguläre Ausdrücke veranschaulicht, um Datenfelder aus einer tabulatorgetrennten Textdatei zu extrahieren. Sie können dasselbe Ergebnis erzielen, indem Sie einen durch Trennzeichen getrennten Decoder mit einem Tabulatortrennzeichen definieren.

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

Weitere Informationen zu Dekodierern für reguläre Ausdrücke, einschließlich Terminologie und Syntax, finden Sie unter [Reguläre Ausdrücke](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

## Getrennte Decoders {#section-7e0a23decdbc4c75ae750a42446997a6}

Ein mit Trennzeichen versehener Decoder dekodiert eine Protokolldatei, deren Felder durch ein einzelnes Zeichen getrennt sind. Die Anzahl der Felder muss der Anzahl der Spalten in der getrennten Datei entsprechen. Es müssen jedoch nicht alle Felder benannt werden. Wenn ein Feld leer gelassen wird, ist die Spalte weiterhin in der Protokolldatei erforderlich, der Decoder ignoriert sie jedoch.

**So fügen Sie einer Textdatei-Decoder-Gruppe einen mit Trennzeichen versehenen Decoder hinzu**

1. Öffnen Sie die [!DNL Log Processing Dataset Include] Datei, wie unter [Bearbeiten vorhandener DataSet-Include-Dateien](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) beschrieben, und fügen Sie eine Textdatei-Decoder-Gruppe hinzu. Siehe Tabelleneintrag [Decoder Groups](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Decoders]** unter der neu erstellten Decoder-Gruppe und klicken Sie dann auf **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. Geben Sie die folgenden Informationen an:

   * **Felder:** Liste der Felder in der Protokolldatei. Wenn eines der hier definierten Felder an die Umwandlungsphase der Datensatzkonstruktion übergeben werden soll, müssen diese Felder im Parameter &quot;Felder&quot;einer der [!DNL Log Processing Dataset Include] Dateien für den Datensatz aufgeführt werden. Benutzerdefinierte Feldnamen müssen mit &quot;x-&quot;beginnen.

   * **Trennzeichen:** Zeichen, das zum Trennen von Feldern in der Ausgabedatei verwendet wird.

1. Wiederholen Sie die Schritte 4 und 5 für alle anderen Decoder, die Sie der Gruppe hinzufügen möchten.
1. Um die [!DNL Log Processing Dataset Include] Datei zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

>[!NOTE]
>
>Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

In diesem Beispiel wird die Verwendung eines durch Trennzeichen getrennten Decoders zum Extrahieren von Datenfeldern aus einer kommagetrennten Textdatei mit Daten zu Filmen veranschaulicht.

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)

