---
description: Der Sensor kann bei Verwendung auf einem Server Felder von Ereignisdaten aus allen gültigen HTTP-Anfragen, Antwortheadern oder -Variablen erfassen, die über die Server-API für ihn verfügbar sind.
title: Erweiterbare Felder
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---

# Erweiterbare Felder{#extensible-fields}

{{eol}}

Der Sensor kann bei Verwendung auf einem Server Felder von Ereignisdaten aus allen gültigen HTTP-Anfragen, Antwortheadern oder -Variablen erfassen, die über die Server-API für ihn verfügbar sind.

Um solche Datenfelder zu erfassen, müssen Sie die gewünschten Kopfzeilenfelder oder Variablen in der [!DNL txlogd.conf] Konfigurationsdatei für [!DNL Sensor].

* [Anforderungsheader](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Servervariablen](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## Anforderungsheader {#section-22766692b45546d8bfc93dbe3bc9368f}

Im Folgenden finden Sie die Syntax zum Angeben eines Anforderungsheader-Felds, das erfasst werden soll (z. B. Host, Accept-Encoding, Keep-Alive usw.), in [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

Die erfassten Daten werden von [!DNL Sensor] in ein Feld mit dem Namen &quot;cs(RequestHeaderName)&quot;im [!DNL .vsl] Dateien, die von der [!DNL data workbench server]. Um beispielsweise den spezifischen Anfrage-Header-Wert aus der Anfrage-Kopfzeile &quot;Host&quot;zu erfassen, geben Sie &quot;LogHeader Host&quot;in [!DNL txlogd.conf]. Die Daten werden in das Feld &quot;cs(Host)&quot;im Ereignisdatensatz aufgezeichnet.

## Servervariablen {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] kann Datenfelder aus Antwortheadern oder API-zugänglichen Servervariablen mithilfe von SpecialLogField-Einträgen erfassen, die Sie in die Variablen [!DNL txlogd.conf] -Datei. Sie können auch &quot;SpecialLogField&quot;-Einträge zusätzlich zu oder anstelle von &quot;LogHeader&quot;-Einträgen verwenden, um Anforderungsheader zu erfassen. Siehe [Anforderungsheader](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). Die Option für Anfragekopfzeilen bleibt für Abwärtskompatibilität verfügbar.

Im Folgenden finden Sie die Syntax für die Angabe eines &quot;SpecialLogField&quot;in [!DNL txlogd.conf]:

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
   <td colname="col1"> cs(log-Feld) </td> 
   <td colname="col2"> Der Name des Felds, in das die erfassten Daten im Ereignisdatensatz aufgezeichnet werden, und die <span class="filepath"> .vsl </span> Dateien, die von der <span class="keyword"> Data Workbench-Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Jede Server-Variable, die für <span class="wintitle"> Sensor </span> über die API des Servers </p> <p>Beispiel: response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>Entweder vys_log oder vys_cookie </p> <p>Wenn Sie die Phase angeben, müssen Sie wissen, welche Servervariablen für vys_log und vys_cookie verfügbar sind. </p> <p>Beispiel: Für die serverVariable response.p3p geben Sie vys_log ein. </p> </td> 
  </tr> 
 </tbody> 
</table>

Hilfe zur Konfiguration [!DNL Sensor] um erweiterbare Ereignisdatensatzfelder zu erfassen, wenden Sie sich an Adobe Consulting Services.
