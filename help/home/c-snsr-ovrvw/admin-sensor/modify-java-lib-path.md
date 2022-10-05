---
description: Anweisungen zum Hinzufügen der Datei visual_sciences.dll zum Java-Bibliothekspfad von Tomcat.
title: Ändern des Pfads zur Java-Bibliothek
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
exl-id: bd853d95-3f44-4860-9965-c3210ec4adcf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 12%

---

# Ändern des Pfads zur Java-Bibliothek{#modify-the-java-library-path}

{{eol}}

Anweisungen zum Hinzufügen der Datei visual_sciences.dll zum Java-Bibliothekspfad von Tomcat.

1. Navigieren Sie auf Ihrem Windows-Server zum Installationsordner von Tomcat. (Tomcat > bin)
1. Führen Sie im Ordner &quot;bin&quot;Tomcat9w.exe (Common Daemon Service Manager) aus.

Fügen Sie auf der Registerkarte Java unter Java-Optionen eine neue Zeile hinzu:

```
-Djava.library.path=C:\Sensor directory
```

Wo C:\Sensor directory is the directory containing the visual_sciences.dll Datei.
