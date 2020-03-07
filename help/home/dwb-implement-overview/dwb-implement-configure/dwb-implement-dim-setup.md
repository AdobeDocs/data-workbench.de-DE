---
description: In diesem Abschnitt werden die verschiedenen Arten von Dimensionen und ihre Einrichtung in DWB erläutert.
title: Dimensionseinstellungen
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Dimensionseinstellungen{#dimension-setup}

In diesem Abschnitt werden die verschiedenen Arten von Dimensionen und ihre Einrichtung in DWB erläutert.

## Dimensionen {#section-dac631943df24706827cedc6f0641543}

Auf der grundlegendsten Ebene sind Dimensionen Kategorien, in die die Daten im Datensatz unterteilt werden können.

Best Practice: Dimensionen im Datenschema können mit jedem beliebigen Namen versehen werden. Dimensionsnamen, die in diesem Kurs verwendet und erläutert werden, gelten als Best Practice. Dimensionen können unterschiedlich benannt werden. Mit zunehmender Exposition gegenüber anderen Datensätzen werden Sie beginnen, Unterschiede in den Datensätzen zu erkennen. Es ist wichtig, den Zweck der Dimensionen und nicht ihren Namen zu verstehen. Es ist wichtig zu verstehen, dass es sich bei den Begriffen &quot;Besucher&quot;, &quot;Kunde&quot;, &quot;Person&quot;, &quot;Verbraucher&quot;oder &quot;Benutzer&quot;um Begriffe handelt, die in der Regel auf die zählbare Dimension der höchsten Ebene verweisen, mit der Informationen über eine bestimmte Person erfasst werden.

Vollständige Informationen finden Sie im Handbuch zur Konfiguration von [Datasets](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html) .

## Arten von Dimensionen in DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

Es gibt zwei Arten von Dimensionen in Data Workbench: Erweiterte Dimensionen und abgeleitete Dimensionen.

Erweiterte Dimensionen werden aus Feldern in den &quot;Rohdatendateien&quot;erstellt. Erweiterte Dimensionen werden zur Kategorisierung von &quot;Rohdaten&quot;und zur Angabe der Beziehungen zwischen den Daten verwendet. Erweiterte Dimensionen werden von Data Workbench Architects erstellt.

Abgeleitete Dimensionen werden von einem Benutzer &quot;clientseitig&quot;erstellt, nachdem der Datensatz mit vorhandenen erweiterten Dimensionsdefinitionen verarbeitet wurde. Ein Benutzer kann beispielsweise auf der Grundlage der vorhandenen URI-Dimension eine abgeleitete Dimension &quot;Seitenname&quot;erstellen, die anstelle eines gegebenen URI einen benutzerfreundlicheren Seitennamen anzeigt. Alle Dimensionen bestehen aus Elementen oder Elementen, die zusammen kategorisiert (gruppiert) wurden, um die Dimension zu bilden. Unten sind drei Dimensionen und ihre Elemente.

Viele abgeleitete Dimensionen werden automatisch erstellt, um verschiedene Visualisierungen zu ermöglichen. Wenn ein Benutzer beispielsweise eine Site oder eine Prozesszuordnung erstellt, erstellen DWB-Server eine Präfix-Dimension. Andere Dimensionen, wie zum Beispiel die in Berichten aufgeführten Zeitdimensionen, werden durch Dateien im Dimensionsverzeichnis eines Profils definiert.

>[!NOTE]
>
>Die Elemente, die in einer bestimmten Dimension angezeigt werden, spiegeln nur die Werte wider, die in den Datensätzen vorhanden sind, die für das Laden in den Datensatz ausgewählt wurden. Wenn zum Beispiel keine Daten für &quot;12. Mai&quot;vorliegen, wird dieser Monat nicht in der Dimension &quot;Monat&quot;angezeigt.

## Extended Dimensions {#section-5fc51fa539034941a30a2df606f7d727}

Arten erweiterter Dimensionen

**1) Zählbare Dimensionen**

Auf der höchsten Ebene befinden sich zählbare Dimensionen. Zählbare Dimensionen dienen zwei Hauptfunktionen. Zunächst sind es Dimensionen, deren Elemente Sie zählen möchten. Mit anderen Worten beantworten die Tabellen Antworten auf die folgenden Fragen:

