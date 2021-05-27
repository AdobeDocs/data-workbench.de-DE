---
description: Data Workbench Geography unterstützt sowohl Längen- und Breitenprognosen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Topografiebildequellen.
title: Festlegen von Projektionsinformationen für Topografiebilder
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%

---

# Festlegen von Projektionsinformationen für Topografiebilder{#specifying-projection-information-for-terrain-images}

Data Workbench Geography unterstützt sowohl Längen- und Breitenprognosen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Topografiebildequellen.

Projektionsinformationen sind für nicht projizierte Raw-Bitmaps und allgemeine, nicht projizierte Bilder erforderlich. Sie können Projektionsinformationen für Bilder mit eingebetteten Projektionsinformationen angeben, dies ist jedoch normalerweise nicht erforderlich, da die Projektionsparameter automatisch aus den im Bild selbst eingebetteten geodätischen Daten bestimmt werden. In den folgenden Abschnitten finden Sie Details zum Festlegen dieser Projektionsformate in der Datei [!DNL Terrain Images.cfg] .
