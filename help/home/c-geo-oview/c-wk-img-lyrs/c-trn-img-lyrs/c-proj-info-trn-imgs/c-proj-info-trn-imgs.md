---
description: Data Workbench Geography unterstützt sowohl Längen- und Breitengradprognosen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Terrain-Bildschichtquellen.
title: Festlegen von Projektionsinformationen für Topografiebilder
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%

---

# Festlegen von Projektionsinformationen für Topografiebilder{#specifying-projection-information-for-terrain-images}

Data Workbench Geography unterstützt sowohl Längen- und Breitengradprognosen als auch UTM-Projektionen (Universal Transverse Mercator) für alle Terrain-Bildschichtquellen.

Projektionsinformationen sind für unprojizierte und nicht projizierte Rohdaten und allgemeine Bilder erforderlich. Sie können Projektionsinformationen für Bilder mit eingebetteten Projektionsinformationen angeben, die jedoch normalerweise nicht erforderlich sind, da die Parameter der Projektion automatisch anhand der im Bild selbst eingebetteten geodätischen Daten bestimmt werden. Die folgenden Abschnitte enthalten Details zum Festlegen dieser Projektionsformate in der Datei [!DNL Terrain Images.cfg].
