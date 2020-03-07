---
description: Data Workbench unterstützt jetzt den Eingabemethoden-Editor (IME) als sekundären Texteingabeprozess für internationale Sprachen.
solution: Analytics
title: Installieren des Eingabemethoden-Editors
topic: Data workbench
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installieren des Eingabemethoden-Editors{#installing-the-input-method-editor}

Data Workbench unterstützt jetzt den Eingabemethoden-Editor (IME) als sekundären Texteingabeprozess für internationale Sprachen.

Mit IMEs können Sie internationale Zeichen mit einer Vielzahl von Methoden eingeben, die für Ihre Landessprache geeignet sind. Data Workbench bietet ein Eingabedokument, mit dem Sie den gewünschten IME für Textfelder öffnen und verwenden können.

>[!NOTE]
>
>Für die Version Data Workbench 6.1 wird nur die virtuelle vereinfachte chinesische Tastatur unterstützt. Die Eingabe anderer Sprachen über den IME kann zu unerwartetem Verhalten führen.

## Verwenden eines IME {#section-5f008d75a7b24119ab6aebc55454f927}

So verwenden Sie die schwebende IME-Texteingabefunktion:

1. Klicken Sie **[!UICONTROL Alt + Space]** für einen beliebigen Texteingabebereich.
1. Geben Sie Werte mit dem IME Ihres Systems ein.
1. Schließen Sie das Eingabedokument, indem Sie die **[!UICONTROL Enter]** Taste markieren oder auf die **[!UICONTROL OK]** Schaltfläche klicken.

   Das Dialogfeld wird ausgeblendet und die Zeichen werden dann im ausgewählten Feld angezeigt.

**Aktualisieren der Datei Insight.cfg**

Um den IME verwenden zu können, müssen Sie die [!DNL Insight.cfg] Datei mit der folgenden Einstellung aktualisieren:

```
Localized IME = bool: true
```

Wenn diese Einstellung nicht in der Konfigurationsdatei vorhanden ist, wird die IME-Funktion durch Drücken der Taste nicht aktiviert **[!UICONTROL Alt + Space]** .

**Starten von Insight in einer anderen Sprache:** Um lokalisierte Assets wie einen Begrüßungsbildschirm besser zu unterstützen und in Zukunft mehrere Sprachen zu unterstützen, erfordert Data Workbench Befehlszeilenargumente, die die zu ladende Sprache identifizieren. Die Standardsprache ist Englisch.

Zum Starten von Data Workbench auf Chinesisch müssen Sie [!DNL Insight.exe] mit dem Argument &quot;-zh-cn&quot;aufrufen:

```
Insight.exe -zh-cn
```

(Bei diesen Befehlszeilenargumenten wird nicht zwischen Groß- und Kleinschreibung unterschieden.)
