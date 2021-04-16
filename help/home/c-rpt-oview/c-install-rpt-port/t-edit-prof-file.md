---
description: Um die Profil anzugeben, die in Report Portal verfügbar sein sollen, müssen Sie die Datei "Profils.xml"konfigurieren.
title: Bearbeiten der Datei „Profiles.xml“
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# Bearbeiten der Datei „Profiles.xml“{#edit-the-profiles-xml-file}

Um die Profil anzugeben, die in Report Portal verfügbar sein sollen, müssen Sie die Datei &quot;Profils.xml&quot;konfigurieren.

Die Datei [!DNL profiles.xml] befindet sich in dem Ordner, den Sie für die Ausgabe festgelegt haben. Standardmäßig befindet sie sich im Ordner \*PortalName*\PortalFiles\Output folder.

**So fügen Sie der Datei &quot;Profils.xml&quot;Profil hinzu**

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die Datei [!DNL profiles.xml] in einem Texteditor wie Notepad.
1. hinzufügen Sie ein Profil-Element und -Tag für jedes [!DNL Profile] in Ihrem Portal, wie im folgenden Beispiel:

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
