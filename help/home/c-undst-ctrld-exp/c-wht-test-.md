---
description: Die Testergebnisse müssen klar und aussagekräftig sein, damit Sie sich darauf verlassen können, auf der Grundlage dieser Ergebnisse große Dollarentscheidungen zu treffen.
solution: Insight,Analytics
title: Was soll ich testen?
topic: Data workbench
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# What Should I Test?{#what-should-i-test}

Die Testergebnisse müssen klar und aussagekräftig sein, damit Sie sich darauf verlassen können, auf der Grundlage dieser Ergebnisse große Dollarentscheidungen zu treffen.

Obwohl Sie verschiedene Seitenlayouts mit [!DNL Sensor] und Site testen können, empfiehlt Adobe, dass Sie sich auf das Testen von hochwertigen strategischen Geschäftsinitiativen oder auf neue oder neu entworfene Website-Funktionen konzentrieren, die die Ziele ansprechen, die Sie sowohl für Ihre Website als auch für Ihr Unternehmen festgelegt haben. Sie können Tests auf beste Preisgarantien, Personalisierungsfunktionalität, Marktangebote (z. B. Pakete oder Pakete), kreatives Design und Anwendungsprozesse durchführen.

Die folgenden Konzepte sind bei der Entwicklung Ihres kontrollierten Experiments besonders wichtig:

* **Machen Sie sich mit den richtigen Änderungen vertraut.** Dies erfordert einige Forschungsarbeiten darüber, wie Ihre Website funktioniert und welche Geschäftsprozesse der Front-End-Website zugrunde liegen. Sie möchten Änderungen vornehmen, die den größten Einfluss haben und problemlos getestet werden können.
* **Kleine Änderungen können erhebliche Auswirkungen haben.** Nicht alle Änderungen, die Sie testen, müssen drastisch sein, um erhebliche Auswirkungen auf Ihr Geschäft zu haben. Seien Sie immer offen für kleine, aber sehr wichtige Änderungen.

## Unterstützte Methoden {#section-1071adaf54c64ba9bc5ef228c4a23635}

Viele Arten von Experimenten mit vielen verschiedenen Zielen können mithilfe von Site durchgeführt werden. Die folgende Liste enthält einige Beispiele:

* Ändern von Seiten-, Inhalts- und Website-Prozessen zur Verbesserung der Konversionsraten.
* Ändern von Marketingkampagnen, Promotions, Querverkäufen und Upsells, um den Umsatz zu steigern.
* Verschiedene Seitenladezeiten, um die Qualität des Kundenservice und den tatsächlichen Wert der Infrastrukturleistung zu verstehen.

Um diese Ziele zu erreichen, unterstützt Site die folgenden Methoden für kontrolliertes Experimentieren und Testen:

* **Seitenaustausch:** Ersetzen Sie die statische URL X durch die statische URL Y. Diese Methodik ist in einem dynamischen Umfeld von begrenztem Nutzen.
* **Dynamischer URI-Austausch:** Dies ist eine Variante des Seitenaustauschs, die die statische Seite X durch die dynamische Seite Y ersetzt, um dynamischen Inhalt zu rendern.
* **Objektaustausch:** Ersetzen Sie das feste Objekt X durch das feste Objekt Y.
* **Inhaltsersetzung:** Ersetzen Sie den Inhaltssatz X (mehrere Objekte, Seiten, Tabellen usw.) durch den Inhaltssatz Y.
* **Ersetzen von Experimentvariablen:** Ersetzen Sie das JavaScript-Objekt /writeCookie_X.js durch das JavaScript-Objekt /writeCookie_Y.js, um ein Cookie zu schreiben, das von einem Back-End-System zur Bereitstellung bestimmter Inhalte verwendet werden kann.

>[!NOTE]
>
>Kontrollierte Experimente basieren auf dem URI-Ersatz, nicht auf dem Abfragezeichenfolgen-Ersatz. Der URI innerhalb einer bestimmten URL wird im folgenden Beispiel hervorgehoben:
>
>`http://www.omniture.com/index.asp?id=1`
>
>In Ihrem kontrollierten Experiment können Sie beispielsweise angeben, dass die URI der Kontrollgruppe durch den URI der Testgruppe ersetzt [!DNL index.asp] werden soll, [!DNL index2.asp] um festzustellen, welcher Seitenentwurf zu mehr Wert führt.
