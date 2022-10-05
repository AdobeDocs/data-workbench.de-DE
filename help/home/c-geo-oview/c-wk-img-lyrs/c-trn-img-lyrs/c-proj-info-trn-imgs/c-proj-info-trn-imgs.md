---
description: Data Workbench Geography unterstützt sowohl Längen- und Breitenprognosen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Topografiebildequellen.
title: Festlegen von Projektionsinformationen für Topografiebilder
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%

---

# Festlegen von Projektionsinformationen für Topografiebilder{#specifying-projection-information-for-terrain-images}

{{eol}}

Data Workbench Geography unterstützt sowohl Längen- und Breitenprognosen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Topografiebildequellen.

Projektionsinformationen sind für nicht projizierte Raw-Bitmaps und allgemeine, nicht projizierte Bilder erforderlich. Sie können Projektionsinformationen für Bilder mit eingebetteten Projektionsinformationen angeben, dies ist jedoch normalerweise nicht erforderlich, da die Projektionsparameter automatisch aus den im Bild selbst eingebetteten geodätischen Daten bestimmt werden. Die folgenden Abschnitte enthalten Details zum Festlegen dieser Projektionsformate in der [!DNL Terrain Images.cfg] -Datei.
