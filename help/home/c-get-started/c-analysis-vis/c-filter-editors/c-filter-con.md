---
description: Informationen zum Arbeiten mit Filterbedingungen, einschließlich Erstellen eines neuen Filters und Hinzufügen einer Bedingung zu einem neuen Filter.
title: Arbeiten mit Filterbedingungen
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
exl-id: 15745b0c-2754-4f8b-acfd-a6bd5886ecf8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 1%

---

# Arbeiten mit Filterbedingungen{#working-with-filter-conditions}

Informationen zum Arbeiten mit Filterbedingungen, einschließlich Erstellen eines neuen Filters und Hinzufügen einer Bedingung zu einem neuen Filter.

## Filter erstellen {#section-70ba51ae625e493fa3ca70b93ffba406}

* Öffnen Sie einen Filter-Editor in Ihrem Arbeitsbereich, indem Sie mit der rechten Maustaste auf **[!UICONTROL Add Visualization]** > **[!UICONTROL Filter Editor]** klicken.

   -oder-

* Wenn Sie bereits einen Filter-Editor geöffnet und einen Filter geladen haben, klicken Sie mit der rechten Maustaste auf den Namen des aktuellen Filters und klicken Sie auf **[!UICONTROL New Blank Filter]**.

## Hinzufügen einer Bedingung zu einem neuen Filter {#section-50986db80f1148c489630a8a63fe9f28}

1. Erstellen Sie einen neuen Filter. Stellen Sie sicher, dass der Designfilter hervorgehoben ist (im Gegensatz zu &quot;Filter anwenden&quot;), was angibt, dass Sie im Designfiltermodus arbeiten.
1. Klicken Sie mit der rechten Maustaste in den Bereich, der mit **[!UICONTROL Right-click to build filter]** markiert ist, und wählen Sie eine der folgenden Optionen aus:

   * Um einen Einschlussfilter zu erstellen, klicken Sie auf **[!UICONTROL Include group with]**.
   * Um einen Ausschlussfilter zu erstellen, klicken Sie auf **[!UICONTROL Exclude group with]**.

1. Wählen Sie den Bedingungstyp aus, der dem Filter hinzugefügt werden soll.

   Die folgende Tabelle enthält Beschreibungen der verfügbaren Filterbedingungen:

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Bedingungstyp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Arbeitsbereichsauswahl </p> </td> 
   <td colname="col2"> <p>Definiert eine Filterbedingung basierend auf den im Arbeitsbereich ausgewählten Elementen. Diese Option ist nur verfügbar, wenn eine oder mehrere Auswahlen im Arbeitsbereich vorhanden sind. </p> <p>Um weitere Informationen zur Auswahl anzuzeigen, klicken Sie mit der rechten Maustaste auf die Bedingung und klicken Sie auf <span class="uicontrol"> Details anzeigen</span>. Für die Bedingung wird ein Callout angezeigt. </p> <p>Wenn Sie eine andere Auswahl im Arbeitsbereich vornehmen, können Sie die Auswahl als Unterbedingung der ersten Auswahl hinzufügen. Die Auswahlen werden als logische UNDs gruppiert. Daher müssen die von der Bedingung eingeschlossenen oder ausgeschlossenen Daten alle Arbeitsbereichsauswahlen erfüllen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mindestens </p> </td> 
   <td colname="col2">Definiert eine Filterbedingung, die auf dem Vorhandensein von mindestens einem Element (eines beliebigen Elements) einer von Ihnen gewählten Dimension basiert. Klicken Sie zum Bearbeiten der Bedingung mit der rechten Maustaste auf die Bedingung und klicken Sie auf <span class="uicontrol"> Bedingung ändern in . </span> Klicken Sie auf eine der verfügbaren Dimensionen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Formel </p> </td> 
   <td colname="col2"> <p>Definiert eine Filterbedingung anhand der eingegebenen Formel. Sie müssen die entsprechende Syntax verwenden, damit der Filter funktioniert. </p> <p> <p>Hinweis: Informationen zur Syntax zum Definieren von Filtern finden Sie unter <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntax für Filterausdrücke</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrikwert </p> </td> 
   <td colname="col2"> <p>Definiert eine Filterbedingung basierend auf einem von Ihnen angegebenen Metrikwert. </p> <p>Gehen Sie wie folgt vor, um die Bedingung zu definieren: 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> [Ebene auswählen]</span> &gt; <span class="uicontrol"> Ebene ändern</span> , um Ebene und Metrik aus einer Liste von Dimensionen in Ihrem Datensatz auszuwählen. </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> [Metrik auswählen]</span> &gt; <span class="uicontrol"> Metrik ändern</span> , um die Metrik aus einer Liste von Metriken in Ihrem Datensatz auszuwählen. </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">Klicken Sie mit der rechten Maustaste auf "kleiner als"und klicken Sie auf <span class="uicontrol"> Vergleich ändern</span>, um eine der verfügbaren Vergleichsbedingungen auszuwählen (kleiner als, größer, genau, mindestens oder höchstens). </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">Geben Sie den gewünschten Wert für die Metrik ein. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>first/last </p> </td> 
   <td colname="col2"> <p>Definiert einen Filter, mit dem Sie eine Ebene mit einer bestimmten Dimension ein- oder ausschließen können. Sie können beispielsweise einen ersten/letzten Filter angeben, der ein- oder ausgeschlossen werden soll: </p> <p>Sitzungen, deren letzte Seitenansicht eine Seite von <span class="filepath"> /hme/rts/our Rates</span> hat. </p> <p>So definieren Sie eine Erst-/Letzte Bedingung: 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">Wählen Sie <span class="uicontrol"> Gruppe mit</span> oder <span class="uicontrol"> Gruppe mit</span> ausschließen &gt; <span class="uicontrol"> first/last</span> als neue Bedingung im Filter-Editor aus. </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> [Container auswählen]</span> &gt; <span class="uicontrol"> Container</span> ändern , um den Container auszuwählen. </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">Klicken Sie mit der rechten Maustaste auf <span class="uicontrol"> first</span> oder <span class="uicontrol"> last</span> , um die Ebene anzugeben. </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">Klicken Sie mit der rechten Maustaste, um eine Dimension anzugeben, und geben Sie dann einen Wert in das verfügbare Feld ein. </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">Klicken Sie auf <span class="uicontrol">Übernehmen</span>. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Der Filter in diesem Beispiel definiert einen ersten/letzten Filter für Benutzer, deren letzte Seitenansicht [!DNL /hme/rts/Our Rates] war:

