---
title: Ausgeblendete Testseite
description: Diese Seite wird aus der Suche und dem Inhaltsverzeichnis ausgeblendet.
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
source-git-commit: 87af4ae77f71701b52247f996b89edfb93794dd7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Ausgeblendete Testseite

## Badges 

Ein Badge ist eine farbige Bezeichnung, die als Inhaltsanzeige verwendet wird. Sie können beispielsweise ein Zeichen hinzufügen, um einen Artikel als _Beta_ oder einen Abschnitt als _Premium_. Sie können die Farbe eines Badges ändern und eine URL und eine QuickInfo verknüpfen.

[!BADGE Badge-Beispiel]

Es gibt zwei Arten von Badges mit jeweils unterschiedlicher Syntax:

* **Metadaten** - Zeigt den Badge oben auf einer Seite an
* **Inline** - Zeigt den Badge an, unter dem sich die Syntax befindet

### Metadaten-Abzeichen

Durch Hinzufügen der Badge-Syntax in Metadaten wird ein Badge über dem Seitentitel (H1) im Artikel platziert.

Sie können Badges beispielsweise mit _badge1_ oder _badge2_. Oder Sie können kreativer sein (solange der Name mit _badge_).

Metadatenbeispiele:

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** In diesem Beispiel wird ein Premium-Zeichen mit einer URL und einer QuickInfo angezeigt.

* **badgeExam:** In diesem Beispiel wird ein dunkler Badge mit einer Prüfungs-ID-Nummer angezeigt.

#### Inline-Zeichen

Geben Sie die Badge-Informationen in einer eigenen Zeile oder in einer Überschrift, Tabelle oder einem anderen Seitenelement an.

Hier finden Sie die Syntax für ein Inline-Badge mit einer Beta-Beschriftung, blauen Farbe, URL und QuickInfo:

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Verfügbare Badge-Farben

Zeichen verwenden in Adobe Spectrum definierte Farben:

| Typ | Badge |
|---|---|
| Informativ (Standard) | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| Positiv | [!BADGE Neue Funktion]{type=Positive url="https://www.example.com" tooltip="Gehen Sie zu beispiel.com"} |
| Negativ | [!BADGE Abbruch]{type=negative tooltip="Diese Funktion ist jetzt eingestellt"} |
| Neutral | [!BADGE Eventuell]{type=Neutral tooltip="Ein Reiter fiel vom Pferd..."} |
| Vorsicht | [!BADGE Achtung]{type=Caution tooltip="Gelber Status"} |

Syntaxbeispiele

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### Voraussetzungen für Badges

* In Metadaten sind nur zwei Abzeichen zulässig. Diese Regel ist konfigurierbar. Teilen Sie uns also mit, ob Sie eine Ausnahme benötigen.
* Nur die Badge-Bezeichnung ist erforderlich. Die `type`, `url`und `tooltip` -Parameter sind optional. Die `type` bestimmt die Farbe. Die `url` -Parameter können Benutzer auf das Zeichen klicken, um einen Artikel oder eine Seite zu öffnen. Die `tooltip` zeigt den QuickInfo-Text beim Bewegen des Mauszeigers an.
* Hinzufügen eines Abzeichens zum `TOC.md` -Datei zeigt den Badge in jedem Artikel des Handbuchs an. Wenn Sie eine URL für das Badge angeben, um zu einem Artikel zu springen, stellen Sie sicher, dass Sie einen Stammlink verwenden (z. B. `/help/guide/article.md`) keinen relativen Link (z. B. `article.md`), um Artikel in verschiedenen Ordnern zu berücksichtigen.
* Badge hinzufügen zu `metadata-new.md` zeigt den Badge auf jedem Artikel in einem Repo an.
* Stellen Sie bei Metadaten-Badges sicher, dass alle Werte in Anführungszeichen gesetzt sind. Stellen Sie bei Inline-Abzeichen sicher, dass `url` und `tooltip` in Anführungszeichen gesetzt werden.
* Gültige Typwerte umfassen *Informativ* (Standard, blau), *Positiv* (grün), *Negativ* (rot), *Neutral* (dunkelgrau) und *Vorsicht* (gelb).
* Badge-Beschriftungen werden lokalisiert.
* Wenn mehrere Metadaten-Abzeichen angegeben sind, werden Abzeichen basierend auf dem Badge-Namen in alphabetischer Reihenfolge angezeigt, z. B. `badge1:` oder `badgeWeb`.
* Wenn die URL in einer neuen Registerkarte geöffnet werden soll, verwenden Sie diese Syntax:

   ```
   [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
   ```

   Gerendert:

   [!BADGE In neuer Registerkarte öffnen]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Öffnen Sie adobe.com auf der neuen Registerkarte"}

## Texthervorhebung

Das Workfront-Team bat darum, gelbe Hervorhebung verwenden zu können, um die Vorschau der künftigen Funktionen anzuzeigen. So funktioniert es.

Beispiel 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Gerendert:

Dieser gesamte Absatz sollte NICHT hervorgehoben werden. <span class="preview"> Dieses Wort ist **fett** innerhalb eines markierten Satzes.</span> Und das ist nur der letzte Satz.

Beispiel 2:

```
Highlighting should start after this paragraph.

<span class="preview">

**This is a test**

>[!TIP]
>
>Drink 6 cups of water a day.

Last highlighted paragraph

</span>

Not highlighted
```

Gerendert:

Die Hervorhebung sollte nach diesem Absatz beginnen.

<span class="preview">

**Dies ist ein Test**

>[!TIP]
>
>Trinken Sie 6 Tassen Wasser am Tag.

Zuletzt hervorgehobener Absatz

</span>

Nicht hervorgehoben

## Syntaxhervorhebung für Codeblöcke

Experience League unterstützt die Syntaxhervorhebung für Codeblöcke. Stellen Sie sicher, dass Sie eine Sprache wie `java` nach der ersten Reihe von Backticks, um sicherzustellen, dass die Syntax richtig hervorgehoben wird. Eine Liste der gültigen Sprachen finden Sie unter [https://prismjs.com](https://prismjs.com/#supported-languages). Wenn Sprachen fehlen, protokollieren Sie bitte ein Jira-Ticket.

### Zeilennummerierung in Codeblöcken

Hinzufügen `{line-numbers="true"}` nach der Sprache, um die Zeilennummerierung zu aktivieren.

Beispiel mit Zeilennummern (&grave;&grave;&grave;`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**Nummerierung in Zeile _ beginnen**

Hinzufügen `start-number="n"` nach der Zeilennummersyntax , um die Nummerierung auf einer anderen Zahl als 1 zu beginnen.

Beispiel mit neuer Start-Linie (&grave;&grave;&grave;&grave;`html {line-numbers="true" start-line="7"}`):

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### Zeilenhervorhebung in Codeblöcken

Hinzufügen `highlight="n"` nach der Zeilennummersyntax verwenden, um Zeilen in einem Codeblock hervorzuheben. Festlegen `11-13, 16` markiert die Linien 11 bis 13 und 16.

Beispiel mit Zeilenhervorhebung (&grave;&grave;&grave;&grave;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```
