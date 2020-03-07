---
description: Mit Worktop können Sie ganz einfach bestimmen, wo die einzelnen Arbeitsflächen gespeichert sind, ob auf dem Data Workbench-Server, auf Ihrem lokalen Computer oder auf beiden.
solution: Analytics
title: Dateiversionen
topic: Data workbench
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dateiversionen{#file-versioning}

Mit Worktop können Sie ganz einfach bestimmen, wo die einzelnen Arbeitsflächen gespeichert sind, ob auf dem Data Workbench-Server, auf Ihrem lokalen Computer oder auf beiden.

## Identifizieren von Dateiversionen {#section-d555c96b016344f19b356c12213dd2a9}

**Server**

Ein Serverarbeitsbereich wird auf dem angeschlossenen Data Workbench-Server gespeichert und steht allen Benutzern zur Verfügung, die Zugriff auf dieses Profil und diese Registerkarte haben. Ein Serverarbeitsbereich wird als einzelne Miniaturansicht angezeigt.

![](assets/wsp_thumb_server.png)

Server-Arbeitsbereiche werden standardmäßig im entsprechenden Unterordner im Ordner &quot;Workspaces&quot;auf dem angeschlossenen Data Workbench-Server gespeichert.

**lokal**

Ein lokaler Arbeitsbereich ist die lokale Version eines Serverarbeitsbereichs. Ein lokaler Arbeitsbereich wird als zwei überlappende Miniaturbilder angezeigt. Die Miniaturansicht oben ist anfangs von einem Schein umgeben, was darauf hinweist, dass kürzlich Änderungen lokal am Arbeitsbereich des Servers vorgenommen wurden. Dieser Schein verschwindet mit der Zeit.

![](assets/wsp_thumb_local.png)

Lokale Arbeitsbereiche werden standardmäßig im Ordner &quot; [!DNL User\working profile name\Workspaces\tab] name&quot;im Installationsordner von Data Workbench (oder Insight) gespeichert.

>[!NOTE]
>
>Wenn Sie über eine lokale Version eines Serverarbeitsbereichs verfügen, müssen Sie zur Serverversion zurückkehren, bevor Sie eine aktualisierte Version des Serverarbeitsbereichs herunterladen können. Wenn Sie ohne lokale Änderungen zur Serverversion zurückkehren möchten, klicken Sie mit der rechten Maustaste auf die Miniaturansicht des lokalen Arbeitsbereichs und klicken Sie auf **[!UICONTROL Revert to server version]**.

**Benutzer**

Ein Arbeitsbereich für Benutzer ist ein Arbeitsbereich, der auf dem lokalen Computer erstellt wurde und nur auf dem lokalen Computer vorhanden ist. Ein Arbeitsbereich des Benutzers wird als einzelne Miniaturansicht mit einer gepunkteten Umrisslinie eines leeren Arbeitsbereichs dahinter angezeigt. Dies weist darauf hin, dass auf dem angeschlossenen Data Workbench-Server kein Quellarbeitsbereich vorhanden ist.

![](assets/wsp_thumb_user.png)

Benutzerarbeitsflächen werden standardmäßig im Ordner &quot;Benutzer\*Arbeitsprofilname*\Workspaces\*tab name*&quot;im Installationsordner von Insight gespeichert.
