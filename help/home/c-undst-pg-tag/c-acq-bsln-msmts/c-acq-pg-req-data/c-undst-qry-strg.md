---
description: Die Abfrage-Zeichenfolge (cs-uri-Abfrage) wird häufig von Webanwendungen und Site-Entwicklern verwendet, um Informationen aufgrund der statuslosen Natur von HTTP von Seite zu Seite zu übergeben.
title: Grundlagen zur Abfragezeichenfolge
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# Grundlagen zur Abfragezeichenfolge{#understanding-the-query-string}

Die Abfrage-Zeichenfolge (cs-uri-Abfrage) wird häufig von Webanwendungen und Site-Entwicklern verwendet, um Informationen aufgrund der statuslosen Natur von HTTP von Seite zu Seite zu übergeben.

In vielen Fällen können Informationen in der Abfrage-Zeichenfolge übergeben werden, wenn sie von [!DNL Sensor] auf dem Webserver abgerufen werden. Solche Informationen können von [!DNL Site] verwendet werden, um die wahre Struktur der Website, den Pfad der Besucher durch sie zu beleuchten, sowie andere Informationen.

Bei einigen dynamischen Websites sind Name=Wert-Paare (Variablen) in der Abfrage-Zeichenfolge wichtig, um die tatsächliche Seite zu bestimmen, die von einem Besucher angefordert wird. In solchen Fällen können URLs wie folgt oder ähnlich strukturiert sein:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

In diesem Beispiel ist PAGENAME tatsächlich der Indikator dafür, welche Seite dem Anforderer dieser URL bereitgestellt wird. Viele Tools und Dienste zur Analyse von Webprotokollen schränken die Fähigkeit eines Site-Operators ein, zu definieren, was eine Seite auf ihrer Site ist, basierend darauf, welche Abfrage Zeichenfolgenvariablen in den Zeichenfolgen der Abfrage der URLs der Site auftreten. Der Data Workbench-Server und die Data Workbench können so konfiguriert werden, dass sie solche Seitennamen zum Definieren individueller Abfragen verwenden. Dies ist wichtig, da viele Systeme die folgenden URLs als dieselbe Seite interpretieren würden, [!DNL Site] dies jedoch nicht.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Auf ähnliche Weise fügen Site-Entwickler und -Anwendungen oft viele Zeichenfolgenvariablen zu den URLs einer Site hinzu, die nichts mit der Identifizierung der tatsächlich angeforderten Abfrage zu tun haben. Nachfolgend sind Beispiele aufgeführt:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

In diesem Beispiel wurde der URL die Abfrage String variable KAMPAGNE= hinzugefügt. Diese Variable zur KAMPAGNE wird verwendet, um anzugeben, welche Marketing-Kampagne dazu geführt hat, dass ein Besucher diese URL auswählt. [!DNL Site] können so konfiguriert werden, dass diese KAMPAGNE verwendet wird, trennen Sie sie jedoch von der Seitendefinition, auf der ein Besucher sie angezeigt hat, sodass in Ihrer Liste der Seiten zu Berichte- und Analysen-Zwecken einfach Folgendes angezeigt wird:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
