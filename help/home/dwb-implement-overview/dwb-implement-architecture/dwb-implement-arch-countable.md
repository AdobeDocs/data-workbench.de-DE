---
description: Erläuterung der Tabellen in DataWorkbench (DWB) zur Erstellung und Implementierung des Schemas.
title: Schema-Aufbau von zählbaren Strukturen
uuid: 2530980d-1c6b-4a96-b9c1-431fc75678bb
exl-id: 4f2a2f8a-7b42-42bb-8ba1-2675ffe6b2c2
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 3%

---

# Schema-Aufbau von zählbaren Strukturen{#schema-design-countable-structures}

Erläuterung der Tabellen in DataWorkbench (DWB) zur Erstellung und Implementierung des Schemas.

## Grundlagen zur Zählung in Data Workbench {#section-6e6b8d1c17634d669e62c91a80a0bc62}

Auf der höchsten Ebene sind zählbare Dimensionen. Zählbare Dimensionen bieten zwei Hauptfunktionen. Zunächst handelt es sich um Dimensionen, deren Elemente Sie zählen möchten. Mit anderen Worten: Zählungen beantworten Fragen wie:

* Wie viele Besucher haben Ihre Homepage besucht?

* Wie viele Besuche kamen von Google.com?

`<discoiqbr>`Zählbare Dimensionen werden normalerweise verwendet, um Summenmetriken zu erstellen, die die Anzahl oder Summe aller Elemente der Dimension zurückgeben. Sie können zählbare Dimensionen definieren, um Instanzen wie Reservierungen oder Produktbestellungen zu zählen. Sie können beispielsweise die zählbaren Dimensionsbestellungen definieren, deren Elemente (Protokolleinträge, die den Bestellungen aus Ihrem Online-Store entsprechen) gezählt werden können. Wenn Sie innerhalb einer Visualisierung eine Anzahl von Bestellungen anzeigen möchten, definieren Sie die Metrik der Bestellsumme, die über eine Dimension ausgewertet werden kann oder auf die Filter angewendet werden sollen.

Zählbare Dimensionen können übergeordnete Elemente anderer Dimensionen oder untergeordnete Elemente anderer zählbarer Dimensionen sein.

Obwohl Ihre zählbare Stammdimension nicht mit den Tracking-IDs in den Daten verknüpft werden muss, empfiehlt Adobe, die zählbare Stammgruppendimension Ihres Datensatzes so zu konfigurieren, dass das Tracking-ID-Feld (x-trackingid) als Schlüssel verwendet wird. Daher wird jedes Element der Stammzählung mit einem eindeutigen Wert von x-trackingid verknüpft und alle Daten zu jedem Element werden gruppiert.

Zählbare Dimensionen werden durch die folgenden Parameter definiert:

<table id="table_5E00B72CFDD645368ADCC25AB9B5E53D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Deskriptiver Name der Dimension, wie er dem Benutzer in Data Workbench angezeigt wird. Der Dimensionsname darf keinen Bindestrich (-) enthalten. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kommentare </p> </td> 
   <td colname="col2"> <p>Optional. Hinweise zur erweiterten Dimension.

    &lt;/p> &lt;/td>
