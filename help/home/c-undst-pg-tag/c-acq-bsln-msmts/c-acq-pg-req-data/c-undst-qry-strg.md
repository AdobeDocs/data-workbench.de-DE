---
description: Die Abfragezeichenfolge (cs-uri-query) wird häufig von Webanwendungen und Site-Entwicklern verwendet, um Informationen aufgrund der statuslosen Natur von HTTP von Seite zu Seite zu übergeben.
solution: Analytics
title: Die Abfragezeichenfolge
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Die Abfragezeichenfolge{#understanding-the-query-string}

Die Abfragezeichenfolge (cs-uri-query) wird häufig von Webanwendungen und Site-Entwicklern verwendet, um Informationen aufgrund der statuslosen Natur von HTTP von Seite zu Seite zu übergeben.

In vielen Fällen können Informationen in der Abfragezeichenfolge übergeben werden, wenn sie vom [!DNL Sensor] Webserver erfasst werden. Diese Informationen können verwendet werden, [!DNL Site] um die wahre Struktur der Site und den Pfad der Besucher durch sie zu beleuchten, sowie andere Informationen.

Auf einigen dynamischen Websites sind Name=Wert-Paare (Variablen) in der Abfragezeichenfolge wichtig, um die tatsächliche Seite zu bestimmen, die von einem Besucher angefordert wird. In solchen Fällen können URLs wie folgt oder ähnlich strukturiert sein:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

In diesem Beispiel ist PAGENAME tatsächlich der Indikator dafür, welche Seite dem Anforderer dieser URL bereitgestellt wird. Viele Webprotokollanalysetools und -dienste beschränken die Fähigkeit eines Site-Operators, zu definieren, was eine Seite in ihrer Site ist, basierend darauf, welche Abfragezeichenfolgenvariablen in den Abfragezeichenfolgen der URLs der Site auftreten. Der Data Workbench-Server und die Data Workbench können so konfiguriert werden, dass sie solche Abfragenamen verwenden, um eindeutige Seiten zu definieren. Dies ist wichtig, da viele Systeme die folgenden URLs als dieselbe Seite interpretieren würden, dies jedoch [!DNL Site] nicht.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Auf ähnliche Weise fügen Site-Entwickler und Anwendungen oft viele Abfragezeichenfolgenvariablen zu den URLs einer Site hinzu, die nichts mit der Identifizierung der tatsächlich angeforderten Seite zu tun haben. Nachfolgend sind Beispiele aufgeführt:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

In diesem Beispiel wurde der URL die Abfragezeichenfolgen-Variable CAMPAIGN= hinzugefügt. Diese CAMPAIGN-Variable wird verwendet, um anzugeben, welche Marketingkampagne einen Besucher veranlasst hat, diese URL auszuwählen. [!DNL Site] kann so konfiguriert werden, dass diese CAMPAIGN-Informationen verwendet werden, trennen Sie sie jedoch von der Definition der Seite, die ein Besucher angezeigt hat, sodass in Ihrer Liste der Seiten zu Berichts- und Analysezwecken einfach Folgendes angezeigt wird:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

