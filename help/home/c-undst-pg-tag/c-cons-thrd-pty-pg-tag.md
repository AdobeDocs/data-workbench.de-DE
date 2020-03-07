---
description: Grundlegende Informationen zum Tagging von Drittanbietern und zur Verhinderung von Cookie-Blockierung mit P3P.
solution: Analytics
title: P3P-Überlegungen zum Tagging von Drittanbieterseiten
topic: Data workbench
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# P3P-Überlegungen zum Tagging von Drittanbieterseiten{#p-p-considerations-for-third-party-page-tagging}

Grundlegende Informationen zum Tagging von Drittanbietern und zur Verhinderung von Cookie-Blockierung mit P3P.

## Informationen zum Tagging von Drittanbieterseiten {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

In den meisten Implementierungen wird das beständige Adobe-Cookie als Erstanbieter-Cookie angesehen. Erstanbieter-Cookies werden als mit der Hostdomäne verbundene Cookies definiert.

Angenommen, ein Benutzer besucht http://www.example.com/. Wenn ein Sensor auf dem Webserver, der die Domäne hostet, installiert und betriebsbereit ist, wird ein beständiges Adobe-Cookie gesetzt und als Erstanbieter-Cookie angesehen. Sie können jedoch mithilfe von eingebetteten Objekten Messungsdaten von einer Drittanbieter-Site erfassen, die von Ihrem Server, der ausgeführt wird, angefordert und geladen werden, [!DNL Sensor] anstatt von dem Drittanbieter-Server, der die Seite oder das Werbeprogramm hostet. Beispielsweise stellt http://www.example2.com/ eine Webseite mit einer eingebetteten Objektanforderung bereit, die von http://www.example.com/ gesendet wird. Die Anforderung des eingebetteten Objekts unter http://www.example.com/ führt dazu, dass ein Cookie gesetzt wird. In diesem Zusammenhang sieht der Webbrowser oder Benutzeragent das Cookie jedoch als Drittanbieter-Cookie an.

In neueren Webbrowsern, wie z. B. dem IE6 von Microsoft, werden Cookies aufgrund ihrer kompakten Richtlinien gefiltert, die im HTTP-Antwort-Header vom Webserver gesendet werden. In den Standardeinstellungen von IE6, die die meisten Benutzer nie ändern, werden Drittanbieter-Cookies blockiert, wenn sie keine oder keine zufriedenstellende kompakte Richtlinie haben. Die meisten Sites, bei denen Cookie-Blocker auftreten, verfügen über Drittanbieter-Cookies auf ihrer Site, die nicht über die entsprechenden Kompaktrichtlinien verfügen, die im HTTP-Antwort-Header gesendet werden. Außerdem treten einige Cookie-Blockierungsprobleme auf, wenn eine Site von einer anderen Site gerahmt wird. Beispielsweise kann ein Online-Store, der Teil eines Online-Shopping-Portals ist, in einem vom Portal bereitgestellten Rahmen angezeigt werden. Aus der Perspektive des Browsers kann es vorkommen, dass Inhalte von Drittanbietern gespeichert werden, wenn sie vom Portal gerahmt werden. Wenn ein Besucher jedoch direkt zum Online-Store wechselt, ohne das Portal zu besuchen, handelt es sich bei dem Inhalt um Inhalte von Erstanbietern. Der Online-Store stellt daher fest, dass Cookies nur blockiert werden, wenn Besucher über das Portal eingehen.

Internetbasierte Mail-Systeme verursachen ein ähnliches Problem. Wenn ein Besucher einer Website eine Webseite per E-Mail an einen Freund sendet, der ein webbasiertes E-Mail-System verwendet, wird die E-Mail-Nachricht als Drittanbieterinhalt für den Browser des Freundes angezeigt, da sie vom E-Mail-System gerahmt wird. Wenn der Seite, die per E-Mail gesendet wurde, Cookies zugeordnet sind, werden sie von IE6 als Drittanbieter-Cookies behandelt.

## Verwenden von P3P zur Verhinderung der Cookie-Blockierung {#section-96831cad887649f295aec6931750e41a}

P3P bietet eine Standardmethode für Websites, ihre Datenschutzrichtlinien in einem computerlesbaren XML-Format zu kodieren. P3P-fähige Webbrowser und andere P3P-Benutzeragenten rufen automatisch die P3P-Datenschutzrichtlinien ab, analysieren sie und vergleichen sie mit den Datenschutzeinstellungen eines Benutzers.

Um zu verhindern, dass IE6 Cookies auf Ihrer Site blockiert, müssen Sie Folgendes sicherstellen:

1. Für alle Cookies, die in einem Drittanbieterkontext gesetzt werden, sind P3P-Kompaktrichtlinien zugeordnet.
1. Die entsprechende Kompaktrichtlinie wird mit einem benutzerdefinierten HTTP-Antwort-Header gesendet.
1. Diese kompakten Richtlinien werden von IE6 als zufriedenstellend angesehen.
1. Wenn die Drittanbieter-Cookies von einem anderen Unternehmen gesetzt werden, müssen Sie diese möglicherweise bitten, P3P zu aktivieren und P3P-Kompaktrichtlinien festzulegen. Jeder Host, der eine P3P-Kompaktrichtlinie festlegt, muss ebenfalls über eine entsprechende vollständige P3P-Richtlinie verfügen. Benutzer können ihre IE6-Einstellungen ändern, sodass Cookies auch unter anderen Bedingungen blockiert werden. Allerdings verhindert die Platzierung zufriedenstellender kompakter Richtlinien auf Drittanbieter-Cookies die meisten Cookie-Blockierungen in IE6.

Das folgende Beispiel zeigt einen solchen P3P-Header:

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

In diesem Beispiel [!DNL p3p.xml] wird die Datei verwendet, um auf eine zugehörige [!DNL policy.xml] Datei zu verweisen, die auf Ihrem Webserver gespeichert ist und die Art der von Ihrer Website erfassten Informationen, die Methoden zur Streitbeilegung, die Ihre Organisation einhält, die Art und Weise, wie die erfassten Daten verwendet werden, wem die Daten gehören, und andere Standardinformationen zum Datenschutz im Internet angibt. Die drei Zeichencodes, die dem &quot;CP&quot; folgen, sind die kompakten Richtlinien-Codes, die das nachahmen, was in Ihrer [!DNL policy.xml] Datei angegeben ist.

Alle kompakten Richtlinien und Richtlinien-XML-Dateien sollten auf das jeweilige Unternehmen zugeschnitten sein, für das sie bereitgestellt werden, und ihre internen Datenschutzrichtlinien bezüglich der Datenerfassung von Websites genau angeben. Eine Vielzahl von P3P-Policy-Editoren finden Sie online zusammen mit detaillierteren Informationen zur Implementierung einer entsprechenden Datenschutzrichtlinie auf Ihrer Website.

Weitere Informationen zum Umgang mit P3P-Headern von Internet Explorer 6 finden Sie unter:

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
