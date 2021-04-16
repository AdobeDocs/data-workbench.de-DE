---
description: Text oder Ausdrücke können in eine beliebige Zelle eines Arbeitsblatts eingegeben werden.
title: Arbeiten mit Daten in Arbeitsblättern
uuid: c2331fa5-aa07-4622-8f44-5124c22dffcb
exl-id: 40d9211b-8f5c-4051-8f93-638ffacf45bd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 3%

---

# Arbeiten mit Daten in Arbeitsblättern{#work-with-data-in-worksheets}

Text oder Ausdrücke können in eine beliebige Zelle eines Arbeitsblatts eingegeben werden.

Allen Ausdrücken in einem Arbeitsblatt wird ein Gleichheitszeichen (=) vorangestellt, es sei denn, es wird [!DNL eval( )] verwendet, wodurch der Text in der referenzierten Zelle als Ausdruck behandelt wird.

Eine vollständige Liste der Metrik-, Dimensions- und Filtersyntax-Regeln finden Sie unter [Abfrage-Syntax](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

**So geben Sie Daten in ein Arbeitsblatt ein**

1. Klicken Sie zweimal auf eine Zelle im Arbeitsblatt, um in den Bearbeitungsmodus zu wechseln. Die ausgewählte Zelle wird hervorgehoben.
1. Geben Sie die gewünschten Daten in die Zelle ein oder fügen Sie sie ein.

**So kopieren Sie eine Zelle in eine andere**

1. Klicken Sie mit der rechten Maustaste auf die Zelle, die die zu kopierenden Daten enthält, und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie mit der rechten Maustaste auf die Zelle, in die Sie die kopierten Daten einfügen möchten, und klicken Sie auf **[!UICONTROL Paste]**.

Data Workbench aktualisiert automatisch die Verweise in der neuen Zelle, um auf die entsprechenden Spalten und Zeilen zu verweisen.

**So kopieren Sie Zellen aus einer Gruppe in eine andere**

1. Wählen Sie die Zellen aus, die die zu kopierenden Daten enthalten.
1. Klicken Sie mit der rechten Maustaste auf die Zellen, die die zu kopierenden Daten enthalten, und klicken Sie auf **[!UICONTROL Copy]**.
1. Klicken Sie mit der rechten Maustaste auf die erste Zelle, in die Sie die kopierten Daten einfügen möchten, und klicken Sie auf **[!UICONTROL Paste]**. Die Daten werden in die erste Zelle und darunter eingefügt.

Data Workbench aktualisiert automatisch die Verweise in der neuen Zelle, um auf die entsprechenden Spalten und Zeilen zu verweisen.

**So fügen Sie eine Spalte ein**

* Klicken Sie mit der rechten Maustaste auf eine Spalte und klicken Sie auf **[!UICONTROL Insert Column]**. Die neue Spalte wird links neben der ausgewählten Spalte eingefügt.

**So löschen Sie eine Spalte**

* Klicken Sie mit der rechten Maustaste auf die Spalte, die Sie löschen möchten, und klicken Sie auf **[!UICONTROL Delete Column]**. Die Spalte wird entfernt.

**So fügen Sie eine Zeile ein**

* Klicken Sie mit der rechten Maustaste auf eine Zeile und klicken Sie auf **[!UICONTROL Insert Row]**. Die neue Zeile wird oberhalb der ausgewählten Zeile eingefügt.

**So löschen Sie eine Zeile**

* Klicken Sie mit der rechten Maustaste auf die zu löschende Zeile und klicken Sie auf **[!UICONTROL Delete Row]**. Die Zeile wird entfernt.

**So ändern Sie die Größe einer Spalte**

1. Platzieren Sie in der Spaltenüberschrift den Cursor über die Trennlinie rechts neben der Spalte, deren Größe Sie ändern möchten.
1. Klicken und ziehen Sie nach rechts, um die Spaltenbreite zu erhöhen, oder nach links, um die Spaltenbreite zu verringern.

**So formatieren Sie eine Zelle**

1. Klicken Sie mit der rechten Maustaste auf die Zelle und klicken Sie auf **[!UICONTROL Format]**.

   ![](assets/mnu_Worksheet_Format.png)

1. Klicken Sie im Menü der verfügbaren Optionen auf das gewünschte Format:

<table id="table_5788E01E52CC44E7927A0D23760D9EDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menüoption </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nummer </p> </td> 
   <td colname="col2"> <p>Wendet das ausgewählte numerische Format auf Ihre Daten an, z. B. Uhrzeit, Datum, Prozentsatz oder Dezimalzahl. </p> <p>Klicken Sie auf <span class="uicontrol"> Default</span>, um die ausgewählte Formatierung zu entfernen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Blocksatz </p> </td> 
   <td colname="col2"> <p>Richtet die Daten in der Zelle links, zentriert oder rechts aus. Die Standardausrichtung bleibt erhalten. </p> <p>Klicken Sie auf <span class="uicontrol"> Default</span>, um die ausgewählte Formatierung zu entfernen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Farbe </p> </td> 
   <td colname="col2"> <p>Wendet die ausgewählte Schriftfarbe auf die Daten in der Zelle an. Die Standardschriftfarbe ist weiß. </p> <p>Klicken Sie auf <span class="uicontrol"> Default</span>, um die ausgewählte Formatierung zu entfernen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indikator </p> </td> 
   <td colname="col2"> <p>Erstellt eine Metrikanzeige mithilfe dieser Zelle. Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#concept-f0e911b23b2c4e8da3e1ea7b9ae04183"> Erstellen von Metrikindikatoren</a>. </p> <p>Klicken Sie auf <span class="uicontrol"> Default</span>, um die ausgewählte Formatierung zu entfernen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eingabezelle </p> </td> 
   <td colname="col2"> <p>Macht die ausgewählte Zelle zu einer Eingabezelle. Weitere Informationen finden Sie unter <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-input-cells.md#concept-08cd2c05a28a43dd9f7698b37e23e590"> Erstellen von Eingabezellen</a>. </p> <p>Klicken Sie auf <span class="uicontrol"> Default</span>, um die ausgewählte Formatierung zu entfernen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Tastaturbefehle {#section-05301f4d2c60418e86902635a7aeee20}

In Arbeitsblättern können Sie viele der grundlegenden Tastenkombinationen zur Bearbeitung verwenden, die Sie in jedem Texteditor wie Notepad oder Microsoft Word verwenden können.

In der folgenden Tabelle werden die grundlegenden Tastaturbefehle Liste, die Sie bei der Eingabe von Daten in ein Arbeitsblatt verwenden können.

<table id="table_8E6F73F253B3451CA1DE45EE4F4E69EF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tastaturbefehl </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pfeiltasten </p> </td> 
   <td colname="col2"> <p>Wechseln Sie mit den Pfeiltasten nach oben, unten, links und rechts von der Zelle zur Zelle im Arbeitsblatt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F2 </p> </td> 
   <td colname="col2"> <p>Bearbeiten Sie die Zelle, indem Sie den Cursor in die ausgewählte Zelle setzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eingabetaste </p> </td> 
   <td colname="col2"> <p>Schließt die Bearbeitung der ausgewählten Zelle ab. Der Cursor wird aus der Zelle entfernt und der Zelleninhalt spiegelt Ihre Bearbeitung wider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esc </p> </td> 
   <td colname="col2"> <p>Abbrechen der Bearbeitung der ausgewählten Zelle Der Cursor wird aus der Zelle entfernt, und der Zelleninhalt wird auf das zurückgesetzt, was er vor Beginn der Bearbeitung war. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Löschen </p> </td> 
   <td colname="col2"> <p>Löschen Sie den Inhalt der Zelle(n). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Strg+A </p> </td> 
   <td colname="col2"> <p>Wählen Sie den Inhalt der Zelle aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Strg+c </p> </td> 
   <td colname="col2"> <p>Kopieren Sie den Inhalt der Zelle(n). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Strg+x </p> <p>Umschalt+Löschen </p> </td> 
   <td colname="col2"> <p>Kopieren und entfernen Sie den Inhalt der Zelle(n). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Strg+V </p> <p>Umschalt+Einfügen </p> </td> 
   <td colname="col2"> <p>Fügen Sie den Inhalt der Zellen ein, die Sie in die ausgewählten Zellen kopiert haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Strg+z </p> </td> 
   <td colname="col2"> <p>Rückgängigmachen der Eingabe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Strg+Umschalt+z </p> </td> 
   <td colname="col2"> <p>Wiederholen Sie die Eingabe. </p> </td> 
  </tr> 
 </tbody> 
</table>
