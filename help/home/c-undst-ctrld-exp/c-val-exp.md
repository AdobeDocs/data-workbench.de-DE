---
description: Nachdem Sie das Experiment bereitgestellt haben, sollten Sie überprüfen, ob das Experiment ordnungsgemäß funktioniert.
solution: Analytics,Analytics
title: Validieren des Experiments
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# Validieren des Experiments{#validating-the-experiment}

Nachdem Sie das Experiment bereitgestellt haben, sollten Sie überprüfen, ob das Experiment ordnungsgemäß funktioniert.

Wie unter [Ändern des ExpCookieURL-Parameters (Optional)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) beschrieben, kann die im Parameter ExpCookieURL in der Konfigurationsdatei [!DNL Sensor] angegebene Seite verwendet werden, um sich in einer bestimmten Experimentgruppe zu platzieren.

Die virtuelle Standardseite ist [!DNL /setcookie.htm], Sie müssen jedoch den Wert verwenden, den Sie im Parameter ExpCookieURL festgelegt haben.

## Anfordern der Testseite {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Um eine bestimmte Experimentgruppe für Ihre Website zu testen, muss Ihr Browser so konfiguriert sein, dass Cookies akzeptiert werden, und Sie dürfen für diese Website kein Cookie verwenden.

Achten Sie bei jedem Test einer neuen Gruppe darauf, die Cookies für die Website zu löschen.

Um sich in einer bestimmten Gruppe innerhalb eines bestimmten Experiments zu platzieren, fordern Sie die Testseite mit einer Abfrage-Zeichenfolge in folgendem Formular an:

[!DNL http://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

Beispiel:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Wenn die virtuelle URL-Anforderung an den Server gesendet wird, identifiziert [!DNL Sensor] Sie innerhalb des angegebenen Experiments als Mitglied der angegebenen Gruppe und leitet Sie dann zum Stammordner der Website weiter. Sie können nun zum entsprechenden Speicherort auf der Website navigieren, um zu überprüfen, ob der richtige Inhalt für dieses Experiment und diese Gruppe angezeigt wird.

Wenn Sie Folgendes in Ihren Browser eingeben, zeigt der Browser die Startseite der Website an und platziert Sie im Experiment &quot;New_Homepage&quot;in die Gruppe &quot;index2&quot;:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Wenn Besucher der Gruppe &quot;index2&quot;die Startseite anfordern, wird der grafische Link &quot;Anforderung einer Demo&quot;höher auf der Seite angezeigt, wie in der folgenden Grafik:

![](assets/TestPage.png)
