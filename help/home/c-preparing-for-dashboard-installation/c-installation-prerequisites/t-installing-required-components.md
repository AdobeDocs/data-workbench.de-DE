---
description: Schritte zum Installieren der erforderlichen Microsoft-Komponenten.
solution: Analytics
title: Erforderliche Komponenten installieren
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Erforderliche Komponenten installieren{#installing-required-components}

Schritte zum Installieren der erforderlichen Microsoft-Komponenten.

1. Installieren Sie Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Dies muss erst nach der Installation und Konfiguration der IIS-Webrolle installiert werden.

1. Folgen Sie dem Assistenten und wählen Sie bei Aufforderung die Standardeinstellungen, um die Installation abzuschließen.
1. Vergewissern Sie sich nach der Installation, dass der ASP.NET v.4.0-Anwendungspool in der **[!UICONTROL Application Pools]** Liste in IIS hinzugefügt wurde.
1. Installieren Sie die Microsoft SQL Server-Datenbank.

   Verwenden Sie eine beliebige Version von SQL Server 2008 oder 2008 R2 (Express wird unterstützt) mit Management Tools (Adobe empfiehlt SQL Server 2008 R2 SP1 - Express Edition). 1. Bei einer allgemeinen Installation ohne vorhandene SQL Server-Instanzen, die im Voraus ausgeführt werden, wählen Sie die **[!UICONTROL Default Instance]** Option auf dem **[!UICONTROL Instance Configuration]** Bildschirm.
1. Für die übrigen Konfigurationsoptionen folgen Sie dem Assistenten und wählen die Standardeinstellungen, wenn Sie zum Abschluss der Installation aufgefordert werden.
1. Installieren Sie Microsoft Web Deploy v2.0.

   Bei den meisten Installationen ist die **[!UICONTROL Typical]** Installation in Ordnung. Wenn Sie jedoch eine Remote-Bereitstellung planen, müssen Sie eine vollständige Installation durchführen (wählen Sie **[!UICONTROL Complete]**).

   Sobald alle Voraussetzungen ordnungsgemäß installiert sind, können Sie die Data Workbench-Server für die Kommunikation mit dem Dashboard vorbereiten.
