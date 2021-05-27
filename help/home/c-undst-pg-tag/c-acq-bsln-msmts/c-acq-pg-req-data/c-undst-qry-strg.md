---
description: Die Abfragezeichenfolge (cs-uri-query) wird häufig von Webanwendungen und Site-Entwicklern verwendet, um Informationen aufgrund der statuslosen Natur von HTTP von Seite zu Seite zu übergeben.
title: Grundlagen zur Abfragezeichenfolge
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# Grundlagen zur Abfragezeichenfolge{#understanding-the-query-string}

Die Abfragezeichenfolge (cs-uri-query) wird häufig von Webanwendungen und Site-Entwicklern verwendet, um Informationen aufgrund der statuslosen Natur von HTTP von Seite zu Seite zu übergeben.

In vielen Fällen können Informationen in der Abfragezeichenfolge übergeben werden, wenn sie von [!DNL Sensor] auf dem Webserver abgerufen werden. Diese Informationen können von [!DNL Site] verwendet werden, um die wahre Struktur der Site, den Pfad der Besucher durch sie sowie andere Informationen zu beleuchten.

Auf einigen dynamischen Websites sind Name=Wert Paare (Variablen) in der Abfragezeichenfolge wichtig, um die tatsächliche Seite zu bestimmen, die von einem Besucher angefordert wird. In solchen Fällen können URLs wie folgt oder auf ähnliche Weise strukturiert sein:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

In diesem Beispiel ist PAGENAME tatsächlich der Indikator dafür, welche Seite dem Anfragenden dieser URL bereitgestellt wird. Viele Webprotokollanalysetools und -dienste schränken die Fähigkeit eines Site-Operators ein, zu definieren, welche Seite sich auf ihrer Site befindet, basierend darauf, welche Abfragezeichenfolgenvariablen in den Abfragezeichenfolgen der URLs der Site auftreten. Der Data Workbench-Server und die Data Workbench können so konfiguriert werden, dass sie solche Abfragenamen zum Definieren eindeutiger Seiten verwenden. Dies ist wichtig, da viele Systeme die folgenden URLs als dieselbe Seite interpretieren würden, [!DNL Site] dies jedoch nicht tut.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Auf ähnliche Weise fügen Site-Entwickler und Anwendungen häufig viele Abfragezeichenfolgenvariablen zu den URLs einer Site hinzu, die nichts mit der Identifizierung der tatsächlichen Seite zu tun haben, die angefordert wird. Nachfolgend finden Sie Beispiele:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

In diesem Beispiel wurde die Abfragezeichenfolgenvariable CAMPAIGN= zur URL hinzugefügt. Diese CAMPAIGN-Variable wird verwendet, um anzugeben, durch welche Marketing-Kampagne ein Besucher diese URL ausgewählt hat. [!DNL Site] kann so konfiguriert werden, dass diese CAMPAIGN-Informationen verwendet werden, sie jedoch von der Definition der Seite trennen, die ein Besucher angezeigt hat, sodass in Ihrer Liste der Seiten zu Berichts- und Analysezwecken einfach Folgendes angezeigt wird:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
