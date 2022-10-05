---
description: In diesem Abschnitt werden die verschiedenen Typen von Dimensionen und deren Einrichtung in DWB erläutert.
title: Einrichten von Dimensionen
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
exl-id: 04afd773-e938-49f7-83c9-1d706a6dc525
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 4%

---

# Einrichten von Dimensionen{#dimension-setup}

{{eol}}

In diesem Abschnitt werden die verschiedenen Typen von Dimensionen und deren Einrichtung in DWB erläutert.

## Was sind Dimensionen? {#section-dac631943df24706827cedc6f0641543}

Auf der grundlegendsten Ebene sind Dimensionen Kategorien, in die die Daten im Datensatz unterteilt werden können.

Best Practice: Dimensionen im Datenschema können beliebig benannt werden. Die in diesem Kurs verwendeten und erklärten Dimensionen gelten als Best Practice. Dimensionen können unterschiedlich benannt werden. Wenn Sie Informationen zu anderen Datensätzen erhalten, werden Sie Unterschiede in Datensätzen erkennen. Es ist wichtig, den Zweck der Dimensionen und nicht ihren Namen zu verstehen. Ob es beispielsweise &quot;Besucher&quot;, &quot;Kunde&quot;, &quot;Person&quot;, &quot;Verbraucher&quot;oder &quot;Benutzer&quot;heißt, es ist wichtig zu verstehen, dass diese Begriffe häufig verwendet werden, um auf die zählbare Dimension der höchsten Ebene zu verweisen, mit der Informationen über eine bestimmte Person erfasst werden.

Vollständige Informationen finden Sie in der [Datensatzkonfiguration](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html) Handbuch.

## Typen von Dimensionen in DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

Es gibt zwei Arten von Dimensionen in der Data Workbench: Erweiterte Dimensionen und abgeleitete Dimensionen.

Erweiterte Dimensionen werden aus Feldern in den &quot;Rohdatendateien&quot;erstellt. Erweiterte Dimensionen werden verwendet, um &quot;Rohdaten&quot;zu kategorisieren und die Beziehungen anzugeben, die zwischen den Daten bestehen. Erweiterte Dimensionen werden von Data Workbench Architects erstellt.

Abgeleitete Dimensionen werden von einem Benutzer &quot;clientseitig&quot;erstellt, nachdem der Datensatz mit vorhandenen erweiterten Dimensionsdefinitionen verarbeitet wurde. Basierend auf der vorhandenen URI-Dimension kann ein Benutzer beispielsweise eine abgeleitete Dimension &quot;Seitenname&quot;erstellen, die anstelle eines angegebenen URI einen benutzerfreundlicheren Seitennamen anzeigt. Alle Dimensionen bestehen aus Elementen oder Elementen, die zur Bildung der Dimension kategorisiert (gruppiert) wurden. Im Folgenden finden Sie drei Dimensionen und ihre Elemente.

Viele abgeleitete Dimensionen werden automatisch erstellt, um verschiedene Visualisierungen zu ermöglichen. Wenn ein Benutzer beispielsweise eine Site oder eine Prozesskarte erstellt, erstellen DWB-Server eine Präfixdimension. Andere Dimensionen, wie zum Beispiel die in Berichten aufgeführten Zeitdimensionen, werden durch Dateien im Dimensionsverzeichnis eines Profils definiert.

>[!NOTE]
>
>Die Elemente, die in einer bestimmten Dimension angezeigt werden, spiegeln nur die Werte wider, die in Datensätzen vorhanden sind, die für das Laden in den Datensatz ausgewählt wurden. Wenn beispielsweise keine Daten für &quot;12. Mai&quot;vorhanden sind, wird dieser Monat nicht in der Dimension &quot;Monat&quot;angezeigt.

## Erweiterte Dimensionen {#section-5fc51fa539034941a30a2df606f7d727}

Typen von erweiterten Dimensionen

**1) Zählbare Dimensionen**

Auf der höchsten Ebene sind zählbare Dimensionen. Zählbare Dimensionen bieten zwei Hauptfunktionen. Zunächst handelt es sich um Dimensionen, deren Elemente Sie zählen möchten. Mit anderen Worten: Zählungen beantworten Fragen wie:

