---
description: Konzeptbezogene Informationen zum Tagging von Drittanbietern und zur Verhinderung von Cookie-Blockierung mithilfe von P3P.
title: Konzepte zum Tagging von Drittanbieterseiten mittels P3P
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Konzepte zum Tagging von Drittanbieterseiten mittels P3P{#p-p-considerations-for-third-party-page-tagging}

{{eol}}

Konzeptbezogene Informationen zum Tagging von Drittanbietern und zur Verhinderung von Cookie-Blockierung mithilfe von P3P.

## Informationen zum Tagging von Drittanbieterseiten {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

In den meisten Implementierungen wird das persistente Cookie der Adobe als Erstanbieter-Cookie betrachtet. Erstanbieter-Cookies werden als mit der Hostdomäne verknüpfte Cookies definiert.

Angenommen, ein Benutzer besucht https://www.example.com/. Wenn ein Sensor auf dem Webserver installiert und betriebsbereit ist, auf dem die Domäne gehostet wird, wird ein persistentes Cookie für die Adobe gesetzt und als Erstanbieter-Cookie betrachtet. Sie können jedoch Messdaten von einer Drittanbieter-Site mithilfe von eingebetteten Objekten erfassen, die von Ihrem Server angefordert und geladen werden, der ausgeführt wird [!DNL Sensor] anstatt vom Drittanbieter-Server, auf dem die Seite oder das Werbeprogramm gehostet wird. Beispielsweise stellt https://www.example2.com/ eine Webseite mit einer eingebetteten Objektanforderung bereit, die von https://www.example.com/ bereitgestellt wird. Die Anforderung für das eingebettete Objekt von https://www.example.com/ führt dazu, dass ein Cookie gesetzt wird. In diesem Kontext betrachtet der Webbrowser oder Benutzeragent das Cookie jedoch als Drittanbieter-Cookie.

In neueren Webbrowsern wie dem IE6 von Microsoft filtern Datenschutzfunktionen Cookies basierend auf ihren kompakten Richtlinien, die im HTTP-Antwortheader vom Webserver gesendet werden. In den Standard-IE6-Einstellungen, die die meisten Benutzer nie ändern, werden Drittanbieter-Cookies blockiert, wenn sie nicht vorhandene oder unbefriedigende kompakte Richtlinien haben. Die meisten Sites, bei denen Cookie-Blockierungsprobleme auftreten, verfügen auf ihrer Site über Drittanbieter-Cookies, die nicht über die entsprechenden kompakten Richtlinien verfügen, die im HTTP-Antwortheader gesendet werden. Darüber hinaus treten einige Cookie-Blockierungsprobleme auf, wenn eine Site von einer anderen Site gerahmt wird. Beispielsweise kann ein Online-Store, der Teil eines Online-Shopping-Portals ist, in einem vom Portal bereitgestellten Frame angezeigt werden. Aus der Sicht des Browsers kann es vorkommen, dass der Store-Inhalt als Drittanbieterinhalt erscheint, wenn er vom Portal gerahmt wird. Wenn ein Besucher jedoch direkt zum Online-Store wechselt, ohne das Portal zu besuchen, wird der Inhalt Erstanbieterinhalt sein. Der Online-Store findet also, dass seine Cookies nur blockiert werden, wenn Besucher über das Portal einreisen.

Webbasierte E-Mail-Systeme verursachen ein ähnliches Problem. Wenn ein Besucher einer Website eine Webseite per E-Mail an einen Freund sendet, der ein webbasiertes E-Mail-System verwendet, wird die E-Mail-Nachricht als Drittanbieterinhalt im Browser des Freundes angezeigt, da sie vom E-Mail-System gerahmt wird. Wenn der per E-Mail gesendeten Seite Cookies zugeordnet sind, werden sie von IE6 als Drittanbieter-Cookies behandelt.

## Verwenden von P3P zur Verhinderung von Cookie-Blockierung {#section-96831cad887649f295aec6931750e41a}

P3P bietet eine Standardmethode für Websites, ihre Datenschutzrichtlinien in einem computerlesbaren XML-Format zu kodieren. P3P-fähige Webbrowser und andere P3P-Benutzeragenten rufen automatisch P3P-Datenschutzrichtlinien ab, analysieren sie und vergleichen sie mit den Datenschutzeinstellungen eines Benutzers.

Um zu verhindern, dass IE6 Cookies auf Ihrer Site blockiert, müssen Sie Folgendes sicherstellen:

1. Allen Cookies, die in einem Drittanbieterkontext gesetzt werden, sind P3P-Kompaktrichtlinien zugeordnet.
1. Die entsprechende kompakte Richtlinie wird mit einem benutzerdefinierten HTTP-Antwortheader gesendet.
1. Diese kompakten Richtlinien werden von IE6 als zufriedenstellend betrachtet.
1. Wenn die Drittanbieter-Cookies von einem anderen Unternehmen gesetzt werden, müssen Sie sie möglicherweise auffordern, P3P zu aktivieren und P3P-Kompaktrichtlinien festzulegen. Jeder Host, der eine P3P-Kompaktrichtlinie festlegt, muss ebenfalls über eine entsprechende vollständige P3P-Richtlinie verfügen. Benutzer können ihre IE6-Einstellungen so ändern, dass Cookies auch unter anderen Bedingungen blockiert werden. Allerdings verhindert das Setzen zufriedenstellender kompakter Richtlinien auf Drittanbieter-Cookies die meisten IE6-Cookie-Blockierungen.

Im Folgenden finden Sie ein Beispiel für einen solchen P3P-Header:

```
P3P: policyref=” https://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

In diesem Beispiel wird die Datei [!DNL p3p.xml] wird verwendet, um auf eine verknüpfte [!DNL policy.xml] -Datei auf Ihrem Webserver, die angibt, welche Arten von Informationen Ihre Website erfasst, welche Streitbeilegungsmethoden Ihr Unternehmen einhält, wie die erfassten Daten verwendet werden, wem die Daten gehören und andere Standardinformationen im Zusammenhang mit dem Datenschutz im Internet. Die drei Zeichencodes, die dem &quot;CP&quot;folgen, sind die kompakten Richtliniencodes, mit denen die in Ihrem [!DNL policy.xml] -Datei.

Alle kompakten Richtlinien und Richtlinien-XML-Dateien sollten auf die jeweilige Organisation zugeschnitten sein, für die sie bereitgestellt werden, und ihre internen Datenschutzrichtlinien im Hinblick auf die Website-Datenerfassung genau angeben. Eine Vielzahl von P3P-Richtlinien-Editoren finden Sie online zusammen mit detaillierteren Informationen zur Implementierung einer entsprechenden Datenschutzrichtlinie auf Ihrer Website.

Weitere Informationen dazu, wie Internet Explorer 6 mit P3P-Headern umgeht, finden Sie unter:

[https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