* &quot;Wie viele Besucher haben Ihre Homepage besucht?&quot;
* &quot;Wie viele Besuche kamen von google.com?&quot;

Aus diesem Grund werden zählbare Elemente oft als grundlegende Bausteine zur Erstellung von Metriken verwendet.

Die zweite wichtige Funktion von Countables ist, dass sie das Rückgrat Ihrer Datensatzschemastruktur bilden. Ihr Datenschema und alle anderen Dimensionen sind so organisiert, dass sie unter einer Zählung gruppiert werden und zu dieser gehören. Mit anderen Worten, wenn wir Dimensionen als &quot;Kategorien&quot;betrachten, dann sind Zähler die Art und Weise, wie wir diese &quot;Kategorien&quot;in Gruppen organisieren.

Wenn Dimensionen unter einer zählbaren Dimension gruppiert werden, werden sie als &quot;Ebene&quot;der zählbaren Dimension bezeichnet. Beispielsweise kann &quot;E-Mail-Adresse&quot;auf Besucherebene und &quot;Browser&quot;auf Besuchsebene angegeben werden. &quot;Übergeordnet&quot;und &quot;untergeordnet&quot;beziehen sich auf die Beziehung zwischen der zählbaren und den darunter gruppierten Dimensionen. Der Besucher ist beispielsweise ein &quot;übergeordnetes&quot;Element der E-Mail-Adresse. Umgekehrt ist die E-Mail-Adresse ein untergeordnetes Element des Besuchers.

**2) Einfache Dimensionen**

Die gängigsten Dimensionen sind einfache Dimensionen. Einfache Dimensionen haben eine Eins-zu-viele-Beziehung zu einer übergeordneten zählbaren Dimension und werden häufig in Visualisierungen verwendet, damit Sie ihre Elemente anzeigen können. Das bedeutet, dass eine zählbare Dimension einen Wert für eine einfache Dimension haben kann, die einfache Dimension jedoch zu einer oder mehreren Zählerwerten gehören kann. Zum Beispiel hat ein Kunde den Namen &quot;John&quot; - dieser Kunde kann nur einen Vornamen haben, aber viele andere Kunden können den Namen &quot;John;... Als weiteres Beispiel kann nur ein Browser (z. B. Firefox) für einen bestimmten Besuch einer Website verwendet werden, aber dieser Browser kann für viele verschiedene Besuche verwendet werden.

Wenn zählbare Dimensionen auf &quot;Wie viele?&quot;antworten, beantworten einfache Dimensionen &quot;Welche?&quot;. Verwenden Sie dasselbe Beispiel, das oben im Abschnitt zählbare Dimensionen verwendet wird. Der Seitenname ist die einfache Dimension. Mithilfe der Tabelle und der einfachen Dimension &quot;Seitenname&quot;können wir Fragen wie die folgenden beantworten:

* &quot;Welche Seite hatte die meisten Seitenansichten?&quot;
* &quot;Von allen Seiten des Einkaufswagens, die man am häufigsten besucht hat?&quot;

**3) Viele-zu-viele-Dimensionen**

Viele-zu-viele-Dimensionen haben eine Viele-zu-viele-Beziehung mit einer übergeordneten zählbaren Dimension. Wenn sich beispielsweise eine Dimension mit dem Namen &quot;Externer Suchbegriff&quot;auf Besuchsebene befindet; Ein bestimmter externer Suchbegriff kann bei einem oder mehreren Besuchen verwendet werden, und ein bestimmter Besuch kann einen oder mehrere externe Suchbegriffe enthalten. Der Begriff der externen Suche ist daher eine Viele-zu-viele-Dimension.

**4) Numerische Dimensionen**

