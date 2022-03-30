---
description: Diese Datei dient nicht nur als Arbeitsblatt, sondern auch als Datensatz Ihrer Experimententscheidungen.
solution: Analytics
title: Tabelle für den Experimentaufbau
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
exl-id: 554790ab-1182-4481-87b0-e768ea769ddf
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# Tabelle für den Experimentaufbau{#experiment-design-spreadsheet}

Diese Datei dient nicht nur als Arbeitsblatt, sondern auch als Datensatz Ihrer Experimententscheidungen.

Wenn Sie Hilfe beim Entwerfen Ihres Experiments benötigen, können Sie die von Adobe bereitgestellte Tabelle zum Experimententwurf verwenden (standardmäßig &quot;VS Controlled Experiment Design.xls&quot;genannt).

Die Tabelle mit dem Experimententwurf kann nur nützliche statistische Rückschlüsse liefern, wenn die betreffende Metrik als Prozentsatz der Besucher definiert ist, die bestimmte Kriterien erfüllen. Dies ist also nur beim Testen einer besucherbasierten Metrikhypothese nützlich.

**So entwerfen Sie Ihr Experiment mit der Experimententwurfsdatei**

1. Wenn Sie über Administratorzugriff auf Ihre Web- oder Anwendungsserver verfügen, navigieren Sie zum [!DNL Sensor] Installationsordner auf einem beliebigen [!DNL Sensor] Computer in Ihrem Webcluster. Wenn Sie keinen Administratorzugriff haben, wenden Sie sich an Ihren Adobe Account Manager, um die Datei anzufordern.
1. Öffnen Sie die Datei VS Controlled Experiment Design.xls . (Sie können diese Datei bei Bedarf umbenennen.)

   Die Tabelle auf der folgenden Seite ist ein Beispiel dafür, wie Sie das Arbeitsblatt bei der Vorbereitung auf den Test der in diesem Handbuch verwendeten Beispielhypothese abschließen.

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. Geben Sie Text oder Werte für alle blauen Felder in dieser Datei ein, die in der folgenden Tabelle beschrieben werden. Die berechneten Felder werden in der zweiten Tabelle definiert.

