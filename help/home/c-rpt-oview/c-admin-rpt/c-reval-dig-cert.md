---
description: Nach der Installation fungiert das von der Adobe ausgestellte digitale Zertifikat als Schlüssel, mit dem Sie Report Server ausführen können.
title: Erneute Validierung des digitalen Zertifikats
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 13%

---

# Erneute Validierung des digitalen Zertifikats{#re-validating-the-digital-certificate}

Nach der Installation fungiert das von der Adobe ausgestellte digitale Zertifikat als Schlüssel, mit dem Sie Report Server ausführen können.

**Empfohlene Häufigkeit:** Nach Bedarf

Um ordnungsgemäß funktionieren zu können, muss ein digitales Zertifikat aktuell sein.

Um auf dem neuesten Stand zu bleiben, muss Ihr digitales Zertifikat regelmäßig erneut validiert werden (im Allgemeinen alle 30 Tage, dies kann jedoch je nach Vereinbarung mit der Adobe variieren). Wenn Ihr Computer über Internetzugang verfügt, ist der Erneuerungsvorgang vollkommen transparent. [!DNL Report Server] stellt automatisch eine Verbindung zum Lizenzserver der Adobe her und überprüft das Zertifikat bei Bedarf erneut. Wenn Ihr Computer keinen Internetzugriff hat, müssen Sie ein neues, validiertes Zertifikat vom Adobe License Server herunterladen und auf Ihrem Computer installieren, indem Sie die unter [Herunterladen und Installieren des digitalen Zertifikats](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76) beschriebenen Schritte durchführen.
