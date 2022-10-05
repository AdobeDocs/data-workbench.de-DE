---
description: Die Arbeitsfläche erleichtert die Bestimmung des Speicherorts der einzelnen Arbeitsbereiche, sei es auf dem Data Workbench-Server, auf Ihrem lokalen Computer oder auf beiden Geräten.
title: Versionierung von Dateien
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
exl-id: 82a70d51-a95c-4ddd-8d3c-cd0364940693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 2%

---

# Versionierung von Dateien{#file-versioning}

{{eol}}

Die Arbeitsfläche erleichtert die Bestimmung des Speicherorts der einzelnen Arbeitsbereiche, sei es auf dem Data Workbench-Server, auf Ihrem lokalen Computer oder auf beiden Geräten.

## Dateiversionen identifizieren {#section-d555c96b016344f19b356c12213dd2a9}

**Server**

Ein Serverarbeitsbereich wird auf dem verbundenen Data Workbench-Server gespeichert und steht allen Benutzern zur Verfügung, die Zugriff auf dieses Profil und diese Registerkarte haben. Ein Server-Arbeitsbereich wird als einzelne Miniaturansicht angezeigt.

![](assets/wsp_thumb_server.png)

Server-Arbeitsbereiche werden standardmäßig im entsprechenden Unterordner im Ordner Arbeitsbereiche auf dem verbundenen Data Workbench-Server gespeichert.

**Lokal**

Ein lokaler Arbeitsbereich ist die lokale Version eines Server-Arbeitsbereichs. Ein lokaler Arbeitsbereich wird als zwei überlappende Miniaturansichten angezeigt. Die Miniaturansicht oben ist anfangs von einem Leuchten umgeben, was darauf hinweist, dass kürzlich erfolgte Änderungen lokal am Server-Arbeitsbereich vorgenommen wurden. Dieser Glanz verschwindet im Laufe der Zeit.

![](assets/wsp_thumb_local.png)

Lokale Arbeitsbereiche werden standardmäßig im [!DNL User\working profile name\Workspaces\tab] den Ordner &quot;name&quot;im Installationsverzeichnis der Data Workbench (oder Insight).

>[!NOTE]
>
>Wenn Sie eine lokale Version eines Server-Arbeitsbereichs haben, müssen Sie zur Server-Version zurückkehren, bevor Sie eine aktualisierte Version des Server-Arbeitsbereichs herunterladen können. Wenn Sie die Serverversion ohne lokale Änderungen wiederherstellen möchten, klicken Sie mit der rechten Maustaste auf die Miniaturansicht des lokalen Arbeitsbereichs und klicken Sie auf **[!UICONTROL Revert to server version]**.

**Benutzer**

Ein Benutzer-Workspace ist ein Arbeitsbereich, der in erstellt wurde und nur auf dem lokalen Computer vorhanden ist. Ein Benutzerarbeitsbereich wird als einzelne Miniaturansicht mit gepunkteten Umrissen eines leeren Arbeitsbereichs dahinter angezeigt, was darauf hinweist, dass auf dem verbundenen Data Workbench-Server kein Quellarbeitsbereich vorhanden ist.

![](assets/wsp_thumb_user.png)

Benutzerarbeitsbereiche werden standardmäßig im Ordner &quot;User\*Working profile name*\Workspaces\*tab name*&quot;im Insight-Installationsordner gespeichert.