* &quot;Wie viele Besucher haben Ihre Homepage besucht?&quot;
* &quot;Wie viele Besuche hat google.com durchgeführt?&quot;

Aus diesem Grund werden zählbare Elemente häufig als grundlegende Bausteine für die Erstellung von Metriken verwendet.

Die zweite wichtige Funktion von zählbaren Elementen besteht darin, dass sie das Rückgrat Ihrer Datensatzschemastruktur bilden. Ihr Datenschema und alle anderen Dimensionen sind so organisiert, dass sie unter einer Zählung gruppiert werden und zu dieser gehören. Mit anderen Worten, wenn wir Dimensionen als &quot;Kategorien&quot;betrachten, dann sind Zählungen die Art und Weise, wie wir diese &quot;Kategorien&quot;in Gruppen organisieren.

Wenn Dimensionen unter einer zählbaren Dimension gruppiert werden, befinden sie sich auf der &quot;Ebene&quot;der zählbaren Dimension. Beispielsweise kann sich die &quot;E-Mail-Adresse&quot;auf Besucherebene und die &quot;Browser&quot;auf Besuchsebene befinden. &quot;Übergeordnetes Element&quot;und &quot;untergeordnetes Element&quot;beziehen sich auf die Beziehung zwischen der zählbaren Tabelle und den darunter gruppierten Dimensionen. Beispielsweise ist Besucher ein &quot;übergeordnetes&quot;Element der E-Mail-Adresse. Umgekehrt ist die E-Mail-Adresse ein &quot;untergeordnetes Element&quot;des Besuchers.

**2) Einfache Dimensionen**

Die gängigsten Dimensionen sind einfache Dimensionen. Einfache Dimensionen haben eine Eins-zu-viele-Beziehung mit einer übergeordneten zählbaren Dimension und werden häufig bei Visualisierungen verwendet, damit Sie ihre Elemente anzeigen können. Das bedeutet, dass eine zählbare Dimension einen Wert für eine einfache Dimension haben kann, die einfache Dimension jedoch zu einer oder mehreren zählbaren Werten gehören kann. Beispielsweise hat ein Kunde den Namen &quot;John&quot;- dieser Kunde kann nur einen Vornamen haben, viele andere Kunden können jedoch den Namen &quot;John;&quot;haben. Als weiteres Beispiel kann nur ein Browser (z. B. Firefox) für jeden bestimmten Besuch einer Website verwendet werden, dieser Browser kann jedoch für viele verschiedene Besuche verwendet werden.

Wenn zählbare Dimensionen auf &quot;Wie viele?&quot;antworten, antworten einfache Dimensionen auf &quot;Welche?&quot;. Verwenden Sie dasselbe oben im Abschnitt zählbare Dimension verwendete Beispiel: Seitenname ist die einfache Dimension. Mithilfe der Tabelle und der einfachen Dimension &quot;Seitenname&quot;können wir Fragen beantworten, z. B.:

* &quot;Welche Seite hatte die meisten Seitenansichten?&quot;
* &quot;Von allen Einkaufswagenseiten, die die meisten Besuche hatten?&quot;

**3) Viele-zu-viele-Dimensionen**

Viele-zu-viele-Dimensionen haben eine Viele-zu-viele-Beziehung mit einer übergeordneten zählbaren Dimension. Wenn sich beispielsweise eine Dimension mit dem Namen &quot;Externer Suchbegriff&quot;auf Besuchsebene befindet; kann ein bestimmter externer Suchbegriff bei einem oder mehreren Besuchen verwendet werden und ein bestimmter Besuch kann einen oder mehrere externe Suchbegriffe umfassen. Der externe Suchbegriff ist daher eine Viele-zu-viele-Dimension.

**4) Numerische Dimensionen**

