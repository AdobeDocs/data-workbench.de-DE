---
description: Die Elemente einer zählbaren Dimension können vom System gezählt werden.
title: Zählbare Dimensionen
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
exl-id: c607c15d-de85-4daf-af76-79b460f51b38
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 4%

---

# Zählbare Dimensionen{#countable-dimensions}

Die Elemente einer zählbaren Dimension können vom System gezählt werden.

Zählbare Dimensionen werden normalerweise verwendet, um Summenmetriken zu erstellen, die die Anzahl oder Summe aller Elemente der Dimension zurückgeben. Sie können zählbare Dimensionen definieren, um Instanzen wie Reservierungen oder Produktbestellungen zu zählen. Sie können beispielsweise die zählbare Dimension Bestellungen definieren, deren Elemente (Protokolleinträge, die Bestellungen aus Ihrem Online-Store entsprechen) gezählt werden können. Wenn Sie eine Anzahl von Bestellungen in einer Visualisierung anzeigen möchten, definieren Sie die Metrik Bestellungen-Summe , die über eine Dimension ausgewertet werden kann oder auf die Filter angewendet werden sollen.

Zählbare Dimensionen können übergeordnete Elemente anderer Dimensionen oder untergeordnete Elemente anderer zählbarer Dimensionen sein.

>[!NOTE]
>
>Wenn Sie eine Dimension benötigen, die nur eine Zählung von etwas bereitstellt, sollten Sie eine numerische Dimension mit dem Vorgang COUNT verwenden. Siehe [Numerische Dimensionen](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed).

Zählbare Dimensionen werden durch die folgenden Parameter definiert:

<table id="table_9F3F093F5B074EA68CA4DCE731161F6C"> 
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
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Hinweise zur erweiterten Dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen das Eingabefeld zur Erstellung der zählbaren Dimension beiträgt. Sofern angegeben, beschränkt eine Bedingung den Satz von Protokolleinträgen, der für die Dimension und alle untergeordneten Elemente im Datensatzschema sichtbar ist. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verborgen </td> 
   <td colname="col2"> Bestimmt, ob die Dimension in der Data Workbench-Benutzeroberfläche angezeigt wird. Standardmäßig ist dieser Parameter auf false gesetzt. Wenn die Dimension beispielsweise nur als Grundlage einer Metrik verwendet werden soll, können Sie diesen Parameter auf "true"setzen, um die Dimension aus der Data Workbench-Anzeige auszublenden. </td> 
   <td colname="col3"> false (falsch) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schlüssel </td> 
   <td colname="col2"> <p>Optional. Der Name des Felds, das als Schlüssel verwendet werden soll. Wenn Sie diesen Parameter definieren, ist für jede Kombination eines Elements der übergeordneten zählbaren Dimension ein Element der zählbaren Dimension und für das als Schlüssel angegebene Feld ein eindeutiger Wert vorhanden. </p> <p> Jedes Element der zählbaren Dimension muss sich auf einen zusammenhängenden Satz von Protokolleinträgen beziehen. Wenn die Protokolleinträge daher nicht nach Schlüssel geordnet werden, wird jedes Mal, wenn sich das Schlüsselfeld ändert, ein Element der zählbaren Dimension erstellt. Um dies zu verhindern, empfiehlt Adobe die Verwendung eines eindeutigen Schlüssels, der zeitlich aufeinander folgt. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> <p>Der Name der übergeordneten Dimension. Jede zählbare Dimension kann eine übergeordnete Dimension sein. Um eine Dimension zur Dimension der obersten Ebene im Schema des Datensatzes zu machen, setzen Sie den Parameter auf "root". Die definierte Dimension wird zur zählbaren Stammdimension für den Datensatz. Wenn Sie beispielsweise mit Site arbeiten, ist die Dimension Besucher die Dimension Stamm-Zählung für Ihren Datensatz. </p> <p> <p>Hinweis:  Obwohl Ihre zählbare Stammdimension nicht mit den Tracking-IDs in den Daten verknüpft werden muss, empfiehlt Adobe, die zählbare Stammdimension Ihres Datensatzes so zu konfigurieren, dass das Tracking-ID-Feld (x-trackingid) als Schlüssel verwendet wird. Daher wird jedes Element der Stammzählung mit einem eindeutigen Wert von x-trackingid verknüpft und alle Daten zu jedem Element werden gruppiert. Wenn Sie Ihren Datensatz anders konfigurieren möchten, wenden Sie sich an Adobe. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird die Definition einer zählbaren Dimension anhand von Ereignisdaten veranschaulicht, die aus dem Website-Traffic erfasst wurden. Die zählbare Dimension zählt die Webkampagnenereignisse innerhalb einer bestimmten Sitzung. Es wird angenommen, dass alle E-Mail-Kampagnenressourcen vom Webserver mit &quot;email=&quot;als Teil der cs-uri-Abfrage angefordert werden. Im Beispiel ist die Anzahl der Antworten des Besuchers auf eine E-Mail-Kampagne während einer bestimmten Sitzung interessant, nicht der tatsächliche Wert des Felds cs-uri-query(email) .

![](assets/cfg_Transformation_Dim_Countable.png)

In diesem Beispiel wird auch die Definition einer zählbaren Dimension anhand von Ereignisdaten veranschaulicht, die aus dem Website-Traffic erfasst wurden, es gibt jedoch einen definierten Schlüsselparameter. Die zählbare Dimension Sitzung verwendet das Feld x-session-key als Schlüssel. (Das Feld x-session-key ist die Ausgabe der [!DNL Sessionize]-Transformation und hat einen eindeutigen Wert für jede Sitzung.) Jede eindeutige Kombination eines Elements der Besucherdimension (das übergeordnete Element) und des Felds x-Sitzungsschlüssel ist ein Element der Sitzungsdimension.

![](assets/cfg_Transformation_Dim_Countable2.png)
