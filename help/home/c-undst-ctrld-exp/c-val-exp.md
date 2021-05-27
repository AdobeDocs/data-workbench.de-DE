---
description: Nachdem Sie Ihr Experiment bereitgestellt haben, sollten Sie überprüfen, ob das Experiment ordnungsgemäß funktioniert.
solution: Analytics,Analytics
title: Validieren des Experiments
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# Validieren des Experiments{#validating-the-experiment}

Nachdem Sie Ihr Experiment bereitgestellt haben, sollten Sie überprüfen, ob das Experiment ordnungsgemäß funktioniert.

Wie unter [Bearbeiten des ExpCookieURL-Parameters (optional)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) beschrieben, kann die im Parameter ExpCookieURL in der Konfigurationsdatei [!DNL Sensor] angegebene Seite verwendet werden, um sich in einer bestimmten Experimentgruppe zu platzieren.

Die standardmäßige virtuelle Seite ist [!DNL /setcookie.htm], Sie müssen jedoch den Wert verwenden, den Sie im Parameter ExpCookieURL festgelegt haben.

## Anfordern der Testseite {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Um eine bestimmte Experimentgruppe für Ihre Website zu testen, muss Ihr Browser so konfiguriert sein, dass er Cookies akzeptiert, und Sie dürfen für diese Website kein Cookie haben.

Jedes Mal, wenn Sie eine neue Gruppe testen möchten, müssen Sie die Cookies für die Website löschen.

Um sich in einer bestimmten Gruppe innerhalb eines bestimmten Experiments zu platzieren, fordern Sie die Testseite mit einer Abfragezeichenfolge im folgenden Formular an:

[!DNL http://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

Beispiel:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Wenn die virtuelle URL-Anforderung an den Server gesendet wird, identifiziert [!DNL Sensor] Sie innerhalb des angegebenen Experiments als Mitglied der angegebenen Gruppe und leitet Sie dann zum Stammverzeichnis der Website weiter. Sie können jetzt zur entsprechenden Stelle auf der Website navigieren, um zu überprüfen, ob der richtige Inhalt für dieses Experiment und diese Gruppe angezeigt wird.

Wenn Sie Folgendes in Ihren Browser eingeben würden, würde der Browser die Startseite der Website anzeigen und Sie in die Gruppe index2 innerhalb des Experiments New_Homepage einfügen:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Wenn Besucher der Gruppe index2 die Startseite anfordern, wird der grafische Link &quot;Demo anfordern&quot;höher auf der Seite angezeigt, wie in der folgenden Abbildung dargestellt:

![](assets/TestPage.png)