Numerische Dimensionen sind ein Typ einer einfachen Dimension mit einem numerischen Wert. Numerische Dimensionen werden häufig erstellt, um in Metriken verwendet zu werden. Beispiele für numerische Dimensionen sind &quot;Umsatz&quot;, &quot;Bestellungen&quot;und &quot;Einheiten&quot;. Im obigen Beispiel ist die Dimension &quot;Kundenaufträge&quot;eine numerische Dimension.
**5) Denormale Dimensionen** Denormale Dimensionen sind Dimensionen, die eine Eins-zu-Eins-Beziehung mit einer übergeordneten zählbaren Dimension aufweisen. Denormale Dimensionen werden häufig mit Dimensionen mit hoher Kardinalität (viele eindeutige Elemente) wie Identifizierungsdaten verwendet. Beispielsweise kann ein Besucher nur eine Benutzer-ID und eine Benutzer-ID nur zu einem Besucher gehören. Dies ist also eine Eins-zu-Eins-Beziehung und kann eine denormale Dimension sein.

Beispielsweise ist die Geometrixx Web User ID eine denormale Dimension auf Kundenebene. Da es sich um eine denormale Dimension handelt, besteht eine Eins-zu-Eins-Beziehung mit der übergeordneten Dimension, d. h. jede Web-Anwender-ID hat einen Kunden und jeder Kunde nur eine Web-Benutzer-ID. Daher kann die Metrik &quot;Kunden&quot;nur für jedes Element der Geometrixx Web-Benutzer-ID &quot;1&quot;lauten.

**6) Dimensionen**

Mit Zeitdimensionen können Sie einen Satz periodischer oder absoluter lokaler Zeitdimensionen erstellen, die auf dem von Ihnen angegebenen Zeitstempelfeld basieren. Beispiele für Zeitdimensionen sind &quot;Tag&quot;, &quot;Stunde&quot;, &quot;Woche&quot;und &quot;Stunde des Tages&quot;. Im obigen Beispiel zeigt die Tabelle &quot;Stunde des Tages&quot;an, wie viele Besuche und Seitenansichten während der verschiedenen Stunden der Tage empfangen wurden.

>[!NOTE]
>
>Die für die Anzeigeformatierung verwendeten Escape-Zeichen in % entsprechen der standardmäßigen C-Bibliothek. *strftime*.

## Definieren erweiterter Dimensionen {#section-38ee124ec74b43fb95f13194a9582b97}

Schritte zum Definieren der erweiterten Dimension:

1. Öffnen Sie während der Arbeit mit Ihrem Datensatzprofil den Profil-Manager und klicken Sie auf Datensatz , um dessen Inhalt anzuzeigen.
1. Öffnen Sie die Datei &quot;Transformation.cfg&quot;oder die Datei &quot;Transformation-Datensatz einschließen&quot;, in der Sie die erweiterte Dimension definieren möchten.
1. Klicken Sie mit der rechten Maustaste auf Umwandlungen und klicken Sie auf Neu hinzufügen > `<Extended dimension type>`.
1. Geben Sie die entsprechenden Informationen für Ihre erweiterte Dimension ein. Beschreibungen der Umwandlungstypen und Informationen zu ihren Parametern finden Sie in den folgenden Abschnitten:

   * [Zählbare Dimensionen](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Einfache Dimensionen](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Viele-zu-viele-Dimensionen](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Numerische Dimensionen](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Denormale Dimensionen](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Zeitdimensionen](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. Für jede erweiterte Dimension, die Sie definieren, können Sie dem Kommentar-Parameter eine oder mehrere Kommentarzeilen hinzufügen, um die Dimension weiter zu beschreiben oder Anmerkungen zur Verwendung hinzuzufügen. Um einen Kommentar hinzuzufügen, klicken Sie mit der rechten Maustaste auf die *Kommentare* und klicken Sie auf &quot;Neu hinzufügen&quot;> &quot;Kommentarzeile&quot;.

1. Nachdem Sie Ihre erweiterte Dimension(en) in der Konfigurationsdatei definiert haben, speichern Sie die Datei lokal und speichern Sie sie in Ihrem Datensatzprofil auf dem DWB-Server.

## Ausblenden erweiterter Dimensionen {#section-02339fb51658418eabc10186cd5957d7}

Erweiterte Dimensionen können ausgeblendet werden, sodass sie nicht im Menü &quot;Dimension&quot;im DWB angezeigt werden. Um die Dimension auszublenden, setzen Sie die Eigenschaft &quot;Ausgeblendet&quot;in der Dimensionsdefinition auf &quot;True&quot;.