Numerische Dimensionen sind eine Art einfache Dimension mit einem numerischen Wert. Numerische Dimensionen werden häufig für die Verwendung in Metriken erstellt. Beispiele für numerische Dimensionen sind &quot;Umsatz&quot;, &quot;Bestellungen&quot;und &quot;Einheiten&quot;. Im obigen Beispiel ist die Dimension &quot;Kundenaufträge&quot;eine numerische Dimension.
**5) Denormale Dimensionen** Denormale Dimensionen sind Dimensionen, die eine Eins-zu-Eins-Beziehung mit einer übergeordneten zählbaren Dimension aufweisen. Denormale Dimensionen werden häufig mit Dimensionen verwendet, die eine hohe Kardinalität (viele eindeutige Elemente) aufweisen, wie Identifizierungsdaten. Ein Besucher kann beispielsweise nur eine Benutzer-ID und eine Benutzer-ID nur einem Besucher angehören. Dies ist also eine Eins-zu-Eins-Beziehung und kann eine denormale Dimension sein.

Beispielsweise ist die Geometrixx-Web-Benutzer-ID eine denormale Dimension auf Kundenebene. Da es sich um eine denormale Dimension handelt, besteht eine Eins-zu-Eins-Beziehung mit der übergeordneten Dimension. Das bedeutet, dass jede Web-Benutzer-ID einen Kunden hat und jeder Kunde nur eine Web-Benutzer-ID hat. Die Metrik &quot;Kunden&quot;kann daher nur für jedes Element der Geometrixx-Web-Benutzer-ID &quot;1&quot;lauten.

**6) Zeitdimensionen**

Mit Zeitdimensionen können Sie einen Satz periodischer oder absoluter lokaler Zeitdimensionen erstellen, die auf dem von Ihnen angegebenen Zeitstempelfeld basieren. Beispiele für Zeitdimensionen sind &quot;Tag&quot;, &quot;Stunde&quot;, &quot;Woche&quot;und &quot;Stunde des Tages&quot;. Im obigen Beispiel zeigt die Tabelle &quot;Stunde des Tages&quot;an, wie viele Besuche und Seitenansichten während der verschiedenen Stunden der Tage empfangen wurden.

>[!NOTE]
>
>Die %-Escapes, die für die Anzeigeformatierung verwendet werden, sind identisch mit der C-Standardbibliothek *strftime*.

## Definieren erweiterter Dimensionen {#section-38ee124ec74b43fb95f13194a9582b97}

Schritte zum Definieren der erweiterten Dimension:

1. Öffnen Sie bei der Arbeit mit Ihrem DataSet-Profil den Profilmanager und klicken Sie auf &quot;Datensatz&quot;, um den Inhalt anzuzeigen.
1. Öffnen Sie die Datei &quot;Transformation.cfg&quot;oder die Datei &quot;Transformation DataSet Include&quot;, in der Sie die erweiterte Dimension definieren möchten.
1. Klicken Sie mit der rechten Maustaste auf Transformationen und klicken Sie auf Neu hinzufügen > `<Extended dimension type>`.
1. Geben Sie die entsprechenden Informationen für Ihre erweiterte Dimension ein. Beschreibungen der Transformationstypen und Informationen zu ihren Parametern finden Sie in den folgenden Abschnitten:

   * [Zählbare Dimensionen](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Einfache Dimensionen](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Viele-zu-viele-Dimensionen](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Numerische Dimensionen](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Denormale Dimensionen](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Zeitdimensionen](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. Für alle von Ihnen definierten erweiterten Dimensionen können Sie dem Parameter &quot;Kommentare&quot;eine oder mehrere Kommentarzeilen hinzufügen, um die Dimension weiter zu beschreiben oder Anmerkungen zur Verwendung hinzuzufügen. Um einen Kommentar hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Bezeichnung *Kommentare* und klicken Sie auf* Neu hinzufügen > Kommentarzeile*.

1. Nachdem Sie die erweiterte(n) Dimension(en) in der Konfigurationsdatei definiert haben, speichern Sie die Datei lokal und speichern Sie sie im DataSet-Profil auf dem DWB-Server.

## Ausblenden erweiterter Dimensionen {#section-02339fb51658418eabc10186cd5957d7}

Erweiterte Dimensionen können ausgeblendet werden, sodass sie nicht im Menü &quot;Abmessungen&quot;im DWB angezeigt werden. Um die Dimension auszublenden, setzen Sie die Eigenschaft &quot;Ausgeblendet&quot;in der Dimensionsdefinition auf &quot;True&quot;.