<table id="table_C343F7A4BF3D4E0E9A5E9739EC7C2E10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In diesem Feld.. </th> 
   <th colname="col2" class="entry"> Legen Sie  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Experimenttitel </td> 
   <td colname="col2"> Ein beschreibender Name für Ihr Experiment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Experimentbeschreibung </td> 
   <td colname="col2"> Eine Textbeschreibung des Experiments. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zu untersuchende Metrik </td> 
   <td colname="col2"> <p>Der Name der Metrik, auf der das Experiment basiert. </p> <p>Beispiel: Besucherkonversion </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrikdefinition </td> 
   <td colname="col2"> <p>Die Definition der Metrik, auf der das Experiment basiert. </p> <p>Format: Besucher[X]/Besucher </p> <p>Beispiel: <span class="filepath"> Visitors[URI='conversionpage.asp']/Visitors</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgesehene Startzeit </td> 
   <td colname="col2"> Datum und Uhrzeit des Beginns des Experiments. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vorgesehene Endzeit </td> 
   <td colname="col2"> Datum und Uhrzeit des Endes des Experiments. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anwendbare Auswahlmöglichkeiten </td> 
   <td colname="col2"> (Optional) Der Dimensionsname und der Elementsatz bzw. der Bereich, mit dem Sie den Datensatz weiter segmentieren möchten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Experiment-URIs </td> 
   <td colname="col2"> Die an Ihrer Hypothese beteiligten URIs. Sie definieren die aktuellen URIs für die Kontrollgruppe und die alternativen URIs, die Sie für die Testgruppe(n) erstellt haben oder erstellen werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erwartete Metriken für Anwendungsauswahl </td> 
   <td colname="col2"> Überschrift für die Metrikwerte, die Sie für Ihre Website erwarten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durchschnittliche Besucher pro Tag </td> 
   <td colname="col2"> Durchschnittliche Anzahl der Besucher Ihrer Website pro Tag. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besucherkonversion </td> 
   <td colname="col2"> Die durchschnittliche Besucherkonversionsrate für Ihre Website. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Experiment bestimmt, ob der Metrikname für die Testgruppen ... </td> 
   <td colname="col2"> Überschrift für den Vergleich der Metrikwerte. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Größer als der Wert für die Kontrollgruppe? </td> 
   <td colname="col2"> Setzen Sie dieses Feld auf True , wenn Sie feststellen möchten, dass die Metrik der Testgruppe während des Experiments erhöht wurde. Setzen Sie dieses Feld auf False , um die Anzahl der Besucher zu reduzieren, die zum Zeichnen von Schlussfolgerungen benötigt werden. Adobe empfiehlt, dass Sie True festlegen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kleiner als der Wert für die Kontrollgruppe? </td> 
   <td colname="col2"> Setzen Sie dieses Feld auf True , wenn Sie feststellen möchten, dass die Metrik der Testgruppe während des Experiments reduziert wurde. Adobe empfiehlt, dass Sie True festlegen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mindestens nach (Erkennungsniveau) </td> 
   <td colname="col2"> Der Prozentsatz, um den die Metrik für die Testgruppe höher oder kleiner als der für die Kontrollgruppe sein soll. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mit einem Konfidenzniveau von mindestens </td> 
   <td colname="col2"> Das gewünschte Konfidenzniveau für die Testgruppenwerte. Das Konfidenzniveau bestimmt die Anzahl der Falsch-Positiv-Werte, um die Wahrscheinlichkeit zu messen, dass die angegebene Erwartung wahr ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> und ein Leistungsniveau von </td> 
   <td colname="col2"> Der gewünschte Leistungsgrad für die Testgruppenwerte. Das Leistungsniveau bestimmt die Anzahl der falschen Negativen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % der Besucher </td> 
   <td colname="col2"> Überschrift für die Prozentwerte der Besucher. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Testgruppe </td> 
   <td colname="col2"> Prozentsatz der Besucher, die Sie in die Testgruppe aufnehmen möchten. Sie können mit dieser Zahl wiedergeben, bis der Wert im Feld "Gesamt (normalerweise 100 %)"im Abschnitt "Besucher"dem Wert im Feld "Mindestbesucher erforderlich"(Test+Kontrollgruppen) entspricht oder darüber liegt. Die beiden Werte sind in der folgenden Tabelle beschrieben. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kontrollgruppe </td> 
   <td colname="col2"> Prozentsatz der Besucher, die Sie in die Kontrollgruppe aufnehmen möchten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Andere Designs </td> 
   <td colname="col2"> Alle Notizen, die Sie für künftige Referenzzwecke speichern möchten. </td> 
  </tr> 
 </tbody> 
</table>

Die Berechnung der übrigen Felder erfolgt auf der Basis der eingegebenen Werte. Sie werden in der folgenden Tabelle beschrieben.

