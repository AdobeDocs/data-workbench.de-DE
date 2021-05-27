---
description: Um die Profile anzugeben, die in Report Portal verfügbar sein sollen, müssen Sie die Datei profiles.xml konfigurieren.
title: Bearbeiten der Datei „Profiles.xml“
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# Bearbeiten der Datei „Profiles.xml“{#edit-the-profiles-xml-file}

Um die Profile anzugeben, die in Report Portal verfügbar sein sollen, müssen Sie die Datei profiles.xml konfigurieren.

Die Datei [!DNL profiles.xml] befindet sich in dem Ordner, den Sie für die Ausgabe vorgesehen haben. Standardmäßig befindet er sich im Ordner \*PortalName*\PortalFiles\Output folder.

**Hinzufügen von Profilnamen zur Datei &quot;profiles.xml&quot;**

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die Datei [!DNL profiles.xml] in einem Texteditor wie Notepad.
1. Fügen Sie für jedes [!DNL Profile] in Ihrem Portal ein Profilelement und ein Tag hinzu, wie im folgenden Beispiel gezeigt:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. Speichern und schließen Sie die Datei.
