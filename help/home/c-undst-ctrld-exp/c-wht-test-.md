---
description: Die Testergebnisse müssen klar und aussagekräftig sein, damit Sie sich darauf verlassen können, auf der Grundlage dieser Ergebnisse große Dollarentscheidungen zu treffen.
solution: Analytics,Analytics
title: Was soll getestet werden?
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
exl-id: 0f06ff0f-b385-4614-8007-afdb85191a85
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# Was soll getestet werden?{#what-should-i-test}

Die Testergebnisse müssen klar und aussagekräftig sein, damit Sie sich darauf verlassen können, auf der Grundlage dieser Ergebnisse große Dollarentscheidungen zu treffen.

Obwohl Sie verschiedene Seitenlayouts mit [!DNL Sensor] und Site testen können, legt Adobe nahe, dass Sie sich auf das Testen von hochwertigen, strategischen Geschäftsinitiativen oder neuen oder neu gestalteten Website-Funktionen konzentrieren, die die Ziele ansprechen, die Sie für Ihre Website sowie für Ihr Unternehmen festgelegt haben. Sie können Probleme wie beste Preisgarantien, Personalisierungsfunktionalität, Marktangebote (z. B. Pakete oder Bundles), kreatives Design und Anwendungsprozesse testen.

Die folgenden Konzepte sind bei der Entwicklung Ihres kontrollierten Experiments am wichtigsten:

* **Machen Sie sich mit den richtigen Änderungen vertraut.** Dies erfordert einige Untersuchungen zur Funktionsweise Ihrer Website und zu den Geschäftsprozessen, die der Frontend-Website zugrunde liegen. Sie möchten Änderungen vornehmen, die die größte Auswirkung bieten und einfach getestet werden können.
* **Kleine Änderungen können erhebliche Auswirkungen haben.** Nicht alle Änderungen, die Sie testen, müssen drastisch sein, damit sie sich erheblich auf Ihr Unternehmen auswirken. Seien Sie immer offen für kleine, aber sehr wichtige Änderungen.

## Unterstützte Methoden {#section-1071adaf54c64ba9bc5ef228c4a23635}

Mit Site können viele Arten von Experimenten mit vielen verschiedenen Zielen durchgeführt werden. Die folgende Liste enthält einige Beispiele:

* Ändern von Seiten-, Inhalts- und Website-Prozessen zur Verbesserung der Konversionsraten.
* Änderung von Marketing-Kampagnen, Promotions, Querverkäufen und Up-Sells zur Umsatzsteigerung.
* Unterschiedliche Seitenladezeiten, um die Qualität des Kundendienstes und den tatsächlichen Wert der Infrastrukturleistung zu verstehen.

Um diese Ziele zu erreichen, unterstützt Site die folgenden Arten von Methoden für kontrollierte Experimentierungs- und Tests:

* **Seitenersetzung:**  Ersetzen Sie die statische URL X durch die statische URL Y. Diese Methode ist in einer dynamischen Umgebung von begrenzter Bedeutung.
* **Dynamische URI-Ersetzung:** Dies ist eine Variante des Seitenaustauschs, die die statische Seite X durch die dynamische Seite Y ersetzt, um dynamischen Inhalt zu rendern.
* **Objektersetzung:**  Ersetzen Sie das feste Objekt X durch das feste Objekt Y.
* **Inhaltsersetzung:** Ersetzen Sie den Inhaltssatz X (mehrere Objekte, Seiten, Tabellen usw.) durch den Inhaltssatz Y.
* **Ersetzen von Experimentvariablen:**  Ersetzen Sie das JavaScript-Objekt /writeCookie_X.js durch das JavaScript-Objekt /writeCookie_Y.js , um ein Cookie zu schreiben, das von einem Back-End-System zur Bereitstellung bestimmter Inhalte verwendet werden kann.

>[!NOTE]
>
>Kontrollierte Experimente basieren auf der URI-Ersetzung, nicht auf der Ersetzung der Abfragezeichenfolge. Der URI innerhalb einer bestimmten URL wird im folgenden Beispiel hervorgehoben:
>
>`http://www.omniture.com/index.asp?id=1`
>
>Beispielsweise können Sie in Ihrem kontrollierten Experiment festlegen, dass der Kontrollgruppen-URI [!DNL index.asp] durch den Testgruppen-URI [!DNL index2.asp] ersetzt wird, um zu bestimmen, welcher Seitenentwurf zu mehr Wert führt.
