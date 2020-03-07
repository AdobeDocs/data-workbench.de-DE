---
description: Anweisungen zum Hinzufügen der Datei visual_sciences.dll zum Java-Bibliothekspfad Tomcat.
title: Java-Bibliothekspfad ändern
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Java-Bibliothekspfad ändern{#modify-the-java-library-path}

Anweisungen zum Hinzufügen der Datei visual_sciences.dll zum Java-Bibliothekspfad Tomcat.

1. Navigieren Sie auf Ihrem Windows-Server zum Installationsordner von Tomcat. (Tomcat > bin)
1. Führen Sie im Ordner &quot;bin&quot;den Befehl Tomcat9w.exe (Common Daemon Service Manager) aus.

Fügen Sie auf der Registerkarte Java unter Java-Optionen eine neue Zeile hinzu:

```
-Djava.library.path=C:\Sensor directory
```

C:\Sensor directory is the directory containing the visual_sciences.dll.
