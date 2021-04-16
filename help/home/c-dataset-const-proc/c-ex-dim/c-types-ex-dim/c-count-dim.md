---
description: Die Elemente einer zählbaren Dimension können vom System gezählt werden.
title: Zählbare Dimensionen
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
exl-id: c607c15d-de85-4daf-af76-79b460f51b38
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 4%

---

# Zählbare Dimensionen{#countable-dimensions}

Die Elemente einer zählbaren Dimension können vom System gezählt werden.

Zählbare Dimensionen werden normalerweise zur Erstellung von Summenmetriken verwendet, die die Anzahl oder Summe aller Elemente der Dimension zurückgeben. Sie können zählbare Dimensionen definieren, um z. B. Reservierungen oder Produktbestellungen zu zählen. Sie können beispielsweise die zählbare Dimension Bestellungen definieren, deren Elemente (Protokolleinträge, die Bestellungen aus Ihrem Online-Store entsprechen) gezählt werden können. Wenn Sie eine Anzahl von Bestellungen innerhalb einer Visualisierung anzeigen möchten, definieren Sie die Metrik &quot;Bestellsumme&quot;, die über eine Dimension ausgewertet werden kann oder auf die Filter angewendet werden sollen.

Zählbare Dimensionen können übergeordnete Elemente anderer Dimensionen oder untergeordnete Elemente anderer zählbarer Dimensionen sein.

>[!NOTE]
>
>Wenn Sie eine Dimension benötigen, die nur eine Zählung von etwas liefert, sollten Sie eine numerische Dimension mit einer COUNT-Operation verwenden. Siehe [Numerische Dimensionen](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed).

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
   <td colname="col2"> Beschreibender Name der Dimension, wie er dem Benutzer in Data Workbench angezeigt wird. Der Dimensionsname darf keinen Bindestrich (-) enthalten. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur erweiterten Dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen das Eingabefeld zur Erstellung der zählbaren Dimension beiträgt. Wenn eine Bedingung angegeben ist, beschränkt sie den Satz der Protokolleinträge, die für die Dimension und alle untergeordneten Elemente im DataSet-Schema sichtbar sind. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Verborgen </td> 
   <td colname="col2"> Bestimmt, ob die Dimension in der Data Workbench-Oberfläche angezeigt wird. Standardmäßig ist dieser Parameter auf false festgelegt. Wenn die Dimension beispielsweise nur als Grundlage für eine Metrik verwendet werden soll, können Sie diesen Parameter auf "true"setzen, um die Dimension aus der Datenbasis-Anzeige auszublenden. </td> 
   <td colname="col3"> false (falsch) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schlüssel </td> 
   <td colname="col2"> <p>Optional. Der Name des Felds, das als Schlüssel verwendet werden soll. Wenn Sie diesen Parameter definieren, besteht für jede Kombination eines Elements der übergeordneten zählbaren Dimension und eines eindeutigen Werts des als Schlüssel angegebenen Felds ein Element der zählbaren Dimension. </p> <p> Jedes Element der zählbaren Dimension muss sich auf einen zusammenhängenden Satz von Protokolleinträgen beziehen. Wenn die Protokolleinträge daher nicht nach Schlüssel geordnet sind, wird jedes Mal, wenn sich das Schlüsselfeld ändert, ein Element der zählbaren Dimension erstellt. Um dies zu verhindern, empfiehlt Adobe die Verwendung eines eindeutigen Schlüssels, der zeitlich aufeinander abgestimmt ist. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Übergeordnet </td> 
   <td colname="col2"> <p>Der Name der übergeordneten Dimension. Jede zählbare Dimension kann eine übergeordnete Dimension sein. Um eine Dimension zur Dimension der obersten Ebene im Schema des Datensatzes zu machen, setzen Sie den Parameter auf "root". Die definierte Dimension wird zur zählbaren Dimension für den Dataset. Wenn Sie beispielsweise mit Site arbeiten, ist die Dimension "Besucher"die zählbare Dimension für Ihren Datensatz. </p> <p> <p>Hinweis:  Obwohl Ihre zählbare Dimension für den Stammordner nicht mit den Tracking-IDs in den Daten verknüpft werden muss, empfiehlt Adobe, die zählbare Dimension des Datensatzes zu konfigurieren, um das Verfolgungs-ID-Feld (x-trackingid) als Schlüssel zu verwenden. Daher wird jedes Element der Stamm-Zählung mit dem eindeutigen Wert x-trackingid verknüpft und alle Daten zu jedem Element werden gruppiert. Wenn Sie Ihren Datensatz anders konfigurieren möchten, wenden Sie sich an die Adobe. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In diesem Beispiel wird die Definition einer zählbaren Dimension anhand von Ereignis-Daten veranschaulicht, die aus dem Website-Traffic erfasst wurden. Die zählbare Dimension zählt die Ereignis der Web-Kampagne innerhalb einer bestimmten Sitzung. Es wird davon ausgegangen, dass alle E-Mail-Kampagnen vom Webserver mit &quot;email=&quot;als Teil der cs-uri-Abfrage angefordert werden. In diesem Beispiel ist die Häufigkeit, mit der der Besucher während einer bestimmten Sitzung auf eine E-Mail-Kampagne antwortet, von Interesse, nicht der tatsächliche Wert des Felds &quot;cs-uri-Abfrage(E-Mail)&quot;.

![](assets/cfg_Transformation_Dim_Countable.png)

In diesem Beispiel wird auch die Definition einer zählbaren Dimension anhand von Ereignis-Daten veranschaulicht, die aus dem Website-Traffic gesammelt wurden, jedoch über einen definierten Schlüsselparameter verfügen. Die zählbare Dimension &quot;Sitzung&quot;verwendet das Feld mit dem X-Sitzungsschlüssel als Schlüssel. (Das Feld x-session-key ist die Ausgabe der [!DNL Sessionize]-Transformation und hat einen eindeutigen Wert für jede Sitzung.) Jede eindeutige Kombination eines Elements der Dimension &quot;Besucher&quot;(das übergeordnete Element) und des Felds &quot;x-session-key&quot;ist ein Element der Dimension &quot;Sitzung&quot;.

![](assets/cfg_Transformation_Dim_Countable2.png)
