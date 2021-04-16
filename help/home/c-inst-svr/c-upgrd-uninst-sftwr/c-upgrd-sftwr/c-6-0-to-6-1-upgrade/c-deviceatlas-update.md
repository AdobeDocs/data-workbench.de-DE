---
description: Die JSON-Datei von DeviceAtlas wird jetzt in einer Bundle-Datei (mit dem Namen .tar.gz) zusammen mit den Dateien DeviceAtlas.dll und DeviceAtlas64.dll verteilt.
title: DeviceAtlas-Distribution
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# DeviceAtlas-Distribution{#deviceatlas-distribution}

Die JSON-Datei von DeviceAtlas wird jetzt in einer Bundle-Datei (mit dem Namen .tar.gz) zusammen mit den Dateien DeviceAtlas.dll und DeviceAtlas64.dll verteilt.

Wenn der Administrator den Insight-Server auf Version 6.0 aktualisiert, ist die Datei DeviceAtlas.bundle im Aktualisierungspaket des Software and Docs-Profils (Software-Profil) enthalten, das sich unter folgender Adresse befindet:

[!DNL Server Packages > v6.00 > Server_6.00.zip]

Die Datei DeviceAtlas.bundle wird nach [!DNL Server\Lookups\DeviceAtlas] extrahiert.

Die Datei &quot;DeviceAtlas.bundle&quot;sollte in einem mit den DPUs synchronisierten Ordner abgelegt werden, und die Datei &quot;DeviceAtlas.cfg&quot;entsprechend der neuen DeviceAtlasComponent&quot;sollte im Ordner &quot;Components for Processing Servers&quot;auf dem Synchronisierungsordner Übergeordnet abgelegt werden. Wenn die Datei DeviceAtlas.bundle geändert wird, erhalten die Ergebnisse des nächsten DeviceAtlas-Nachschlageaufrufs auf Basis der aktualisierten API- und/oder JSON-Datei.

## Ändern Sie die Datei &quot;Transformation.cfg&quot;{#section-394823348f5740028666e62e2bd42754}

Die DeviceAtlas-Transformationen müssen nicht mehr den Pfad zur JSON-Datei angeben. Frühere DeviceAtlasTransformation, die in der Datei &quot;transform.cfg&quot;definiert sind, sollten nicht mehr den Parameter File enthalten, der auf die verschleierte JSON-Datei verweist.

Diese Beispieldatei &quot;Transformation.cfg&quot;zeigt das File-Argument, das gelöscht werden sollte, um Verwirrung zu vermeiden. (Es wird keinen Schaden anrichten, sondern nur potenzielle Verwirrung, weil es ignoriert wird.)

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

## Ändern Sie die Datei DeviceAtlas.cfg {#section-10b43705a6c846fd9ec54ea6be249f88}

Dies ist ein Beispiel für das [!DNL component]-Argument, das in der Datei DeviceAtlas.cfg erforderlich ist.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

Diese DeviceAtlas.bundle-Datei wird aus der Sicht der Profil-Synchronisierungsfunktion wie eine Konfigurationsdatei behandelt. Darüber hinaus werden die JSON-Daten und die DLL auf Komponentenebene und nicht auf der Ebene der einzelnen Transformationen verwendet.

Eine neue DeviceAtlasComponent findet beim Start die Bundle-Konglomeration, entfernt die JSON-Datei in den Speicher, extrahiert die Dateien in einen temporären Ordner und lädt die entsprechende DLL für die laufende Plattform. Diese Komponente überwacht auch Änderungen an der Bundle-Datei und lädt die DLL- und .cfg-Datei automatisch neu, wenn sie sich ändert.

## Ausführen von DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

Die richtige Konfiguration macht einen großen Unterschied in der für die Transformation erforderlichen Zeit. Die Transformation kann so konfiguriert werden, dass sie nur einmal pro Besucher pro Sitzung ausgeführt wird, damit DeviceAtlas den Vorgang beschleunigt.

**Bei Bereitstellung mit Log Processing.cfg**:

Führen Sie die Transformationen zweimal aus.

1. Suchen Sie nur das Feld [!DNL mobile id] und dann
1. Erstellen Sie Bedingungen, um die [!DNL mobile id] zu ignorieren und suchen Sie dann die übrigen Felder.

**Bei Bereitstellung mit Transformation.cfg**:

Stellen Sie wie in Schritt 1 in der obigen Protokollverarbeitung bereit oder verwenden Sie Zeilenwechsel, um eine bedingte Einstellung zu unterstützen.

* Zeilenübergreifende Bearbeitung: Ziehen Sie den vorherigen Sitzungsschlüssel ab. Identifizieren Sie dann, ob sich der aktuelle Sitzungsschlüssel von dem mit Kreuzzeilen gefundenen unterscheidet. In diesem Fall wird die DeviceAtlas-Transformation nur mit einem Datensatz pro Sitzung ausgeführt.
