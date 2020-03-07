---
description: Webseiten werden häufig mithilfe der Programmiersprache ASP (Active Server Pages) strukturiert.
solution: Analytics
title: ASP-spezifische Informationen
topic: Data workbench
uuid: 552288cb-b775-4121-8869-322f2a26932b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ASP-spezifische Informationen{#asp-specific-information}

Webseiten werden häufig mithilfe der Programmiersprache ASP (Active Server Pages) strukturiert.

ASP ist eine Microsoft-Technologie, die innerhalb von IIS (Internet Information Services) ausgeführt wird. Wenn ein Browser eine ASP-Datei anfordert, übergibt IIS die Anforderung an die ASP-Engine. Die ASP-Engine liest die ASP-Datei zeilenweise und führt die Skripten in der Datei aus. Schließlich wird die ASP-Datei als einfaches HTML an den Browser zurückgegeben. ASP stellt RESPOND- oder REQUEST-Objekte bereit, die neben anderen Verwendungszwecken auch die Beantwortung oder Anforderung von Benutzerabfragen oder Daten ermöglichen, die von HTML-Formularen gesendet werden.

In bestimmten Fällen möchten Sie die in Formularen eingegebenen Werte möglicherweise nicht an die URL anhängen, die in der Adressleiste des Browsers des Benutzers angezeigt wird oder die im HTML-Code selbst sichtbar ist. Mit einfachem serverseitigen JavaScript können Sie Formularfeldnamen und deren entsprechende Werte an die Protokolldatei anhängen, ohne sie im Browser des Benutzers verfügbar zu machen oder in die HTML-Datei einzubetten. Um die tatsächlichen Formularwerte zu erfassen, die in bestimmte Formulare auf Ihrer Website eingegeben wurden, müssen einige Codezeilen hinzugefügt werden, um die Formularwerte an die Protokollanforderung anzuhängen.

Fügen Sie auf der Verarbeitungsseite eines Formulars den folgenden Code hinzu, um die eingegebenen Formularwerte an die Anforderungsdaten anzuhängen (zusätzlich zum Schreiben der gesendeten Formularwerte in eine externe Datenbank oder an einen anderen Speicherort):

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

Bei diesem Prozess werden die Formularwerte, wie sie definiert sind, an die Anforderungsdaten für die [!DNL Form Processing] Seite angehängt. Innerhalb der Protokolldaten stehen die angehängten Werte als Abfragezeichenfolgen der [!DNL Form Processing] Seite zur Verfügung, wie unten dargestellt. Beispielsweise wären v_1, v_2, v_3 und v_4 nun Abfragezeichenfolgen, die die in die entsprechenden Formularfelder eingegebenen Daten enthalten. Die im obigen Beispiel beschriebene Syntax kann für alle zusätzlichen Formularfelder und Werte, die erfasst werden sollen, dupliziert werden.

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Wenn jedes Formularfeld und jeder Wert erfasst und für die Analyse verfügbar sein sollen, können Sie die folgende Syntax verwenden:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

In diesem Beispiel würden alle im HTML vorhandenen Formularfelder zusammen mit ihren jeweiligen Werten als Abfragezeichenfolgen an den Protokolleintrag der [!DNL Form Processing] Seite angehängt. Beachten Sie, dass dies alle ausgeblendeten Felder im Formular einschließen würde.

Die Protokolldaten werden wie in der folgenden Tabelle beschrieben erweitert:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1 | Mit der Abfragezeichenfolge NAME verknüpfter Wert | v_1=John Smith |
| v_2 | Mit der CITY-Abfragezeichenfolge verknüpfter Wert | v_2=Los Angeles |
| v_3 | Mit der STATE-Abfragezeichenfolge verknüpfter Wert | v_3=Kalifornien |
| v_4 | Mit der ZIP-Abfragezeichenfolge verknüpfter Wert | v_4=90210 |

