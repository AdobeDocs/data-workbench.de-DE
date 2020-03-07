---
description: Mit der Customer Record Service-(CRS-)Exportfunktion können Sie Data Workbench-Daten in die Adobe Analytics Core Services exportieren, um sie in die Funktionen anderer Analytics, einschließlich Reports & Analysen, zu integrieren.
title: Exportieren in Analytics-Hauptdienste
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportieren in Analytics-Hauptdienste{#exporting-to-analytics-core-services}

Mit der Customer Record Service-(CRS-)Exportfunktion können Sie Data Workbench-Daten in die Adobe Analytics Core Services exportieren, um sie in die Funktionen anderer Analytics, einschließlich Reports &amp; Analysen, zu integrieren.

>[!NOTE]
>
>Damit die CRS-Exportfunktion funktioniert, muss die Analytics-ID eines Besuchers auf dem Experience Cloud ID-Dienst (ECID) basieren. Obwohl die ECID für einen Besucher in Data Workbench aufgefüllt werden kann, funktioniert der CRS-Export für diesen Besucher nicht, wenn sich der Client in der Übergangsphase befindet oder das Cookie des Besuchers nicht durch die ECID ersetzt wurde. Weitere Informationen finden Sie unter [Identifizieren von Besuchern](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) und Übergangsphase für den [ID-Dienst](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html).

In einer **Detailtabelle** (Rechtsklick **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** in einem Arbeitsbereich) können Sie Attributwerte und die Variablen festlegen, die zur Integration in Reports &amp; Analysen von Analytics erforderlich sind (mithilfe von Adobe Pipeline Services).

1. **Klicken Sie mit der rechten Maustaste auf die Tabellenüberschrift und dann auf Neuer Kundendatensatzdienst.**

   ![](assets/6_4_CRS.png)

1. **Benennen Sie die Exportdatei und speichern Sie sie.**

   Das Fenster zum Bearbeiten der Exportdatei wird geöffnet.

1. **Öffnen Sie** **Abfrage > CRS-Konfiguration**.
1. **Klicken Sie mit der rechten Maustaste auf CRS-Attribute > Neu hinzufügen.**
1. **Geben Sie** ***CRS-Attributwerte*** - **Parameter** ein.

   Öffnen Sie den neuen Eintrag und geben Sie Werte im Abschnitt &quot; *CRS-Attribute* &quot;der Exportdatei ein oder überprüfen Sie diese:

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Attributname</b> </p> </td> 
      <td colname="col2">Name der Variablen <i>Kundenattribute</i> , die in <i>Reports &amp; Analysen</i>angezeigt wird. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Attributtyp</b> </td> 
      <td colname="col2"> <p>Dieser Parameter akzeptiert Werte von (<i>int</i>, <i>string</i>). </p> <p>Hinweis: Wenn ein Attribut in Analytics <b>nicht</b> abonniert wird: <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">Das Attribut wird mit jedem gültigen Attributtyp erstellt, der von Analytics unterstützt wird (in dieser Version ist es auf nur <i>Zeichenfolge</i> und <i>int</i>beschränkt). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Wenn ein ungültiger Attributtyp eingegeben wird, erhalten Sie eine Fehlermeldung, dass Analytics nicht abonniert werden konnte. </li> 
      </ul> </p> <p>Wenn ein Attribut in Analytics <b>bereits</b> abonniert ist: </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Achten Sie darauf, den richtigen Attributtyp für das bereits abonnierte Attribut einzugeben. </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Wenn Sie den falschen Typ für das Attribut eingeben, hängt sein Verhalten von der Handhabung der Attributtypen durch Analytics ab. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Feldname</b> </p> </td> 
      <td colname="col2">Name der Dimension oder Metrik, aus der die Attributwerte ausgewählt werden. <p>Hinweis: Der <i><b>Feldname</b></i> unter " <i>CRS-Attribute</i> "sollte mit dem Wert " <b><i>Ausgabefelder</i> "&gt; " <i>Feldname</i></b> "identisch sein (der automatisch anhand des ausgewählten Attributs ausgefüllt wird). Wenn der <i>Feldname</i> ungültig ist, wird der Export nicht ausgeführt. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Enter the **[!UICONTROL Report Suite ID]**.

   Öffnen Sie den neuen Eintrag und geben Sie Werte im Abschnitt *Report Suite* der Exportdatei ein oder überprüfen Sie die Werte:

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Report Suite</b> </td> 
      <td colname="col2">ID der Report Suite in <i>Reports &amp; Analysen</i> , die die zu exportierenden <i>Kundenattributvariablen</i> identifiziert. <p> <p>Hinweis: Obwohl <i>Reports &amp; Analysen</i> mehrere Report Suites hinzufügen können, exportiert Data Workbench 6.4 nur eine einzige Report Suite, die an <i>Index 0</i>identifiziert wurde. <p>Der in dieses Feld eingegebene Report Suite-Wert ist die Report Suite-ID (und nicht der Name der Report Suite). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Geben Sie den ECID-Feldparameter ein.

   **ECID-Feld**: Name der Dimension in Ihrem Profil, die die Adobe Experience Cloud ID darstellt. Dies ist ein obligatorisches Feld, und ein ungültiger eingegebener Dimensionswert wird nicht exportiert.

1. (Optional) Füllen Sie den Parameter &quot;Besucher-ID-Feld&quot;aus.

   **Besucher-ID-Feld**: Wenn der Benutzer eine andere benutzerdefinierte ID für einen Besucher in seinen Daten senden möchte, geben Sie hier den Namen der Dimension ein, die die benutzerdefinierte Besucher-ID darstellt. Dies ist ein optionales Feld, das leer gelassen werden kann.
