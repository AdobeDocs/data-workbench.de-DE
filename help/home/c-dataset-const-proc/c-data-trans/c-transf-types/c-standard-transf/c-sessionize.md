---
description: Wenn Sie mit Daten arbeiten, die aus dem Website-Traffic erfasst wurden, können Sie mithilfe der Sessionize-Transformation festlegen, wie Sitzungen definiert werden.
solution: Analytics
title: Sessionieren
topic: Data workbench
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Sessionieren{#sessionize}

Wenn Sie mit Daten arbeiten, die aus dem Website-Traffic erfasst wurden, können Sie mithilfe der Sessionize-Transformation festlegen, wie Sitzungen definiert werden.

Die Transformation benötigt als Eingabe einen Zeitstempel und eine Tracking-ID und gibt für jeden Protokolleintrag eine Sitzungsnummer aus. Die Sitzungsnummer lautet &quot;1&quot;für die erste Sitzung mit einer gegebenen Tracking-ID, &quot;2&quot;für die zweite Sitzung mit derselben Tracking-ID usw. Die Ausgabe kann direkt als Sitzungsschlüssel verwendet werden, da sie für jede Sitzung einen eindeutigen Wert hat.

>[!NOTE]
>
>Damit die [!DNL Sessionize] Transformation funktioniert, müssen die Daten in der Zeit angeordnet und nach der Tracking-ID in den Quelldaten gruppiert werden. Daher [!DNL Sessionize] funktioniert nur, wenn sie in der [!DNL Transformation.cfg] Datei oder in einer [!DNL Transformation Dataset Include] Datei definiert ist.

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Standardeinstellung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Beschreibender Name der Transformation. Sie können hier einen beliebigen Namen eingeben. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentare </td> 
   <td colname="col2"> Optional. Anmerkungen zur Transformation. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bedingung </td> 
   <td colname="col2"> Die Bedingungen, unter denen diese Umwandlung angewendet wird. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabezeitstempel </td> 
   <td colname="col2"> Das Feld mit den Werten des zu verwendenden Zeitstempels. </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eingabe-Tracking-ID </td> 
   <td colname="col2"> <p>Das Feld mit den Werten der zu verwendenden Tracking-ID. Der Wert muss eine 64-Bit- (16-stellige) oder eine kleinere Hexadezimalzahl oder eine Dezimalzahl von 16 Ziffern oder weniger sein. </p> <p> <p>Hinweis: Wenn Sie für die Tracking-ID ein anderes Feld als x-trackingid verwenden möchten, müssen Sie das Feld zuerst hash. Siehe <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> Hash</a>. </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Max. Sitzungsdauer </p> </td> 
   <td colname="col2">Die längste Sitzungslänge vor dem Start einer neuen Sitzung. (Dadurch wird verhindert, dass Webseiten mit automatischem Inhalt beliebig lange Sitzungen erstellen.) Wenn die <span class="wintitle"> Timeout-Bedingung</span> erfüllt ist und die verweisende Stelle eines Klicks auf einen der Einträge im Parameter "Interne Domänen"festgelegt ist, wird die maximale Sitzungsdauer verwendet, um das Ende einer Sitzung zu definieren. Keine Sitzung darf länger als die angegebene maximale Sitzungsdauer sein, unabhängig davon, wie viele Klicks sie enthält. Der empfohlene Wert beträgt 48 Stunden. Weitere Informationen zu den Parametern für die maximale Sitzungsdauer und interne Domänen finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Konfigurationseinstellungen für Webdaten</a>. </td> 
   <td colname="col3"> 48 Stunden </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nummer der Ausgabesitzung </td> 
   <td colname="col2"> Das Feld, in dem die Sitzungsnummer gespeichert wird. Dieses Feld hat für jede Sitzung einen eindeutigen Wert für jeden Besucher. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitzungs-Timeout </td> 
   <td colname="col2"> <p>Die Zeit, die zwischen den Protokolleinträgen eines Besuchers verstreichen muss, um das Ende einer Sitzung und den Beginn einer neuen Sitzung zu bestimmen (d. h. die typische Zeitüberschreitung, die zur Definition einer Benutzersitzung verwendet wird). Der empfohlene Wert dieses Parameters beträgt 30 Minuten. Wenn die Timeout-Bedingung nicht erfüllt ist und die verweisende Stelle eines Klicks nicht auf eine der verweisenden Stellen im Parameter "Interne Domänen"festgelegt ist, wird die Sitzung mit dem Sitzungszeitlimit definiert. </p> <p> Wenn die Timeout-Bedingung erfüllt ist und cs(referrer-domain) für einen Protokolleintrag in der Liste der internen Domänen enthalten ist, bestimmt die maximale Sitzungsdauer, ob der aktuelle Protokolleintrag Teil einer vorhandenen Sitzung oder der Beginn einer neuen Sitzung ist. </p> <p> Weitere Informationen zum Parameter "Sitzungs-Timeout"finden Sie unter <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Konfigurationseinstellungen für Webdaten</a>. </p> </td> 
   <td colname="col3"> 30 Minuten </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zeitüberschreitungsbedingung </td> 
   <td colname="col2"> Die Bedingung, die erfüllt sein muss, damit ein Protokolleintrag als Beginn einer neuen Sitzung betrachtet werden kann. Beachten Sie, dass die Zeit zwischen dem Protokolleintrag und dem vorherigen Protokolleintrag mindestens dem Wert des Sitzungs-Timeout-Parameters entsprechen muss. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Eine neue Sitzung beginnt, wenn eine der folgenden Situationen eintritt:

* Die Tracking-ID ändert sich.
* Die Zeit seit dem letzten Protokolleintrag entspricht mindestens dem Wert des Parameters Sitzungs-Timeout und die Timeout-Bedingung ist erfüllt.
* Die Zeit seit dem ersten Protokolleintrag der letzten Sitzung überschreitet den Wert des Parameters Maximum Session Duration.

>[!NOTE]
>
>Wenn Sie die maximale Sitzungsdauer und das Sitzungszeitlimit bereits als Parameter in der [!DNL Session Parameters.cfg] Datei definiert haben, geben Sie keine Werte für diese Parameter in der Konfiguration ein. Sie können auf die Parameter verweisen, indem Sie *$(Parametername)* eingeben, wie im folgenden Beispiel gezeigt. Weitere Informationen zu diesen Parametern finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

Die [!DNL Sessionize] Transformation in diesem Beispiel nimmt als Eingabe die x-timestamp- und x-trackingid-Felder und zeichnet die Sitzungsnummer für jeden Protokolleintrag im Feld x-session-key auf. Die Transformation [!DNL Timeout Condition] basiert auf einer [!DNL Neither] Bedingung: Wenn das Feld cs(referrer-domain) für einen Protokolleintrag mit einem Mitglied des Parameters Internal Domains übereinstimmt, wird die Bedingung als &quot;false&quot;ausgewertet. Beachten Sie die Verweise auf die Parameter &quot;Interne Domänen&quot;und &quot;Sitzungs-Timeout&quot;.

Weitere Informationen zu den [!DNL NeitherCondition]Variablen finden Sie unter [Bedingungen](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md). Weitere Informationen zu den Parametern &quot;Interne Domänen&quot;und &quot;Sitzungs-Timeout&quot;finden Sie unter [Konfigurationseinstellungen für Webdaten](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

![](assets/cfg_TransformationType_Sessionize.png)