![](assets/client-fil2.png)

1. (Optional) Um weitere Bedingungen zu Ihrem Filter hinzuzufügen, klicken Sie mit der rechten Maustaste in den Bereich des Fensters, in dem Sie den Filter erstellen, und wählen Sie den Filtertyp (siehe Schritt 2) und die Bedingungsregel (siehe Schritt 3) aus.

   >[!NOTE]
   >
   >Mehrere Einschlussbedingungen werden als logische ODERs gruppiert. Daher müssen die vom Filter enthaltenen Daten mindestens eine der definierten Aufnahmebedingungen erfüllen. Mehrere Ausschlussbedingungen werden auch als logische ODERs gruppiert. Damit Daten ausgeschlossen werden können, müssen sie mindestens eine der Ausschlussbedingungen erfüllen.

Der Filter in diesem Beispiel definiert eine Teilmenge von Daten, die aus Filmanbietern (Anwendern) bestehen, die zwar viele Filme bewertet, aber keinem Film eine hohe Punktzahl gegeben haben (4 oder 5). Dieser Filter (entsprechend mit dem Namen Sehr schwer zu empfehlen) besteht aus zwei Bedingungen:

* **Bedingung für einen Metrikwert:** Die Bedingung umfasst Benutzer, die mindestens 500 Filme bewertet haben.
* **Eine Workspace-Auswahlbedingung:** Die Bedingung schließt Benutzer aus, die einem Film eine Punktzahl von 4 oder 5 gegeben haben. Die Berechnung zeigt an, dass 4 und 5 die aus der Score-Dimension ausgewählten Elemente waren.

![](assets/vis_FilterEditor_ExampleMovies.png)

## Filterbedingung {#section-3092e0d7ac624885b8fe24616279de13} löschen

>[!NOTE]
>
>Sie können Bedingungen nur löschen, wenn Sie im Designfiltermodus arbeiten. Wenn Sie einen Filter auf Ihren Arbeitsbereich angewendet haben, müssen Sie auf Design Filter klicken, um in den Designfiltermodus zurückzukehren, bevor Sie eine oder mehrere Filterbedingungen löschen können.

* Klicken Sie auf **x** links neben der Bedingung, um sie zu löschen.

## Bearbeiten einer Bedingungsbeschreibung {#section-5015fd2c88ed4b6a95be7f0d53be2db0}

Sie können allen Bedingungen, die Sie einem Filter hinzufügen, Beschreibungen hinzufügen. Sie können die Beschreibungen nach Bedarf bearbeiten oder entfernen.

>[!NOTE]
>
>Beschreibungen von Bedingungen werden nur angezeigt, wenn Sie im Designfiltermodus arbeiten.

* Klicken Sie mit der rechten Maustaste auf die Bedingung und klicken Sie auf **[!UICONTROL Edit description]**.

   * Um eine Beschreibung hinzuzufügen oder zu bearbeiten, geben Sie sie in das Feld [!DNL Edit condition description] ein. Die Beschreibung wird in Anführungszeichen oberhalb der Bedingung im Fenster des Filtereditors angezeigt.

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* Um eine Beschreibung zu entfernen, klicken Sie auf **[!UICONTROL Remove description]**. Die Bedingung verbleibt im Fenster des Filtereditors.
