---
description: Webseiten werden häufig mithilfe der Programmiersprache ASP (Active Server Pages) strukturiert.
title: ASP-spezifische Informationen
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# ASP-spezifische Informationen{#asp-specific-information}

{{eol}}

Webseiten werden häufig mithilfe der Programmiersprache ASP (Active Server Pages) strukturiert.

ASP ist eine Microsoft-Technologie, die innerhalb von IIS (Internet Information Services) ausgeführt wird. Wenn ein Browser eine ASP-Datei anfordert, übergibt IIS die Anforderung an die ASP-Engine. Die ASP-Engine liest die ASP-Datei zeilenweise und führt die Skripte in der Datei aus. Schließlich wird die ASP-Datei als einfache HTML an den Browser zurückgegeben. ASP stellt RESPOND- oder REQUEST-Objekte bereit, die zusätzlich zu anderen Verwendungen die Antwort oder Anforderung von Benutzerabfragen oder Daten erlauben, die von HTML-Formularen gesendet werden.

In bestimmten Fällen möchten Sie die in Formularen eingegebenen Werte nicht an die URL anhängen, die in der Adressleiste des Browsers eines Benutzers angezeigt wird oder die im HTML-Code selbst sichtbar ist. Mit einfachem serverseitigem JavaScript können Sie Formularfeldnamen und die entsprechenden Werte an die Protokolldatei anhängen, ohne sie im Browser des Benutzers verfügbar zu machen oder in die HTML-Datei einzubetten. Um die tatsächlichen Formularwerte zu erfassen, die in bestimmte Formulare auf Ihrer Website eingegeben wurden, müssen einige Codezeilen hinzugefügt werden, um die Formularwerte an die Protokollanforderung anzuhängen.

Fügen Sie auf der Verarbeitungsseite eines Formulars den folgenden Code hinzu, um die eingegebenen Formularwerte an die Anfragedaten anzuhängen (zusätzlich zum Schreiben der gesendeten Formularwerte in eine externe Datenbank oder an einen anderen Speicherort):

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

Durch diesen Prozess würden die Formularwerte, wie sie definiert sind, an die Anfragedaten für die [!DNL Form Processing] Seite. Innerhalb der Protokolldaten sind die angehängten Werte als Abfragezeichenfolgen der [!DNL Form Processing] wie unten dargestellt. Beispielsweise wären v_1, v_2, v_3 und v_4 jetzt Abfragezeichenfolgen, die die in die entsprechenden Formularfelder eingegebenen Daten enthalten. Die im obigen Beispiel beschriebene Syntax kann für alle zusätzlichen Formularfelder und Werte dupliziert werden, die erfasst werden sollen.

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Wenn Sie möchten, dass jedes Formularfeld und jeder Wert erfasst und für die Analyse verfügbar ist, können Sie die folgende Syntax verwenden:

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

In diesem Beispiel würden alle in der HTML vorhandenen Formularfelder zusammen mit den entsprechenden Werten genommen und als Abfragezeichenfolgen an den Protokolleintrag für die [!DNL Form Processing] Seite. Beachten Sie, dass dies alle im Formular vorhandenen ausgeblendeten Felder einschließen würde.

Die Protokolldaten werden wie in der folgenden Tabelle beschrieben erweitert:

| Erfasste Daten | Erklärung | Beispiel |
|---|---|---|
| v_1 | Wert, der mit der Abfragezeichenfolge NAME verknüpft ist | v_1=John Smith |
| v_2 | Der CITY-Abfragezeichenfolge zugeordnete Wert | v_2=Los Angeles |
| v_3 | Wert, der mit der STATE-Abfragezeichenfolge verknüpft ist | v_3=California |
| v_4 | Der ZIP-Abfragezeichenfolge zugeordnete Wert | v_4=90210 |
