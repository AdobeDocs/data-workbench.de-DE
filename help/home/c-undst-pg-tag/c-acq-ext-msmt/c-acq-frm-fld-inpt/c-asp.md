---
description: Webseiten werden häufig mithilfe der Programmiersprache ASP (Active Server Pages) strukturiert.
title: ASP-spezifische Informationen
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# ASP-spezifische Informationen{#asp-specific-information}

Webseiten werden häufig mithilfe der Programmiersprache ASP (Active Server Pages) strukturiert.

ASP ist eine Microsoft-Technologie, die innerhalb von IIS (Internet-Informationsdienst) ausgeführt wird. Wenn ein Browser eine ASP-Datei anfordert, übergibt IIS die Anforderung an die ASP-Engine. Die ASP-Engine liest die ASP-Datei zeilenweise und führt die Skripten in der Datei aus. Schließlich wird die ASP-Datei als einfaches HTML an den Browser zurückgegeben. ASP stellt RESPOND- oder REQUEST-Objekte bereit, die neben anderen Verwendungszwecken auch die Beantwortung oder Anforderung von Benutzerdaten oder von HTML-Formularen gesendeten Abfragen ermöglichen.

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

Bei diesem Prozess werden die Formularwerte, wie sie definiert sind, an die Anforderungsdaten für die [!DNL Form Processing]-Seite angehängt. Innerhalb der Protokolldaten stehen die angehängten Werte als Abfragen-Zeichenfolgen der Seite [!DNL Form Processing] zur Verfügung, wie unten dargestellt. Beispielsweise sind v_1, v_2, v_3 und v_4 nun Abfragen-Zeichenfolgen, die die in die entsprechenden Formularfelder eingegebenen Daten enthalten. Die im obigen Beispiel beschriebene Syntax kann für alle zusätzlichen Formularfelder und Werte, die erfasst werden sollen, dupliziert werden.

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Wenn alle Formularfelder und -werte erfasst und zur Analyse verfügbar sein sollen, können Sie die folgende Syntax verwenden:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

In diesem Beispiel werden alle im HTML vorhandenen Formularfelder zusammen mit den entsprechenden Werten als Abfragen-Zeichenfolgen an den Protokolleintrag für die [!DNL Form Processing]-Seite angehängt. Beachten Sie, dass dies alle ausgeblendeten Felder im Formular einschließen würde.

Die Protokolldaten werden wie in der folgenden Tabelle beschrieben erweitert:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1 | Der mit der Zeichenfolge NAME-Abfrage verknüpfter Wert | v_1=John Smith |
| v_2 | Mit der CITY-Abfrage verknüpfter Wert | v_2=Los Angeles |
| v_3 | Mit der Zeichenfolge STATE-Abfrage verknüpfter Wert | v_3=Kalifornien |
| v_4 | Mit der ZIP-Abfrage verknüpfter Wert | v_4=90210 |
