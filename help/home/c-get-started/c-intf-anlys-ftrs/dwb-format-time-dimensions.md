---
description: Konfigurieren Sie die Zeitdimensionen für die korrekte Anzeige des Gebietsschemas.
title: Lokalisieren von Zeitdimensionen
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
exl-id: 950fe70b-a687-4b9c-b29f-555139740809
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Lokalisieren von Zeitdimensionen{#localizing-time-dimensions}

{{eol}}

Konfigurieren Sie die Zeitdimensionen für die korrekte Anzeige des Gebietsschemas.

Sie können das angezeigte Format der Zeitdimensionen basierend auf dem Gebietsschema in der **[!DNL Standard Time Dimensions.cfg]** Datei (standardmäßig unter **[!DNL Server/Profiles/`<my profile>`/dataset/transformation/time/standard time Dimension.cfg]**).

In Nordamerika können Sie beispielsweise das Datum vom 3. Mai 2015 als 03.05.15 angeben oder **`%m/%d/%y`**. In anderen Teilen der Welt könnte dies jedoch als `%d/%m/%y`, oder 5. März 2015 aufgrund einer Mehrdeutigkeit in den Werten. Um dies zu vermeiden, sollte ein Administrator das angezeigte Format ändern, um die Erwartungen der Benutzer in einem Gebietsschema zu erfüllen.

## 1. Außerkraftsetzen von Dimensionen der Standardzeit in Dimensionen der Standardzeit.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

Um diese Funktion zu aktivieren, muss der Administrator die Standardeinstellungen außer Kraft setzen, indem er entweder die vorhandenen Zeitdimensionen bearbeitet oder neue Zeitdimensionen mit zusätzlichen Parametern erstellt.

Es folgt ein Beispiel einer modifizierten Zeitdimension.

Die **Format** -Werte für Woche, Stunde, Tag, Monat und Stunde des Tages auf die Standardwerte im Beispiel gesetzt.

>[!NOTE]
>
>Wenn diese Zeilen weggelassen werden, ändert sich das Verhalten der Data Workbench nicht und die Dimension wird mithilfe der Standardwerte kompiliert.

```
Transformation Include = TransformationInclude:  
  Extended Dimensions = vector: 1 items 
    0 = TimeDimensions:  
      Comments = Comment: 0 items 
      Dimensions = map:  
        Day = string: Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Hour of Day = string: Hour of Day 
        Month = string: Month 
        Week = string: Week 
      Hidden = bool: false 
      Input Time (1970 epoch) = string: x-unixtime 
      Week Format = string:  
  %m/%d/%y
      Hour Format = string:  
  %x %H:%M 
      Day Format = string:  
  %x
      Month Format = string:  
  %b '%y
      Hour Of Day Format = string:  
  %#H:%M
      Name = string: Visit Time 
      Parent = string: Visit 
      Week Start Day = string: Mon 
  Transformations = vector: 0 items
```

![](assets/6_4_time_format.png)

## 2. Konfigurieren Sie die Datei &quot;meta.cfg&quot;. {#section-5e077d3298dd48fda7f7bb16af9ea00c}

Darüber hinaus muss der Paketadministrator diese Parameter und ihre Standardeinstellungen dem Profil hinzufügen **[!DNL meta.cfg]** -Datei. Dies ermöglicht die Bearbeitung von der Workstation aus.

Hier ist ein Auszug aus einer konfigurierten **[!DNL meta.cfg]** -Datei.

```
dimensions = vector: 6 items 
  0 = Template: 
    ...
  ...
  5 = Template: 
    name = string: Time Dimensions 
    value = TimeDimensions: 
      Name = string:  
      Comments = Comment: 0 items 
      Hidden = bool: false 
       
  Week Format = string: %d/%m/%y 
       Hour Format = string: %x %H:%M 
       Day Format = string: %x 
       Month Format = string: %b '%y 
       Hour Of Day Format = string: %#H:%M</b> 
      Input Time (1970 epoch) = string:  
      Parent = string:  
      Week Start Day = string: Mon 
      Dimensions = map: 
        Hour of Day = string: Hour of Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Day = string: Day 
        Week = string: Week 
        Month = string: Month
```

Im Folgenden finden Sie ein Beispiel für eine **[!DNL meta.cfg]** -Datei auf der Workstation:

![](assets/dwb_time_format.png)

Der Administrator kann dann zum **Datei-Manager**, öffnen Sie die Dateien, in denen die Zeitdimensionen konfiguriert sind (z. B. **[!DNL Standard Time Dimensions.cfg]**) und bearbeiten Sie sie über in der Workstation.
