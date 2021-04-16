---
description: Mit Worktop können Sie ganz einfach bestimmen, wo die einzelnen Arbeitsflächen gespeichert sind, ob sie sich auf dem Data Workbench-Server, auf Ihrem lokalen Computer oder auf beiden befinden.
title: Versionierung von Dateien
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
exl-id: 82a70d51-a95c-4ddd-8d3c-cd0364940693
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 2%

---

# Versionierung von Dateien{#file-versioning}

Mit Worktop können Sie ganz einfach bestimmen, wo die einzelnen Arbeitsflächen gespeichert sind, ob sie sich auf dem Data Workbench-Server, auf Ihrem lokalen Computer oder auf beiden befinden.

## Identifizieren von Dateiversionen {#section-d555c96b016344f19b356c12213dd2a9}

**Server**

Ein Serverarbeitsbereich wird auf dem Server der angeschlossenen Data Workbench gespeichert und steht allen Benutzern zur Verfügung, die Zugriff auf dieses Profil und diese Registerkarte haben. Ein Serverarbeitsbereich wird als einzelne Miniaturansicht angezeigt.

![](assets/wsp_thumb_server.png)

Serverarbeitsflächen werden standardmäßig im entsprechenden Unterordner im Ordner &quot;Workspaces&quot;auf dem angeschlossenen Data Workbench-Server gespeichert.

**lokal**

Ein lokaler Arbeitsbereich ist die lokale Version eines Serverarbeitsbereichs. Ein lokaler Arbeitsbereich wird als zwei überlappende Miniaturbilder angezeigt. Die Miniaturansicht oben ist anfangs von einem Schein umgeben, was darauf hinweist, dass kürzlich Änderungen lokal am Arbeitsbereich des Servers vorgenommen wurden. Dieser Schein verschwindet mit der Zeit.

![](assets/wsp_thumb_local.png)

Lokale Arbeitsbereiche werden standardmäßig im Ordner [!DNL User\working profile name\Workspaces\tab] name im Installationsordner von Data Workbench (oder Insight) gespeichert.

>[!NOTE]
>
>Wenn Sie über eine lokale Version eines Serverarbeitsbereichs verfügen, müssen Sie zur Serverversion zurückkehren, bevor Sie eine aktualisierte Version des Serverarbeitsbereichs herunterladen können. Wenn Sie ohne lokale Änderungen zur Serverversion zurückkehren möchten, klicken Sie mit der rechten Maustaste auf die Miniaturansicht des lokalen Arbeitsbereichs und klicken Sie auf **[!UICONTROL Revert to server version]**.

**Benutzer**

Ein Arbeitsbereich für Benutzer ist ein Arbeitsbereich, der auf dem lokalen Computer erstellt wurde und nur auf dem lokalen Computer vorhanden ist. Ein Benutzerarbeitsbereich wird als einzelne Miniaturansicht mit einer gepunkteten Umrisslinie eines leeren Arbeitsbereichs dahinter angezeigt. Dies weist darauf hin, dass auf dem angeschlossenen Data Workbench-Server kein Quellarbeitsbereich vorhanden ist.

![](assets/wsp_thumb_user.png)

Benutzerarbeitsflächen werden standardmäßig im Ordner &quot;User\*working Profil name*\Workspaces\*tab name*&quot;im Insight-Installationsordner gespeichert.
