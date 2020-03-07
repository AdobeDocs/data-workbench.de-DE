---
description: Konfigurieren Sie die Zeitdimensionen so, dass sie für das Gebietsschema korrekt angezeigt werden.
title: Lokalisieren von Zeitdimensionen
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Lokalisieren von Zeitdimensionen{#localizing-time-dimensions}

Konfigurieren Sie die Zeitdimensionen so, dass sie für das Gebietsschema korrekt angezeigt werden.

Sie können das angezeigte Format der Zeitdimensionen basierend auf dem Gebietsschema in der **[!DNL Standard Time Dimensions.cfg]** Datei konfigurieren (standardmäßig unter **[!DNL Server/Profiles/`<my profile>`/DataSet/Transformation/Time/Standard Time Dimensions.cfg]**).

In Nordamerika können Sie beispielsweise das Datum 3. Mai 2015 als 5/3/15 oder **`%m/%d/%y`**. In anderen Teilen der Welt könnte dies jedoch aufgrund einer Mehrdeutigkeit der Werte als `%d/%m/%y`- oder 5. März 2015 interpretiert werden. Um diese Situation zu vermeiden, sollte ein Administrator das angezeigte Format möglicherweise an die Erwartungen der Benutzer in einem Gebietsschema anpassen.

## 1. Standardzeitdimensionen in Standardzeitdimensionen außer Kraft setzen.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

Um diese Funktion zu aktivieren, muss der Administrator die Standardwerte außer Kraft setzen, indem er entweder die vorhandenen Zeitdimensionen bearbeitet oder neue Zeitdimensionen mit zusätzlichen Parametern erstellt.

Es folgt ein Beispiel für eine geänderte Zeitdimension.

Die **Formatwerte** für Woche, Stunde, Tag, Monat und Stunde des Tages werden auf die Standardwerte im Beispiel festgelegt.

>[!NOTE]
>
>Wenn diese Zeilen weggelassen werden, ändert sich das Verhalten von Data Workbench nicht und die Dimension wird mit den Standardeinstellungen kompiliert.

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

## 2. Konfigurieren der Datei &quot;meta.cfg&quot; {#section-5e077d3298dd48fda7f7bb16af9ea00c}

Darüber hinaus muss der Paketadministrator diese Parameter und ihre Standardwerte der **[!DNL meta.cfg]** Profildatei hinzufügen. Dies ermöglicht die Bearbeitung von der Workstation aus.

Hier ist ein Auszug aus einer konfigurierten **[!DNL meta.cfg]** Datei.

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

Hier ein Beispiel für eine **[!DNL meta.cfg]** Datei auf der Workstation:

![](assets/dwb_time_format.png)

Der Administrator kann dann in den **Dateimanager** wechseln, die Datei(en) öffnen, in der/denen die Zeitdimensionen konfiguriert sind (z. B. **[!DNL Standard Time Dimensions.cfg]**), und sie auf der Workstation bearbeiten.
