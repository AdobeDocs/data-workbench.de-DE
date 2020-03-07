---
description: Sensor kann bei Verwendung auf einem Server Ereignisdatenfelder aus jeder gültigen HTTP-Anforderung oder jedem Antwortheader oder jeder Variablen erfassen, die über die Server-API verfügbar sind.
solution: Insight
title: Erweiterbare Felder
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erweiterbare Felder{#extensible-fields}

Sensor kann bei Verwendung auf einem Server Ereignisdatenfelder aus jeder gültigen HTTP-Anforderung oder jedem Antwortheader oder jeder Variablen erfassen, die über die Server-API verfügbar sind.

Um solche Datenfelder zu erfassen, müssen Sie die gewünschten Kopfzeilenfelder oder Variablen in der [!DNL txlogd.conf] Konfigurationsdatei für [!DNL Sensor]angeben.

* [Anforderungsheader](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Servervariablen](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## Anforderungsheader {#section-22766692b45546d8bfc93dbe3bc9368f}

Im Folgenden finden Sie die Syntax zum Festlegen eines Anforderungs-Header-Felds, das erfasst werden soll (z. B. Host, Accept-Encoding, Keep-Alive usw.) in [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

Die erfassten Daten werden von einem Feld [!DNL Sensor] mit dem Namen &quot;cs(RequestHeaderName)&quot;in den [!DNL .vsl] Dateien aufgezeichnet, die vom [!DNL data workbench server]. Wenn Sie beispielsweise den jeweiligen Anforderungsheader-Wert aus dem Anforderungsheader &quot;Host&quot;erfassen möchten, geben Sie &quot;LogHeader-Host&quot;in [!DNL txlogd.conf]ein. Die Daten werden im Ereignisdatensatz in das Feld &quot;cs(Host)&quot;eingetragen.

## Servervariablen {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] kann Datenfelder aus Antwortheadern oder API-zugänglichen Servervariablen mithilfe von SpecialLogField-Einträgen erfassen, die Sie in die [!DNL txlogd.conf] Datei einschließen. Sie können auch &quot;SpecialLogField&quot;-Einträge zusätzlich zu oder anstelle von &quot;LogHeader&quot;-Einträgen verwenden, um Anforderungsheader zu erfassen. Siehe [Anforderungsheader](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). Die Option für Anforderungsheader bleibt für Abwärtskompatibilität verfügbar.

Die folgende Syntax dient zum Festlegen eines &quot;SpecialLogField&quot;in [!DNL txlogd.conf]:

```
SpecialLogField cs(log field) = serverVariable stage
```

Die folgende Tabelle enthält Beschreibungen der Komponenten eines Eintrags &quot;SpecialLogField&quot;.

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Komponente </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(Protokollfeld) </td> 
   <td colname="col2"> Der Name des Felds, in dem die erfassten Daten im Ereignisdatensatz und in den <span class="filepath"> .vsl- </span> Dateien aufgezeichnet werden, die vom <span class="keyword"> Data Workbench-Server erstellt wurden </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Jede Servervariable, die über die Server-API für <span class="wintitle"> Sensor verfügbar </span> ist </p> <p>Beispiel: response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>Entweder vys_log oder vys_cookie </p> <p>Wenn Sie die Phase angeben, müssen Sie wissen, welche Servervariablen für vys_log und vys_cookie verfügbar sind. </p> <p>Beispiel: Für die serverVariable response.p3p geben Sie vys_log ein. </p> </td> 
  </tr> 
 </tbody> 
</table>

Wenden Sie sich an Adobe Consulting Services, [!DNL Sensor] um die Erfassung erweiterbarer Ereignisdatensatzfelder zu unterstützen.
