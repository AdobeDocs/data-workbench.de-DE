---
description: Die Testergebnisse müssen klar und aussagekräftig sein, damit Sie sich darauf verlassen können, auf der Grundlage dieser Ergebnisse große Dollarentscheidungen zu treffen.
solution: Analytics,Analytics
title: Was soll getestet werden?
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
exl-id: 0f06ff0f-b385-4614-8007-afdb85191a85
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# Was soll getestet werden?{#what-should-i-test}

Die Testergebnisse müssen klar und aussagekräftig sein, damit Sie sich darauf verlassen können, auf der Grundlage dieser Ergebnisse große Dollarentscheidungen zu treffen.

Obwohl Sie verschiedene Seitenlayouts mit [!DNL Sensor] und Site testen können, legt die Adobe nahe, dass Sie sich auf das Testen von hochwertigen, strategischen Geschäftsinitiativen oder auf neue oder neu gestaltete Website-Funktionen konzentrieren, die die Ziele, die Sie für Ihre Website und Ihr Unternehmen festgelegt haben, ansprechen. Sie können Tests auf beste Preisgarantien, Personalisierungsfunktionalität, Angebot auf dem Markt (z. B. Pakete oder Pakete), kreatives Design und Anwendungsprozesse durchführen.

Die folgenden Konzepte sind bei der Entwicklung Ihres kontrollierten Experiments besonders wichtig:

* **Machen Sie sich mit den richtigen Änderungen vertraut.** Dies erfordert einige Forschungsarbeiten darüber, wie Ihre Website funktioniert und welche Geschäftsprozesse der Front-End-Website zugrunde liegen. Sie möchten Änderungen vornehmen, die den größten Einfluss haben und problemlos getestet werden können.
* **Kleine Änderungen können erhebliche Auswirkungen haben.** Nicht alle Änderungen, die Sie testen, müssen drastisch sein, um erhebliche Auswirkungen auf Ihr Geschäft zu haben. Seien Sie immer offen für kleine, aber sehr wichtige Änderungen.

## Unterstützte Methoden {#section-1071adaf54c64ba9bc5ef228c4a23635}

Viele Arten von Experimenten mit vielen verschiedenen Zielen können mithilfe von Site durchgeführt werden. Die folgende Liste zeigt einige Beispiele:

* Ändern von Seiten-, Inhalts- und Website-Prozessen zur Verbesserung der Konversionsraten.
* Ändern von Marketing-Kampagnen, Promotions, Querverkäufen und Upsells, um den Umsatz zu steigern.
* Verschiedene Seitenladezeiten, um die Qualität des Kundenservice und den tatsächlichen Wert der Infrastrukturleistung zu verstehen.

Um diese Ziele zu erreichen, unterstützt Site die folgenden Methoden für kontrolliertes Experimentieren und Testen:

* **Seitenaustausch: statische URL X durch statische URL Y** ersetzen. Diese Methodik ist in einer dynamischen Umgebung nur begrenzt einsetzbar.
* **Dynamischer URI-Austausch:** Diese Variante des Seitenaustauschs ersetzt statische Seite X durch dynamische Seite Y, um dynamischen Inhalt zu rendern.
* **Objekt ersetzen: Festes Objekt X durch ein festes Objekt Y** ersetzen.
* **Inhaltsersetzung: Inhaltssatz X (mehrere Objekte, Seiten, Tabellen usw.) durch Inhaltssatz Y** ersetzen.
* **Ersetzen von Experimentvariablen:JavaScript-Objekt /writeCookie_X.js durch JavaScript-Objekt /writeCookie_Y.js** ersetzen, um ein Cookie zu schreiben, das von einem Back-End-System zur Bereitstellung bestimmter Inhalte verwendet werden kann.

>[!NOTE]
>
>Kontrollierte Experimente basieren auf einem URI-Ersatz und nicht auf einem Abfrage-String-Ersatz. Der URI innerhalb einer bestimmten URL wird im folgenden Beispiel hervorgehoben:
>
>`http://www.omniture.com/index.asp?id=1`
>
>Beispielsweise können Sie in Ihrem kontrollierten Experiment angeben, dass die Kontrollgruppen-URI [!DNL index.asp] durch die Testgruppe URI [!DNL index2.asp] ersetzt werden soll, um festzustellen, welcher Seitenentwurf zu mehr Wert führt.
