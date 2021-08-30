---
description: Mit der CRS-Exportfunktion (Customer Record Service) können Sie Data Workbench-Daten in die Adobe Analytics Core Services exportieren, um sie in andere Analytics-Funktionen, einschließlich Reports & Analytics, zu integrieren.
title: Exportieren in Analytics Core Services
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
exl-id: 573085e8-2260-4872-be90-a84ad61145bb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 2%

---

# Exportieren in Analytics Core Services{#exporting-to-analytics-core-services}

Mit der CRS-Exportfunktion (Customer Record Service) können Sie Data Workbench-Daten in die Adobe Analytics Core Services exportieren, um sie in andere Analytics-Funktionen, einschließlich Reports &amp; Analytics, zu integrieren.

>[!NOTE]
>
>Damit die CRS-Exportfunktion funktioniert, muss die Analytics-ID eines Besuchers auf dem Experience Cloud-ID-Dienst (ECID) basieren. Auch wenn die ECID in Data Workbench für einen Besucher angegeben werden kann, funktioniert der CRS-Export für diesen Besucher nicht, wenn sich der Client in der Übergangsphase befindet oder das Cookie des Besuchers nicht durch ECID ersetzt wurde. Weitere Informationen finden Sie unter [Identifizieren von Besuchern](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) und [ID-Dienst-Übergangsphase](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html).

In einer **Detailtabelle** (Rechtsklick **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** in einem Arbeitsbereich) können Sie Attributwerte und die Variablen festlegen, die zur Integration in Reports &amp; Analytics (mithilfe von Adobe Pipeline Services) erforderlich sind.

1. **Klicken Sie mit der rechten Maustaste auf die Tabellenüberschrift und klicken Sie auf &quot;New Customer Record Service&quot;.**

   ![](assets/6_4_CRS.png)

1. **Benennen Sie die Exportdatei und speichern Sie sie.**

   Das Bearbeitungsfenster der Exportdatei wird geöffnet.

1. **** **OpenQuery > CRS-Konfiguration**.
1. **Klicken Sie mit der rechten Maustaste auf CRS-Attribute > Neu hinzufügen .**
1. **** ***Geben Sie CRS-*** **Attributparameter ein**.

   Öffnen Sie den neuen Eintrag und geben Sie Werte im Abschnitt *CRS-Attribute* der Exportdatei ein oder überprüfen Sie diese:

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Attributname</b> </p> </td> 
      <td colname="col2">Name der Variablen <i>Kundenattribute</i>, die in <i>Reports &amp; Analytics</i> angezeigt wird. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Attributtyp</b> </td> 
      <td colname="col2"> <p>Dieser Parameter akzeptiert Werte von (<i>int</i>, <i>string</i>). </p> <p>Hinweis: Wenn ein Attribut <b>not</b> in Analytics abonniert ist: <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">Das Attribut wird mit einem beliebigen gültigen Attributtyp erstellt, der von Analytics unterstützt wird (in dieser Version ist es auf <i>string</i> und <i>int</i> beschränkt). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Wenn ein ungültiger Attributtyp eingegeben wird, erhalten Sie eine Fehlermeldung, dass Analytics nicht abonniert werden konnte. </li> 
      </ul> </p> <p>Wenn ein Attribut <b>bereits</b> in Analytics abonniert ist: </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Vergewissern Sie sich, dass Sie den richtigen Attributtyp für das bereits abonnierte Attribut eingeben. </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Wenn Sie den falschen Typ für das Attribut eingeben, hängt sein Verhalten von der Handhabung der Attributtypen durch Analytics ab. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Feldname</b> </p> </td> 
      <td colname="col2">Name der Dimension oder Metrik, aus der die Attributwerte ausgewählt werden. <p>Hinweis: Der <i><b>Feldname</b></i> unter <i>CRS-Attribute</i> sollte mit dem <b><i>Output Fields</i> &gt; <i>Field Name</i></b> übereinstimmen (der automatisch mit dem ausgewählten Attribut gefüllt wird). Wenn der <i>Feldname</i> ungültig ist, wird der Export nicht ausgeführt. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Rechtsklick **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Geben Sie **[!UICONTROL Report Suite ID]** ein.

   Öffnen Sie den neuen Eintrag und geben Sie im Abschnitt *Report Suite* der Exportdatei Werte ein oder überprüfen Sie diese:

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Report Suite</b> </td> 
      <td colname="col2">ID der Report Suite in <i>Reports &amp; Analytics</i>, die die zu exportierenden <i>Kundenattribut</i>-Variablen angibt. <p> <p>Hinweis: Obwohl Sie mit <i>Reports &amp; Analytics</i> mehrere Report Suites hinzufügen können, exportiert Data Workbench 6.4 nur eine einzige Report Suite, die unter <i>index 0</i> angegeben ist. <p>Der in dieses Feld eingegebene Report Suite-Wert ist die Report Suite-ID (und nicht der Name der Report Suite). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Geben Sie den ECID-Feldparameter ein.

   **ECID-Feld**: Name der Dimension in Ihrem Profil, die die Adobe Experience Cloud ID darstellt. Dies ist ein Pflichtfeld und ungültige Dimensionswerte werden nicht exportiert.

1. (optional) Füllen Sie den Parameter Besucher-ID-Feld aus.

   **Besucher-ID-Feld**: Wenn der Benutzer in seinen Daten eine andere benutzerdefinierte ID für einen Besucher senden möchte, gibt er hier den Namen der Dimension ein, die die benutzerdefinierte Besucher-ID darstellt. Dies ist ein optionales Feld und kann leer gelassen werden.
