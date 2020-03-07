---
description: Die verschiedenen Arten von abgeleiteten Dimensionen (clientseitig) und wie diese in Data Workbench eingerichtet werden.
title: Einstellungen für abgeleitete Dimensionen
uuid: 9d2416fb-1c29-45a8-91d0-ddca575224ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Einstellungen für abgeleitete Dimensionen{#derived-dimensions-setup}

Die verschiedenen Arten von abgeleiteten Dimensionen (clientseitig) und wie diese in Data Workbench eingerichtet werden.

## Typen abgeleiteter Dimensionen {#section-33e6dcc9ab9745de9b830cecb2427ca3}

**Metrikdimensionen**

Metrikdimension ermöglicht Ihnen, Metrikzählungen nach einer bestimmten Ebene zu gruppieren. Außerdem können Sie Metrikzählungen nach einer bestimmten Ebene gruppieren. Nachdem eine Metrikdimension erstellt wurde, können Sie Daten basierend auf dem Metrikwert segmentieren.

Beispiel 1: Sie sind ein Reiseunternehmen und möchten den Unterschied zwischen Ihren Vielfliegern und Kunden, die einen Flug weniger als 5-mal gebucht haben, verstehen, wie würden Sie das tun?

Alles, was Sie haben, ist die Zählung der Buchungen als Metrik, wie segmentieren Sie Kunden nach einer Metrik - hier, Buchung -, um ihr Verhalten auf der Website zu verstehen?

Beispiel 2: Sie sind eine Finanzbank und möchten Ihre Kunden nach der Anzahl der CDs gruppieren, in die sie investiert haben. Sie möchten Ihre Kunden in drei Stufen segmentieren. Tier 1 - Kunden mit mehr als 10 CDs, Tier 2 - Kunden mit mehr als 5 und weniger als 10 CDs und Tier 3 - Kunden mit mehr als 0 und weniger als 5 CDs

Die Informationen, die Ihnen zur Verfügung stehen, sind Metriken, die Ihnen die Anzahl der CD-Investitionen geben. Wie werden Sie für Ihre Analyse müde Kundensegmente erstellen?

*Metrikdimension erstellen - über Workstation*

Markieren Sie eine der OOB-Metrikdimensionen als lokal und benennen Sie diese Dimension mit einem benutzerspezifischen Namen um / Erstellen Sie eine lokale Kopie der Datei &quot;RenameDim.example&quot;und benennen Sie sie in den richtigen Dimensionsnamen mit der Erweiterung .dim um

Öffnen Sie die neu erstellte Dimension auf der Workstation, um Änderungen vorzunehmen. Ändern Sie die folgenden Parameter der Metrikdimension basierend auf den Anforderungen: ![](assets/dwb_impl_derived_dims1.png)

Metrik - Zu gruppierende Metrik

Ebene - Ebene, auf der Metriken gruppiert werden

Bucket Start - Startelement der Metrikdimension. Geben Sie denselben Wert im Offset ein.

Behältergröße - Gruppierungsgröße der Metrik. Geben Sie denselben Wert in der Skala ein

Anzahl der Behälter - Maximale Anzahl der Elemente, die in der Dimension angezeigt werden sollen

Speichern Sie die neu erstellte Dimension auf dem Server, wenn Sie sie für andere freigeben möchten.

**Präfix Dimensionen**

Der Hauptzweck der Dimension &quot;Präfix&quot;besteht darin, Elemente der ursprünglichen Dimension zu gruppieren und benutzerfreundliche Namen für die gruppierten Elemente bereitzustellen.

Sie besitzen beispielsweise eine Einzelhandels-Site, und Ihre Site enthält verschiedene Site-Abschnitte wie &quot;Damen-Kleidung&quot;, &quot;Herrenbekleidung&quot;, &quot;Spielzeug und Spiele&quot;, &quot;Home Decor&quot;usw. Jeder dieser Sitebereiche hat mehrere Seiten damit verbunden. Sie möchten eine Pfadanalyse durchführen und Einblicke in den Traffic erhalten, der von einem Site-Abschnitt zum anderen und so weiter geht. Wenn Sie die URI-Dimension verwenden, müssen Sie jede Seite des jeweiligen Sitebereichs im Pfadbrowser oder in der Prozesskarte abrufen und die Analyse fortsetzen.

Die gleiche Analyse kann problemlos durchgeführt werden, wenn eine Präfix-Dimension vorhanden ist, bei der Seiten eines Site-Abschnitts als einzelnes Element gruppiert werden.

Präfixabmessungen erstellen:

Öffnen Sie eine 2D-Prozesszuordnung im Menü Visualisierung.

Ändern Sie die folgenden Parameter der Präfix-Dimension entsprechend den Anforderungen.

Dimension der Karte ändern - Die Dimension, die Sie für 2D-Prozesszuordnung verwenden möchten (z. B: SMS-Typologie)

Dimension der Map-Ebene ändern - Ebene der oben genannten Dimension

Dimension des Map-Clips ändern - Die zählbare Ebene, auf der die Daten angezeigt werden sollen.

Metrik ändern: Die Metrik, die Sie anzeigen möchten.

Sobald die Zuordnung für den 2D-Prozess festgelegt ist, öffnen Sie die Dimension, die Sie im Parameter Dimension ändern der Map erwähnt haben.

Wählen Sie die Elemente aus, die Sie gruppieren möchten. Verwenden Sie STRG+ALT und ziehen Sie die Elemente per Drag &amp; Drop in die Prozesszuordnung.

Klicken Sie mit der rechten Maustaste auf den angezeigten Punkt und benennen Sie den Gruppennamen um. Wenn Sie 3 Elemente für die Gruppe ausgewählt haben, lautet der Standardname 3 ausgewählt.

Klicken Sie mit der rechten Maustaste auf den Umriss der Visualisierung und speichern Sie Dimension aus dem Menü, das angezeigt wird.

**Dimensionen umbenennen**

Dimensionen umbenennen werden aus einer bereits vorhandenen Dimension erstellt. Hauptzweck der Dimension &quot;Umbenennen&quot;ist es, benutzerfreundliche Namen für die Elemente der Dimension bereitzustellen. Die Dimension &quot;Umbenennen&quot;ist standardmäßig die Dimension &quot;Seite&quot;, die aus der URI-Dimension erstellt wird. Die URI-Dimension kann für eine Person verwirrend sein, die die technischen Namen der Seiten nicht kennt. Deshalb ermöglicht Ihnen die Dimension &quot;Seite&quot;die Umbenennung von Elementen der URI-Dimension.

ERSTELLEN VON BENUTZERDEFINIERTEN UMBENENNUNGSDIMENSIONEN:

Elemente der umbenannten Dimension verfügen über eine 1-zu-1-Zuordnung mit den Elementen der ursprünglichen Basisdimension. Sie können dies überprüfen, indem Sie die DIM-Datei &quot;Dimension umbenennen&quot;im Workstation/Notiz-Pad öffnen. Sie werden feststellen, dass jedes Element der ursprünglichen Dimension nur einen Wert (Zeichenfolge umbenennen) für dieses Element in der Datei hat.

Wenn Sie weniger Elemente für den Umbenennungszweck haben; Sie können eine .dim-Datei auf der Workstation erstellen und die einzelnen Elemente anhand der unten beschriebenen Schritte umbenennen.

Schritte zum Erstellen einer dim-Datei für eine Dimension umbenennen - Verwenden der Workstation

Verwenden Sie diese Option, wenn die Anzahl der umbenannten Elemente geringer ist.

1. Öffnen Sie einen leeren Arbeitsbereich und öffnen Sie den Dimensions-Manager. Klicken Sie mit der rechten Maustaste auf > Admin > Profil > Profil-Manager.
1. Erweitern Sie den Dimensionsordner in der Spalte &quot;Datei&quot;.
1. Erweitern Sie den Seitenordner in der Spalte &quot;Datei&quot;und klicken Sie mit der rechten Maustaste auf die Datei &quot;Page.dim&quot;in der Spalte &quot;Zweiter bis letzter&quot;(diese Spalte entspricht normalerweise dem Profilnamen) und klicken Sie auf die Option &quot;Als lokal definieren&quot;.
1. Klicken Sie mit der rechten Maustaste auf &quot;Page.dim&quot; in der Spalte &quot;User&quot; und klicken Sie auf die Option Kopieren und fügen Sie die kopierte .dim-Datei in den gewünschten Ordner unter dem Dimensionsverzeichnis ein.
1. Klicken Sie in der Fehlermeldung auf OK.
1. Nun werden Sie feststellen, dass sich im Ordner Dimensionen zwei Dateien von Page.dim befinden. Eine ist die Originaldatei unter &quot;Dimensions\Page&quot; und die zweite Datei die, die Sie in Schritt 4 eingefügt haben.
1. Klicken Sie mit der rechten Maustaste auf die kürzlich eingefügte Datei &quot;Page.dim&quot;unter der Spalte &quot;Benutzer&quot;und klicken Sie auf das blaue/graue Eingabefeld mit der Meldung &quot;Page.dim&quot;. Das Eingabefeld wird grün, wobei der Cursor blinkt, um anzuzeigen, dass er geändert werden kann. Geben Sie den Namen der Dimension &quot;Umbenennen&quot;ein, die Sie erstellen möchten.
1. Sie werden feststellen, dass die Datei &quot;Page.dim&quot;in der Spalte &quot;Datei&quot;in den neuen Dateinamen geändert wurde, den Sie in Schritt 7 angegeben haben. Klicken Sie mit der rechten Maustaste auf die Datei new.dim in der Spalte Benutzer (Letzte Spalte) und wählen Sie Öffnen > In Workstation.
1. Nachdem die .dim-Datei auf der Workstation geöffnet wurde; Klicken Sie auf das Pluszeichen (+) neben der Entität und erweitern Sie sie. Beachten Sie den Wert, der dem Feld &quot;Übergeordnet&quot;gegenübersteht, und spiegelt die Dimension &quot;URI&quot;wider. Es zeigt &quot;wdata/model/dim/URI&quot; Klicken Sie auf das blaue/graue Eingabefeld, um den URI in den Namen der Dimension zu ändern, deren Elemente Sie umbenennen möchten.
1. Stellen Sie sicher, dass die Dimension, die Sie umbenennen möchten, im Datensatz vorhanden ist. Bei Dimensionsnamen wird die Groß-/Kleinschreibung beachtet, sodass die Groß-/Kleinschreibung der ursprünglichen Dimension beibehalten wird.
1. Achten Sie auf das &quot;Geändert&quot;neben dem Dimensionsnamen. Dies bedeutet, dass die ursprüngliche Dimension geändert wurde. die in Schritt 9 vorgenommenen Änderungen aufrechtzuerhalten; Klicken Sie mit der rechten Maustaste auf new.dim (modifiziert) und klicken Sie auf die Option &quot;Speichern unter&quot;.
1. Sobald die Dimension pro Schritt 10 gespeichert wurde, steht Ihnen die neu erstellte Dimension &quot;Umbenennen&quot;für die Kampagnen jetzt zum Zwecke der Umbenennung zur Verfügung. Dies steht Ihnen nur lokal zur Verfügung.
1. Damit andere die von Ihnen erstellte Dimension sehen können, muss sie im Profil gespeichert werden. Klicken Sie mit der rechten Maustaste auf die .dim-Datei der neuen Dimension in der Spalte &quot;Benutzer&quot; (Letzte Spalte) und klicken Sie auf &quot;Speichern unter > Profilname&quot;, in dem Sie die Dimension speichern möchten.
1. Nach dem Speichern der Datei im Profil können alle Workstation-Benutzer, die Zugriff auf dieses Profil haben, die Dimension &quot;Umbenennen&quot;für die Kampagnen sehen.

Präfix und Umbenennen des dim creator-Tools

Adobe verfügt über ein Excel-Tool zum Generieren von Präfix und Umbenennen von Dimensionen.

Im Folgenden finden Sie die Schritte zum Generieren der Präfix-/Umbenennungsabmessungen mithilfe des Tools:

1. Speichern Sie das Excel-Tool *Adobe_DWB_Dimension_Generator.xlsm* in einem Ordner. Wenden Sie sich an den Adobe-Kundendienst, um das Tool herunterzuladen.
1. Öffnen Sie das Tool und aktivieren Sie Makros: ![](assets/dwb_impl_derived_dims2.png)

1. Füllen Sie das Datenblatt mit den zu verwendenden Werten aus.

   So erstellen wir z. B. die Dimension &quot;Präfix der Produktmarke&quot;basierend auf der Produktdimension. Im Datenblatt werden die folgenden Informationen erfasst: ![](assets/dwb_impl_derived_dims3.png)

   Jedes Produkt wird einer Marke im Datenblatt zugeordnet.

1. Füllen Sie auf der Registerkarte &quot;Konfiguration&quot;die Informationen zu der zu erstellenden Dimension aus. Für die oben stehenden Musterdaten werden folgende Informationen eingegeben: ![](assets/dwb_impl_derived_dims4.png)

   Name: Name für die Dimension &quot;Präfix/Umbenennen&quot;

   Typ: Präfix/Umbenennen

   Quell-Dim: Ursprüngliche Dimension

   Übereinstimmung Spalte: Zu vergleichende Spalte

   Ergebnisspalte: Für neue Dimension zu verwendender Wert.

1. Klicken Sie auf die Schaltfläche *Klicken Sie hier*. ![](assets/dwb_impl_derived_dims5.png)

1. Die dim-Datei wird in demselben Ordner generiert, in dem das Tool gespeichert wurde. ![](assets/dwb_impl_derived_dims6.png)

   Speichern Sie die DMM-Datei mit dem Profil-Manager im Ordner &quot;Dimension&quot;.

**Dimensionen verschieben**

Mit den Umschalt-Dimensionen können Sie sich das n. Element einer beliebigen Dimension innerhalb einer bestimmten zählbaren Dimension ansehen.

Sie geben Ihnen außerdem die Möglichkeit, auf -n. Element einer beliebigen Dimension innerhalb einer bestimmten zählbaren Dimension zurückzublicken.

Beispiel 1:

* Die n. Seite innerhalb einer Sitzung - Dimension &quot;Nächste Seite&quot;
* Die n. Seite eines Besuchers - Nächste Seite für Besucher - für alle Sitzungen
* n. Aufruf für einen Benutzer

Warum ist es wichtig, das n. Element der zählbaren Dimension zu kennen?

* Sie möchten die 5. Seite kennen, die in einer Sitzung angezeigt wird.
* Sie möchten mithilfe von Pfaden zu Kampagnen erkennen, welche Kampagne nach Ansicht der Kampagne &quot;Kostenloses Überprüfungskonto&quot;angezeigt wurde?
* Sie möchten wissen, auf welchen Link der Besucher geklickt hat, bevor Sie auf den Link &quot;Chat mit einem Agent&quot; klicken? ![](assets/dwb_impl_derived_dims7.png)

Der nächste URI ist eine der OOB-Shift-Dimensionen, die als Vorlage verwendet werden können. Im obigen Beispiel erhalten Sie das Element 2nd(Offset = 1) der Kampagne (Dim = Kampagne) im Interaktions-Ereignis (Clip = Interaktionsereignis)

Hier steht offset 1 für einen Blick nach rechts - vorwärts im Ereignis

Andere OOB-Shift-Dimensionen

*Nächste Seite:*

Die nächste Seite, die in einer Sitzung nach der aktuell ausgewählten Seite in der Seitendimension angezeigt wird

Hier ist der Offset 1, Ebene ist Seitenansicht, Dim ist Seite und Clip ist Sitzung

*Vorherige Seite:*

Die vorherige Seite, die in einer Sitzung vor der aktuell ausgewählten Seite in der Seitendimension angezeigt wurde

Hier ist der Offset -1, Ebene ist Seitenansicht, Dim ist Seite und Clip ist Sitzung

Wie sieht die vorherige Kampagne aus, die ein Besucher vor der derzeit ausgewählten Kampagne anzeigte?

Hier ist Offset -1, Ebene ist Kampagnenantwort, Dim ist Kampagnen-Antwortattribut-Wert und Clip ist Besucher

*Shift Dimension erstellen - über Workstation*

* Markieren einer OOB-Verschiebungsdimension als lokal
* Benennen Sie diese Dimension mit einem benutzerdefinierten Namen um
* Neu erstellte Dimension auf der Workstation öffnen, um Änderungen vorzunehmen
* Ändern Sie die folgenden Parameter der Metrikdimension basierend auf den Anforderungen.

   * Ebene-Zählbare Dimension
   * Offset-Sie möchten rückwärts blicken
   * Dim -Dimension, deren Elemente Sie analysieren möchten
   * Clip-zählbar in der Sie anzeigen möchten.

* Speichern Sie die neu erstellte Dimension auf dem Server, wenn Sie sie für andere freigeben möchten.

**Letzte n Dimension**

Last N Dimensions funktioniert nur auf der Zeitdimension und auf der Ausführungszeit des Systems. OOB-Zeitdimensionen sind Tag, Woche, Stunde und Monat. Sie können die Dimension &quot;Letzte N&quot;für jede dieser grundlegenden Zeitdimensionen erstellen, z. B. &quot;Letzte 10 Tage&quot;, &quot;Letzte 72 Stunden&quot;, &quot;Letzte 8 Wochen&quot;, &quot;Letzte 6 Monate&quot;usw. Die letzte N Dimension berechnet die letzte N auf Grundlage der aktuellen &quot;Berichtszeitmetrik&quot;oder der Zeit des Systems. ![](assets/dwb_impl_derived_dims8.png)

Anzahl - Gesamtzahl der Elemente, die in der Dimension angezeigt werden sollen

Bereichsversatz: Versatzwert, der den Startpunkt (Tag/Woche) zur Berechnung des letzten N Tages/der letzten Woche angibt.

**None.dim**

None.dim ist eine Alias-Dimension. Es wird zum Erstellen eines Alias aus erweiterten Dimensionen verwendet.

Beispiel:

In der Datei &quot;None.dim&quot;wird die Entität als &quot;wdata/model/dim/Parent/+name&quot;definiert (sie kann geändert werden). Dies bedeutet, dass die Dimension entsprechend dem Namen der Dimensionsdatei erstellt wird. Wenn wir also eine Kopie der Datei &quot;None.dim&quot;im Ordner &quot;Dimension&quot;erstellen (z. B. Kopieren und Umbenennen der Datei &quot;None.dim&quot;im Ordner &quot;Besucherprofil&quot;) und sie in &quot;Log Source ID.dim&quot;umbenennen, wird im Menü unter Besucherprofil eine neue abgeleitete Dimension mit der Protokollquelle-ID wie unten dargestellt angezeigt:

Vor Änderungen: ![](assets/dwb_impl_derived_dims9.png)

Nach Änderungen von &quot;None.dim&quot;: ![](assets/dwb_impl_derived_dims10.png)

Die Entität kann in den Namen der erweiterten Dimension geändert werden, in diesem Fall kann eine andere Dimension mit einem anderen Namen, der auf dieselbe Dimension verweist wie unten dargestellt:

In diesem Beispiel enthält &quot;Source Name.dim&quot;den folgenden Inhalt: ![](assets/dwb_impl_derived_dims11.png)

Daraufhin wird ein weiterer Dimensionsquellenname angezeigt, der auf die Protokollquelle-ID verweist. ![](assets/dwb_impl_derived_dims12.png)

**Ausblenden abgeleiteter Dimensionen**

Um die abgeleitete Dimension auszublenden, setzen Sie die *Eigenschaft &quot;Anzeigen* &quot;auf &quot;false&quot;. ![](assets/dwb_impl_derived_dims13.png)

