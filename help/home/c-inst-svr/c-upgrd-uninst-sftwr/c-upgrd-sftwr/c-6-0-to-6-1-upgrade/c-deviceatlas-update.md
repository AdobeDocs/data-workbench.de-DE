---
description: Die JSON-Datei DeviceAtlas wird jetzt in einer Bundle-Datei (einer umbenannten .tar.gz-Datei) zusammen mit den Dateien DeviceAtlas.dll und DeviceAtlas64.dll bereitgestellt.
title: DeviceAtlas-Distribution
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# DeviceAtlas-Distribution{#deviceatlas-distribution}

{{eol}}

Die JSON-Datei DeviceAtlas wird jetzt in einer Bundle-Datei (einer umbenannten .tar.gz-Datei) zusammen mit den Dateien DeviceAtlas.dll und DeviceAtlas64.dll bereitgestellt.

Wenn der Administrator den Insight Server auf Version 6.0 aktualisiert, ist die Datei DeviceAtlas.bundle im Aktualisierungspaket im Profil Software und Dokumente (Softwareprofil) enthalten, das sich unter folgender Adresse befindet:

[!DNL Server Packages > v6.00 > Server_6.00.zip]

Die Datei DeviceAtlas.bundle wird in extrahiert. [!DNL Server\Lookups\DeviceAtlas].

Die Datei DeviceAtlas.bundle sollte sich in einem Ordner befinden, der mit den DPUs synchronisiert wird, und die Datei DeviceAtlas.cfg, die der neuen DeviceAtlasComponent entspricht, sollte im Ordner &quot;Components for Processing Servers&quot;auf dem Synchronisations-Übergeordnete abgelegt werden. Wenn die Datei DeviceAtlas.bundle geändert wird, erhält der nächste DeviceAtlas-Suchaufruf Ergebnisse basierend auf der aktualisierten API und/oder JSON-Datei.

## Datei &quot;Transformation.cfg&quot;ändern {#section-394823348f5740028666e62e2bd42754}

Die DeviceAtlas-Umwandlungen müssen den Pfad zur JSON-Datei nicht mehr angeben. Frühere DeviceAtlasTransformation, die in der Datei &quot;transformation.cfg&quot;definiert sind, sollten nicht mehr den Dateiparameter enthalten, der auf die verschleierte JSON-Datei verweist.

Diese Beispiel-Datei Transformation.cfg zeigt das File-Argument, das gelöscht werden sollte, um Verwirrung zu vermeiden. (Wenn man es dort lässt, wird es keinen Schaden verursachen, sondern nur zu potenziellen Verwirrungen, weil es ignoriert wird.)

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  
```

## Datei &quot;DeviceAtlas.cfg&quot;ändern {#section-10b43705a6c846fd9ec54ea6be249f88}

Dies ist ein Beispiel für die [!DNL component] -Argument erforderlich in der Datei DeviceAtlas.cfg .

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

Diese DeviceAtlas.bundle -Datei wird aus der Sicht der Funktion zur Profilsynchronisierung wie eine Konfigurationsdatei behandelt. Darüber hinaus werden die JSON-Daten und DLL auf Komponentenebene und nicht auf der Ebene der einzelnen Umwandlungen verwendet.

Eine neue DeviceAtlasComponent sucht beim Start nach dem .bundle-Konglomerat, deverschleiert die JSON-Datei im Speicher, extrahiert die Dateien in ein temporäres Verzeichnis und lädt die entsprechende DLL für die laufende Plattform. Diese Komponente überwacht auch Änderungen an der Bundle-Datei und lädt die DLL- und .cfg-Datei automatisch neu, wenn sie sich ändert.

## Ausführen von DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

Eine ordnungsgemäße Konfiguration macht einen großen Unterschied in der für die Umwandlung erforderlichen Zeit. Die Umwandlung kann so konfiguriert werden, dass sie pro Besucher und Sitzung nur einmal ausgeführt wird, damit DeviceAtlas den Prozess beschleunigen kann.

**Bei Bereitstellung mit Log Processing.cfg**:

Führen Sie die Umwandlungen zweimal aus.

1. Suchen Sie nur nach [!DNL mobile id] Feld, dann
1. Erstellen Sie Bedingungen, um die [!DNL mobile id] und dann den Rest der Felder nachschlagen.

**Bei Bereitstellung mit Transformation.cfg**:

Stellen Sie wie in Schritt 1 in der Protokollverarbeitung oben bereit oder verwenden Sie Zeilenvergleiche, um eine bedingte Einstellung zu unterstützen.

* Zeilen übergreifend - Erfassen Sie den vorherigen Sitzungsschlüssel. Bestimmen Sie dann, ob sich der aktuelle Sitzungsschlüssel von dem mit Zeilenumbrüchen gefundenen unterscheidet. Ist dies der Fall, wird die DeviceAtlas-Umwandlung nur für einen Datensatz pro Sitzung ausgeführt.
