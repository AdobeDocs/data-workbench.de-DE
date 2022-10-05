---
description: Auf dem Data Workbench-Server stehen verschiedene Dimensionstypen zur Verfügung. Daher ist es wichtig, den Dimensionstyp zu kennen, wenn Sie eine Dimension zum Erstellen von Metriken, Filtern oder abgeleiteten Dimensionen verwenden.
title: Typen von Dimensionen
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
exl-id: cbc25504-2c1c-4622-adc1-c9bbac8e12fb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 68%

---

# Typen von Dimensionen{#dimension-types}

{{eol}}

Auf dem Data Workbench-Server stehen verschiedene Dimensionstypen zur Verfügung. Daher ist es wichtig, den Dimensionstyp zu kennen, wenn Sie eine Dimension zum Erstellen von Metriken, Filtern oder abgeleiteten Dimensionen verwenden.

Insight Server kann die folgenden Dimensionstypen erstellen und verwalten:

<table id="table_1A79B6C57ED145B6AA3BB05DD37AAD1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typen von Dimensionen </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Zählbar </td> 
   <td colname="col2">Ein Dimensionstyp, in dem die Anzahl der Elemente in der Dimension vom System gezählt werden kann. Zählbare Dimensionen müssen aus anderen zählbaren Dimensionen abgeleitet werden. Zählbare Dimensionen können übergeordnete Elemente anderer Dimensionen oder untergeordnete Elemente anderer zählbarer Dimensionen sein. <p>Beispiele: Besucher, Sitzung, Seitenaufruf, Buchung und Bestellung. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einfach </td> 
   <td colname="col2">Eine Dimension, die eine Eins-zu-viele-Beziehung mit einer übergeordneten zählbaren Dimension aufweist. Eine einfache Dimension kann als Darstellung der Eigenschaft von Elementen der übergeordneten Dimension betrachtet werden. <p>Beispiel: Der Besucherverweiser für einen Besucher ist eine einfache Dimension mit der Besucherdimension als übergeordneter Dimension. Jeder Besucher kann über einen Referrer verfügen (der erste HTTP-Referrer), wobei mehrere Besucher denselben Referrer haben können. Daher steht der Referrer im Eins-zu-viele-Bezug zur Besucherdimension. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numerisch </td> 
   <td colname="col2">Eine Dimension, die geordnete, numerische Werte und eine Eins-zu-viele-Beziehung mit einer übergeordneten zählbaren Dimension aufweist. Eine nummerische Dimension kann als Darstellung der nummerischen Eigenschaft von Elementen der übergeordneten Dimension betrachtet werden. Numerische Dimensionen werden häufig zur Definition von Summenmetriken verwendet. <p>Beispiel: Die nummerische Dimension „Sitzungsumsatz“ definiert den Umsatz jeder einzelnen Sitzung in Dollar. Jede Sitzung hat einen eigenen Umsatzbetrag, wobei einige Sitzungen jedoch den gleichen Umsatz aufweisen können, sodass der Sitzungsumsatz in einem Eins-zu-viele-Bezug zur Sitzung steht. Die Metrik "Umsatz"kann als <span class="filepath"> sum(Session_Revenue, Session)</span>, der den Gesamtumsatz für die ausgewählten Sitzungen angibt. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Viele-zu-viele </td> 
   <td colname="col2">Eine Dimension, die eine Viele-zu-viele-Beziehung mit einer übergeordneten zählbaren Dimension aufweist. Eine Viele-zu-viele-Dimension kann als Darstellung eines Satzes von Werten für die einzelnen Elemente der übergeordneten Dimension betrachtet werden. Eine Viele-zu-viele-Dimension ist gleich einer (anonymen) zählbaren Dimension mit ihrer übergeordneten Dimension und einer einfachen Dimension mit einer übergeordneten Dimension des Typs der anonymen zählbaren Dimension. <p>Beispiel: Die Viele-zu-viele-Dimension „Suchbegriff“ hat die übergeordnete Dimension „Sitzung“. Jede Sitzung kann keine oder mehr Suchbegriffe verwenden und ein Suchbegriff kann in mehreren Sitzungen verwendet werden. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2">Eine Dimension, die über eine Eins-zu-eins-Beziehung mit einer übergeordneten zählbaren Dimension verfügt. Die Elementnamen der denormalen Dimension können auf die entsprechenden Elemente der übergeordneten Dimension hinweisen. Eine denormale Dimension speichert einen beliebigen Zeichenfolgenwert für die einzelnen Elemente der übergeordneten Dimension. Denormale Dimensionen können zusammen mit der Segmentexportfunktion von Insight Server verwendet werden, um Details über eine Untergruppe oder ein „Segment“ einer zählbaren Dimension auszugeben. Darüber hinaus können denormale Dimensionen auch in metrischen Formeln und Arbeitsblattvisualisierungen referenziert werden und sie können (mit bestimmten Einschränkungen) zum Definieren von Filtern verwendet werden. <p>Beispiel: Die denormale Dimension „E-Mail-Adresse“ hat die übergeordnete Dimension „Besucher“. Jeder Besucher hat eine E-Mail-Adresse und jedes Element der Dimension „E-Mail-Adresse“ ist mit einem einzelnen Besucher verknüpft. Selbst wenn zwei Besucher über dieselbe E-Mail-Adresse verfügen, sind ihre Adressen verschiedene Elemente der Dimension „E-Mail-Adresse“. Ein Segmentexport kann sich auf die Dimension „E-Mail-Adresse“ beziehen, um die E-Mail-Adresse der einzelnen Besucher in einem Segment auszugeben. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeit </td> 
   <td colname="col2">Eine Dimension, mit der Sie einen Satz periodischer oder absoluter lokaler Zeitdimensionen (z. B. Tag, Wochentag, Stunde, Tageszeit usw.) basierend auf einem von Ihnen angegebenen Zeitstempelfeld erstellen können. Beim Definieren der Zeitdimensionen können Sie auch einen anderen Tag als Montag als ersten Tag der Woche festlegen, indem Sie den Parameter für den Anfangstag der Woche entsprechend einstellen. <p>Beispiel: Die Zeitdimension „Sitzungszeit“ verfügt über die übergeordnete Dimension „Sitzung“. Daher definiert die Dimension einen Satz von Zeitdimensionen (Tag, Wochentag, Stunde, Tageszeit, Monat und Woche), deren Elemente den Zeiten entsprechen, an denen die Sitzungen der Besucher auf der Site begannen. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Abgeleitet </td> 
   <td colname="col2">Abgeleitete Dimensionen werden nicht in der Datensatzkonfiguration basierend auf den verarbeiteten Daten definiert, sondern basierend auf anderen Dimensionen oder Metriken im Profil. Viele abgeleitete Dimensionen werden automatisch erstellt, um verschiedene Visualisierungen zu ermöglichen. <p>Wenn ein Benutzer beispielsweise eine Site oder Prozesskarte erstellt, erstellt Insight Server im Hintergrund eine Dimension "Präfix". Andere Dimensionen, wie zum Beispiel die in Berichten aufgeführten Zeitdimensionen, werden durch Dateien im Dimensionsverzeichnis eines Profils definiert. </p></td> 
  </tr> 
 </tbody> 
</table>
