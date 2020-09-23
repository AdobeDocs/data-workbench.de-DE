---
description: Die Testergebnisse müssen klar und aussagekräftig sein, damit Sie sich darauf verlassen können, auf der Grundlage dieser Ergebnisse große Dollarentscheidungen zu treffen.
solution: Analytics,Analytics
title: Was soll getestet werden?
topic: Data workbench
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---


# Was soll getestet werden?{#what-should-i-test}

Die Testergebnisse müssen klar und aussagekräftig sein, damit Sie sich darauf verlassen können, auf der Grundlage dieser Ergebnisse große Dollarentscheidungen zu treffen.

Obwohl Sie verschiedene Seitenlayouts mit [!DNL Sensor] und Site testen können, legt Adobe nahe, dass Sie sich auf das Testen von hochwertigen, strategischen Geschäftsinitiativen oder neuen oder neu gestalteten Website-Funktionen konzentrieren, die die Ziele, die Sie für Ihre Website und Ihr Unternehmen festgelegt haben, ansprechen. Sie können Tests auf beste Preisgarantien, Personalisierungsfunktionalität, Angebot auf dem Markt (z. B. Pakete oder Pakete), kreatives Design und Anwendungsprozesse durchführen.

Die folgenden Konzepte sind bei der Entwicklung Ihres kontrollierten Experiments besonders wichtig:

* **Machen Sie sich mit den richtigen Änderungen vertraut.** Dies erfordert einige Forschungsarbeiten darüber, wie Ihre Website funktioniert und welche Geschäftsprozesse der Front-End-Website zugrunde liegen. Sie möchten Änderungen vornehmen, die den größten Einfluss haben und problemlos getestet werden können.
* **Kleine Änderungen können erhebliche Auswirkungen haben.** Nicht alle Änderungen, die Sie testen, müssen drastisch sein, um erhebliche Auswirkungen auf Ihr Geschäft zu haben. Seien Sie immer offen für kleine, aber sehr wichtige Änderungen.

## Unterstützte Methoden {#section-1071adaf54c64ba9bc5ef228c4a23635}

Viele Arten von Experimenten mit vielen verschiedenen Zielen können mithilfe von Site durchgeführt werden. Die folgende Liste zeigt einige Beispiele:

* Ändern von Seiten-, Inhalts- und Website-Prozessen zur Verbesserung der Konversionsraten.
* Ändern von Marketing-Kampagnen, Promotions, Querverkäufen und Upsells, um den Umsatz zu steigern.
* Verschiedene Seitenladezeiten, um die Qualität des Kundenservice und den tatsächlichen Wert der Infrastrukturleistung zu verstehen.

Um diese Ziele zu erreichen, unterstützt Site die folgenden Methoden für kontrolliertes Experimentieren und Testen:

* **Seitenaustausch:** Ersetzen Sie die statische URL X durch die statische URL Y. Diese Methodik ist in einer dynamischen Umgebung nur begrenzt einsetzbar.
* **Dynamischer URI-Austausch:** Dies ist eine Variante des Seitenaustauschs, die die statische Seite X durch die dynamische Seite Y ersetzt, um dynamischen Inhalt zu rendern.
* **Objektaustausch:** Ersetzen Sie das feste Objekt X durch das feste Objekt Y.
* **Inhaltsersetzung:** Ersetzen Sie den Inhaltssatz X (mehrere Objekte, Seiten, Tabellen usw.) durch den Inhaltssatz Y.
* **Ersetzen von Experimentvariablen:** Ersetzen Sie das JavaScript-Objekt /writeCookie_X.js durch das JavaScript-Objekt /writeCookie_Y.js, um ein Cookie zu schreiben, das von einem Back-End-System zur Bereitstellung bestimmter Inhalte verwendet werden kann.

>[!NOTE]
>
>Kontrollierte Experimente basieren auf einem URI-Ersatz und nicht auf einem Abfrage-String-Ersatz. Der URI innerhalb einer bestimmten URL wird im folgenden Beispiel hervorgehoben:
>
>`http://www.omniture.com/index.asp?id=1`
>
>Beispielsweise können Sie in Ihrem kontrollierten Experiment angeben, dass der URI der Kontrollgruppe durch den URI der Testgruppe ersetzt [!DNL index.asp] werden soll, [!DNL index2.asp] um festzustellen, welcher Seitenentwurf zu mehr Wert führt.