| Feld | Beschreibung |
|---|---|
| Erwartete Metriken für Anwendungsauswahl | Überschrift für die Metrikwerte, die Sie für Ihre Website erwarten. |
| Erwartete Besucher pro Zeitraum | Dieses Feld wird normalerweise automatisch von der Tabelle berechnet. Es wird davon ausgegangen, dass die Website an den meisten Tagen viel mehr neue Besucher erhält als wiederkehrende Besucher. Ist dies nicht der Fall, sollte die Berechnung dieser Zelle mit der tatsächlichen Anzahl der Besucher überschrieben werden, die während des Experiments erwartet werden. |
| Berechnete z-Punktzahl für Fehler Typ I | Der z-Wert für ein falsch-positives Ergebnis. Dies ist eine statistische Zwischenberechnung. |
| Berechnete z-Punktzahl für Fehler Typ II | Der z-Wert für ein falsch negatives Ergebnis. Dies ist eine statistische Zwischenberechnung. |
| Erforderliche Mindestbesucher (Test- und Kontrollgruppen) | Mindestanzahl der Besucher, die in Ihrem Experiment benötigt werden, um Ihr spezifiziertes Konfidenzniveau, Leistungsniveau und Z-Wert zu erreichen, ausgedrückt als Prozentsatz des Werts im Feld Erwartete Besucher pro Zeitraum . |
| Erforderliche Mindestbesucher (Test- und Kontrollgruppen) | Minimale Anzahl der Besucher, die für Ihr Experiment erforderlich sind, um Ihr spezifiziertes Konfidenzniveau, Leistungsniveau und z-Wert zu erreichen. Dieser Wert muss kleiner oder gleich dem Wert im Feld Gesamtsumme (normalerweise 100 %) im Abschnitt Besucher sein. |
| Minimale Experimentdauer (Tage) | Die Mindestanzahl von Tagen, die Sie benötigen, um Ihr Experiment ausführen zu können, um Ihr bestimmtes Konfidenzniveau, Leistungsniveau und z-Wert zu erreichen. Diese berechnete Zahl unterliegt denselben Problemen wie im Feld Erwartete Besucher pro Zeitraum beschrieben. Bei einer Website mit vielen wiederkehrenden Besuchern entspricht das Feld Mindestexperimentdauer (Tage) der erwarteten Anzahl von Tagen, bis eine Anzahl Unique Visitors dem Wert im Feld Erforderliche Mindestbesucher entspricht. |
| Besucher | Überschrift für die Besucherwerte. |
| Testgruppe | Anzahl der in der Testgruppe benötigten Besucher. |
| Kontrollgruppe | Anzahl der in der Kontrollgruppe benötigten Besucher. |
| Gesamt (in der Regel 100%) | Gesamtzahl der für das Experiment benötigten Besucher. Dieser Wert muss gleich oder größer als der Wert im Feld Erforderliche Mindestbesucher (Test+Kontrollgruppen) sein. |
| Genauigkeit der Testgruppe (auf Target-Konfidenzebene) | Prozentsatz, der angibt, dass eine Chance besteht, die dem angegebenen Konfidenzniveau entspricht, dass der für die Testgruppe berechnete gemessene Wert der Metrik innerhalb dieses Prozentsatzes vom tatsächlichen Wert liegt. |
| Genauigkeit der Kontrollgruppe (auf Target-Konfidenzebene) | Prozentsatz, der angibt, dass eine Chance besteht, die dem angegebenen Konfidenzniveau entspricht, dass der für die Kontrollgruppe berechnete gemessene Wert der Metrik in diesem Prozentsatz des tatsächlichen Werts liegt. |
| z-Bewertung (bei Zielgenauigkeit) | Anzahl der Standardabweichungen, die ein angegebener Wert vom Prüfmittelwert abweicht. |
| Tatsächliches Konfidenzniveau (in Zielintervall) | Das für das Experiment erzielte Konfidenzniveau. Das Konfidenzniveau misst die Wahrscheinlichkeit, dass die angegebene Erwartung wahr ist. |
| Tatsächliches Intervall (auf Target-Konfidenzebene) | Das für den Versuch erzielte Konfidenzintervall, das einen geschätzten Wertebereich liefert, der wahrscheinlich einen unbekannten Populationsparameter enthält. Dieser Bereich wird aus einem bestimmten Satz von Beispieldaten berechnet. |

Sie müssen sich den Wert im Feld Erforderliche Mindestbesucher (Test+Kontrollgruppen) ansehen. . .

![](assets/Experiment_Design_Min_Visitors.png)

und vergleichen sie mit dem Wert im Feld Gesamtsumme im [!DNL Visitors] Spalte.

![](assets/Experiment_Design_Total_Visitors.png)

Damit Ihr Experiment statistisch gültig ist, muss der Wert im Feld Gesamt (normalerweise 100 %) gleich oder größer als der Wert im Feld Mindestbesucher erforderlich (Test+Kontrollgruppen) sein.

In Anbetracht der bereitgestellten Eingaben zeigt das Beispielarbeitsblatt, dass 10.475 Besucher an diesem Experiment teilnehmen müssen, um die eingegebene Konfidenzrate von 95 % zu erreichen (dies ist die empfohlene Mindestsicherheit für ein gesteuertes Experiment, auch wenn Sie diese Zahl erhöhen können). Das derzeit entworfene Experiment umfasst 30.000 Besucher, was deutlich über der erforderlichen Mindestanzahl an Besuchern liegt.

Wenn Sie die Anzahl der Tage beibehalten, können Sie das Konfidenzniveau steigern, solange die Gesamtanzahl der Besucher das erforderliche Minimum nicht erreicht oder überschritten hat.

1. Speichern Sie die Datei für Ihre Datensätze und konfigurieren Sie dann mithilfe der Informationen aus der Datei das Experiment mithilfe der Tabelle für die Experimentkonfiguration. Weitere Informationen zu dieser Tabelle finden Sie unter [Konfigurieren und Bereitstellen des Experiments](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).
