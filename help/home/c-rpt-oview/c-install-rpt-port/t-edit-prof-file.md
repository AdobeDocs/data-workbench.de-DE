---
description: Um die Profile anzugeben, die im Report Portal verfügbar sein sollen, müssen Sie die Datei "profiles.xml"konfigurieren.
solution: Analytics
title: Bearbeiten der Datei "Profiles.xml"
topic: Data workbench
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bearbeiten der Datei &quot;Profiles.xml&quot;{#edit-the-profiles-xml-file}

Um die Profile anzugeben, die im Report Portal verfügbar sein sollen, müssen Sie die Datei &quot;profiles.xml&quot;konfigurieren.

Die [!DNL profiles.xml] Datei befindet sich in dem Ordner, den Sie für die Ausgabe festgelegt haben. Standardmäßig befindet sie sich im Ordner \*PortalName*\PortalFiles\Output folder.

**So fügen Sie der Datei &quot;profiles.xml&quot;Profilnamen hinzu**

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die [!DNL profiles.xml] Datei in einem Texteditor wie Notepad.
1. Fügen Sie ein Profilelement und -tag für jedes Element [!DNL Profile] in Ihrem Portal hinzu, wie im folgenden Beispiel:

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
