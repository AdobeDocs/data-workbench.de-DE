---
description: Schritte zum Installieren der erforderlichen Microsoft-Komponenten.
title: Installieren erforderlicher Komponenten
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# Installieren erforderlicher Komponenten{#installing-required-components}

Schritte zum Installieren der erforderlichen Microsoft-Komponenten.

1. Installieren Sie Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Dies muss erst nach der Installation und Konfiguration der IIS-Webrolle installiert werden.

1. Folgen Sie dem Assistenten und wählen Sie bei Aufforderung die Standardeinstellungen, um die Installation abzuschließen.
1. Vergewissern Sie sich nach der Installation, dass der ASP.NET v.4.0-Anwendungspool innerhalb der **[!UICONTROL Application Pools]**-Auflistung in IIS hinzugefügt wurde.
1. Installieren Sie die Microsoft SQL Server-Datenbank.

   Verwenden Sie eine beliebige Version von SQL Server 2008 oder 2008 R2 (Express wird unterstützt) mit Management Tools (Adobe empfiehlt SQL Server 2008 R2 SP1 - Express Edition). 1. Bei einer allgemeinen Installation ohne vorhandene SQL Server-Instanzen, die im Voraus ausgeführt werden, wählen Sie die Option **[!UICONTROL Default Instance]** im Bildschirm **[!UICONTROL Instance Configuration]**.
1. Für die übrigen Konfigurationsoptionen folgen Sie dem Assistenten und wählen die Standardeinstellungen, wenn Sie zum Abschluss der Installation aufgefordert werden.
1. Installieren Sie Microsoft Web Deploy v2.0.

   Bei den meisten Installationen ist die **[!UICONTROL Typical]** Installation in Ordnung. Wenn Sie jedoch eine Remote-Bereitstellung planen, müssen Sie eine vollständige Installation durchführen (wählen Sie **[!UICONTROL Complete]**).

   Sobald alle Voraussetzungen ordnungsgemäß installiert sind, können Sie die Data Workbench-Server für die Kommunikation mit dem Dashboard vorbereiten.
