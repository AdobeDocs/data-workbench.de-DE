---
description: Verwenden Sie Finder-Bedienfelder in Data Workbench, um Metriken, Dimensionen und Filter auszuwählen. Diese Bedienfelder bieten Suchunterstützung, Sortierungsoptionen und Drag & Drop-Funktionen.
title: Finder
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 1%

---


# Finder{#finders}

Verwenden Sie Finder-Bedienfelder in Data Workbench, um Metriken, Dimensionen und Filter auszuwählen. Diese Bedienfelder bieten Suchunterstützung, Sortierungsoptionen und Drag &amp; Drop-Funktionen.

Ein Finder-Bedienfeld kann in der linken Seitenleiste oder in einem Arbeitsbereich geöffnet werden.

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension Finder </th> 
   <th colname="col2" class="entry"> Metriksuche </th> 
   <th colname="col3" class="entry"> Filter Finder </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eine Liste aller Dimensionen in Ihrem Abfragemodell. </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>Eine Liste aller Metriken in Ihrem Abfragemodell. </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>Eine Liste aller für Ihre Organisation erstellten Filter. </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**So öffnen Sie einen Finder:**

* Klicken Sie mit der rechten Maustaste in einen Arbeitsbereich und wählen Sie **[!UICONTROL Tools]** > **[!UICONTROL Finder]** aus.

   Der Finder-Bereich mit Registerkarten für Metriken, Dimensionen und Filter wird im Arbeitsbereich geöffnet.

* Klicken Sie mit der rechten Maustaste in die linke Seitenleiste und wählen Sie **[!UICONTROL Add]** > **[!UICONTROL Finder]** aus.

   Der Finder-Bereich wird im linken Bereich geöffnet.

**Finder** umfasst die folgenden Funktionen:

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Finder-Funktionen </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Drag &amp; Drop</b> </td> 
   <td colname="col2"> <p> Sie können Dimensionen oder Metriken per Drag-and-Drop aus dem Bedienfeld in eine Visualisierung im Arbeitsbereich ziehen, um die Dimension zu ändern oder neue Metriken hinzuzufügen. </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">Halten Sie die Schlüssel <span class="uicontrol"> &lt;Strg&gt;</span> und <span class="uicontrol"> &lt;Alt&gt;</span> gedrückt und wählen Sie die Dimension oder Metrik aus dem Finder-Bereich aus. </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">Ziehen Sie eine neue Dimension aus dem Bereich und legen Sie sie in der Visualisierung ab, um Dimensionen zu ändern oder hinzuzufügen. </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">Um Metriken hinzuzufügen, ziehen Sie eine neue Metrik aus dem Bereich und legen Sie sie in der Metrikkopfzeile der ausgewählten Visualisierung ab. </li> 
    </ol> <p>Dies funktioniert für alle relevanten Visualisierungen, einschließlich Tabellen, Besuchercluster, Korrelationsmatrix, Streudiagramme und des 2D-Balkendiagramms (je nach Achse). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Durchsuchen</b> </td> 
   <td colname="col2">Mit einem Feld <span class="uicontrol"> Suchen</span> in den Finder-Bereichen können Sie Namen nach Dimensionen, Metriken und Filtern filtern. 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>Musterabgleich (einfache glob-Suche). Beginnen Sie mit der Eingabe des Namens einer erforderlichen Dimension, Metrik oder Filterentität in das Suchfeld. Nur übereinstimmende Zeichenfolgen, die an einer beliebigen Stelle im Namen enthalten sind, werden gefiltert und im Bereich Finder angezeigt. </p> <p>Geben Sie beispielsweise Folgendes ein: </p> <code><b>Search:</b>click</code> <p>Sie können die folgenden Ergebnisse im Dimensionen-Finder erhalten: </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>Bei der Standardmusterübereinstimmung können Sie die Platzhalterzeichen verwenden, z. B. . (Punkt), "?" , und "*" (Stern). </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>Reguläre Ausdrücke. Komplexere reguläre Ausdrücke werden auch für zusätzliche Suchfunktionen unterstützt. Fügen Sie das Präfix "re:"vor Ihrem Suchbegriff (keine Leerzeichen) hinzu, um es als regulären Ausdruck zu interpretieren. </p> <p>Geben Sie beispielsweise Folgendes ein: </p> <code><b>Search:</b>re.*ip</code> <p>Sie können die folgenden Ergebnisse im Dimensionen-Finder erhalten: </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>Detaillierte Suchinformationen finden Sie unter <a href="https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external"> reguläre Ausdrücke</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Dimension Typ</b> </td> 
   <td colname="col2">Im Tab Dimension können Sie mit der rechten Maustaste auf die Registerkartenüberschrift klicken, um sie nach Dimensionstyp zu sortieren. <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">Attribute: Dimensionen, die auf den Eigenschaften des Besuchers, der Produkte, der Geografie, der Zeit, des Videos und anderen Attributen basieren. </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">Cluster - Dimensionen, die im Cluster-Builder erstellt wurden. </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">Bewertungen - Dimensionen, die innerhalb der Tendenzauswertung erstellt wurden. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Beschriftung</b> </td> 
   <td colname="col2">In jeder Registerkarte können Sie mit der rechten Maustaste klicken und <span class="uicontrol"> Beschriftung</span> auswählen, um den Finder-Bereich umzubenennen. <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>Die Standardbezeichnungen für Dimensionen, Metriken und Filter können in einen Registerkartennamen geändert werden, der den Konventionen Ihres Unternehmens entspricht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Element hinzufügen</b> </td> 
   <td colname="col2">Sie können auf jeder Registerkarte mit der rechten Maustaste klicken und <span class="uicontrol"> Element hinzufügen</span> auswählen, um eine Tabelle zu öffnen und Dimensionen, Metriken und Filter manuell hinzuzufügen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Suchleiste</b> </td> 
   <td colname="col2">Klicken Sie mit der rechten Maustaste in die Leiste <span class="uicontrol"> Finders</span> in der linken Seitenleiste, um ein Menü für zusätzliche Funktionen zu öffnen. <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Close</b> </td> 
   <td colname="col2">Klicken Sie mit der rechten Maustaste in die Leiste <span class="uicontrol"> Finders</span> und wählen Sie <span class="uicontrol"> Schließen</span> aus, um einen Finder-Bereich zu schließen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Speichern</b> </td> 
   <td colname="col2">Speichern Sie die Liste lokal, indem Sie mit der rechten Maustaste in die Kopfzeilenleiste klicken und die Option <span class="uicontrol"> Speichern</span> auswählen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Exportieren</b> </td> 
   <td colname="col2">Sie können eine Liste ausgewählter Dimensionen, Metriken oder Filter aus dem Finder-Bereich exportieren, indem Sie mit der rechten Maustaste in der Suchleiste klicken und <span class="uicontrol"> Export</span> aus dem Menü auswählen. <p> Fügen Sie einen Namen hinzu und exportieren Sie diese in Microsoft Excel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Copy</b> </td> 
   <td colname="col2"> Kopieren Sie eine Liste mit Dimensionen, Metriken oder Filtern. Sie können als Datei oder als Grafik in dunklem Hintergrund, heller Hintergrund oder Monochrom kopieren. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Minimieren</b> </td> 
   <td colname="col2"> Minimieren Sie den Finder-Bereich. Es wird nur die Suchleiste angezeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Borderless</b> </td> 
   <td colname="col2"> Zeigt einen Bereich ohne Randlinien für Finder im Arbeitsbereich an (jedoch nicht in der linken Seitenleiste). </td> 
  </tr> 
 </tbody> 
</table>

