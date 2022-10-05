---
description: Data Workbench unterstützt jetzt den Eingabemethoden-Editor (IME) als Sekundärtext-Eingabeprozess für internationale Sprachen.
title: Installieren des Eingabemethoden-Editors
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# Installieren des Eingabemethoden-Editors{#installing-the-input-method-editor}

{{eol}}

Data Workbench unterstützt jetzt den Eingabemethoden-Editor (IME) als Sekundärtext-Eingabeprozess für internationale Sprachen.

Mit IMEs können Sie internationale Zeichen mithilfe einer Vielzahl von Methoden eingeben, die für Ihre Landessprache geeignet sind. Data Workbench bietet ein Dialogfeld für die Eingabe, in dem Sie Ihren gewünschten IME für Textfelder öffnen und verwenden können.

>[!NOTE]
>
>Für die Data Workbench-Version 6.1 wird nur die virtuelle vereinfachte chinesische Tastatur unterstützt. Die Eingabe anderer Sprachen über den IME könnte zu unerwartetem Verhalten führen.

## IME verwenden {#section-5f008d75a7b24119ab6aebc55454f927}

So verwenden Sie die unverankerte IME-Texteingabe-Funktion:

1. Klicken **[!UICONTROL Alt + Space]** für jeden Texteingabefeld.
1. Geben Sie Werte mithilfe des IME Ihres Systems ein.
1. Schließen Sie das Dialogfeld, indem Sie die **[!UICONTROL Enter]** oder klicken Sie auf **[!UICONTROL OK]** Schaltfläche.

   Das Dialogfeld wird ausgeblendet und die Zeichen werden dann im ausgewählten Feld angezeigt.

**Aktualisieren der Datei Insight.cfg**

Um den IME zu verwenden, müssen Sie die [!DNL Insight.cfg] Datei mit dieser Einstellung:

```
Localized IME = bool: true
```

Wenn diese Einstellung nicht in der Konfigurationsdatei vorhanden ist, drücken Sie **[!UICONTROL Alt + Space]** wird nicht mit der IME-Funktion interagieren.

**Starten von Insight in einer anderen Sprache:** Um lokalisierte Assets wie einen Begrüßungsbildschirm besser zu unterstützen und in Zukunft mehrere Sprachen zu unterstützen, erfordert Data Workbench Befehlszeilenargumente, mit denen die zu ladende Sprache identifiziert wird. Die Standardsprache ist Englisch.

Zum Starten von Data Workbench auf Chinesisch müssen Sie aufrufen [!DNL Insight.exe] mit dem Argument &quot;-zh-cn&quot;:

```
Insight.exe -zh-cn
```

(Bei diesen Befehlszeilenargumenten wird nicht zwischen Groß- und Kleinschreibung unterschieden.)