<td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bedingung </p> </td> 
   <td colname="col2"> <p>Die Bedingungen, unter denen das Eingabefeld zur Erstellung der zählbaren Dimension beiträgt. Sofern angegeben, beschränkt eine Bedingung den Satz von Protokolleinträgen, der für die Dimension und alle untergeordneten Elemente im Datensatzschema sichtbar ist. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verborgen </td> 
   <td colname="col2"> Bestimmt, ob die Dimension in der Data Workbench-Benutzeroberfläche angezeigt wird. Standardmäßig ist dieser Parameter auf false gesetzt. Wenn die Dimension beispielsweise nur als Grundlage einer Metrik verwendet werden soll, können Sie diesen Parameter auf "true"setzen, um die Dimension aus der Data Workbench-Anzeige auszublenden. </td> 
   <td colname="col3"> false (falsch) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schlüssel </td> 
   <td colname="col2"> <p>Optional. Der Name des Felds, das als Schlüssel verwendet werden soll. Wenn Sie diesen Parameter definieren, ist für jede Kombination eines Elements der übergeordneten zählbaren Dimension ein Element der zählbaren Dimension und für das als Schlüssel angegebene Feld ein eindeutiger Wert vorhanden. </p> <p>Jedes Element der zählbaren Dimension muss sich auf einen zusammenhängenden Satz von Protokolleinträgen beziehen. Wenn die Protokolleinträge daher nicht nach Schlüssel geordnet werden, wird jedes Mal, wenn sich das Schlüsselfeld ändert, ein Element der zählbaren Dimension erstellt. Um dies zu verhindern, empfiehlt Adobe die Verwendung eines eindeutigen Schlüssels, der zeitlich aufeinander folgt. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> <p> Der Name der übergeordneten Dimension. Jede zählbare Dimension kann eine übergeordnete Dimension sein. Um eine Dimension zur Dimension der obersten Ebene im Schema des Datensatzes zu machen, setzen Sie den Parameter auf "root". Die definierte Dimension wird zur zählbaren Stammdimension für den Datensatz. Wenn Sie beispielsweise mit Site arbeiten, ist die Dimension Besucher die Dimension Stamm-Zählung für Ihren Datensatz. </p> <p>Hinweis: Obwohl Ihre zählbare Stammdimension nicht mit den Tracking-IDs in den Daten verknüpft werden muss, empfiehlt Adobe, die zählbare Stammdimension Ihres Datensatzes so zu konfigurieren, dass das Tracking-ID-Feld (x-trackingid) als Schlüssel verwendet wird. Daher wird jedes Element der Stammzählung mit einem eindeutigen Wert von x-trackingid verknüpft und alle Daten zu jedem Element werden gruppiert. Wenn Sie Ihren Datensatz anders konfigurieren möchten, wenden Sie sich an Adobe. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird die Definition einer zählbaren Dimension anhand von Ereignisdaten veranschaulicht, die aus dem Website-Traffic erfasst wurden. Die zählbare Dimension zählt die Webkampagnenereignisse innerhalb einer bestimmten Sitzung. Es wird angenommen, dass alle E-Mail-Kampagnenressourcen vom Webserver mit &quot;email=&quot;als Teil der cs-uri-Abfrage angefordert werden. Im Beispiel ist die Anzahl der Antworten des Besuchers auf eine E-Mail-Kampagne während einer bestimmten Sitzung interessant, nicht der tatsächliche Wert des Felds cs-uri-query(email) .

![](assets/dwb_impl_arch_1.png)

Die zweite wichtige Funktion von zählbaren Elementen besteht darin, dass sie das Rückgrat Ihrer Datensatzschemastruktur bilden. Ihr Datenschema und alle anderen Dimensionen sind so strukturiert, dass sie unter einer Tabelle gruppiert werden und zu einer Tabelle gehören. Mit anderen Worten, wenn wir Dimensionen als &quot;Kategorien&quot;betrachten, dann sind Zählungen die Art und Weise, wie wir diese &quot;Kategorien&quot;in Gruppen organisieren.
Wenn Dimensionen unter einer zählbaren Dimension gruppiert werden, befinden sie sich auf der &quot;Ebene&quot;der zählbaren Dimension. In der folgenden Abbildung sehen Sie beispielsweise, dass sich &quot;E-Mail-Adresse&quot;auf Besucherebene und &quot;Browser&quot;auf Besuchsebene befindet. &quot;Übergeordnetes Element&quot;und &quot;untergeordnetes Element&quot;beziehen sich auf die Beziehung zwischen der zählbaren Tabelle und den darunter gruppierten Dimensionen. Beispielsweise ist Besucher ein &quot;übergeordnetes&quot;Element der E-Mail-Adresse. Umgekehrt ist die E-Mail-Adresse ein &quot;untergeordnetes Element&quot;des Besuchers. ![](assets/dwb_impl_arch_2.png) ![](assets/dwb_impl_arch_3.png)

## Erstellung von Zählern in Data Workbench {#section-491f3e8e4fbc429e95d6c97f012a208e}

Führen Sie die folgenden Schritte aus, um die Tabelle in Data Workbench zu erstellen:

1. Profil-Manager öffnen
1. Erstellen Sie unter dem Ordner &quot;Transformation&quot;eine Konfigurationsdatei und öffnen Sie sie auf der Workstation.
1. Klicken Sie unter Erweiterte Dimensionen mit der rechten Maustaste und wählen Sie Neue hinzufügen -> Zählbar wie unten dargestellt: ![](assets/dwb_impl_arch_4.png)

1. Geben Sie den Namen für die neue Tabelle &quot;Zählung&quot;ein. Im folgenden Beispiel ist Customer Countable definiert. Wenn es die höchste zählbare Ebene ist, dann schreiben Sie im übergeordneten Stamm. ![](assets/dwb_impl_arch_5.png)

   Wenn die Tabelle Zählung nicht die oberste Ebene ist, geben Sie im übergeordneten Feld den Namen der übergeordneten Tabelle an. Im folgenden Beispiel wird die Interaktionszählung erstellt und das übergeordnete Element für diese zählbare Tabelle ist &quot;Kunde&quot;. ![](assets/dwb_impl_arch_5.png)

Weitere Informationen zur Data Workbench-Architektur für Schemadesign, zählbare Strukturen und Offline-Daten-Feed-Konfigurationen finden Sie in der [Datensatzschema-Schnittstelle](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-dtst-sch-intrf.html).
