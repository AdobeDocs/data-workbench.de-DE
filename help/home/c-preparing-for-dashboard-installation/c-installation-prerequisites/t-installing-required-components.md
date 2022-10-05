---
description: Schritte zum Installieren der erforderlichen Microsoft-Komponenten.
title: Installieren erforderlicher Komponenten
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# Installieren erforderlicher Komponenten{#installing-required-components}

{{eol}}

Schritte zum Installieren der erforderlichen Microsoft-Komponenten.

1. Installieren Sie Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Diese muss erst nach der Installation und Konfiguration der IIS-Web-Rolle installiert werden.

1. Führen Sie den Assistenten aus und wählen Sie die Standardeinstellungen aus, wenn Sie dazu aufgefordert werden, die Installation abzuschließen.
1. Überprüfen Sie nach der Installation, ob der ASP.NET v.4.0-Anwendungspool im **[!UICONTROL Application Pools]** Auflistung in IIS.
1. Installieren Sie die Microsoft SQL Server-Datenbank.

   Verwenden Sie eine beliebige Version von SQL Server 2008 oder 2008 R2 (Express wird unterstützt) mit Management Tools (Adobe empfiehlt SQL Server 2008 R2 SP1 - Express Edition). 1. Für eine generische Installation, ohne dass vorhandene SQL Server-Instanzen vorzeitig ausgeführt werden, wählen Sie bitte die **[!UICONTROL Default Instance]** -Option auf **[!UICONTROL Instance Configuration]** angezeigt.
1. Für die restlichen Konfigurationsoptionen folgen Sie dem Assistenten und wählen Sie Standardeinstellungen, wenn Sie dazu aufgefordert werden, die Installation abzuschließen.
1. Installieren Sie Microsoft Web Deployment v2.0.

   Bei den meisten Installationen wird die Variable **[!UICONTROL Typical]** Installation ist in Ordnung. Wenn Sie jedoch eine Remote-Bereitstellung planen, müssen Sie eine vollständige Installation durchführen (wählen Sie **[!UICONTROL Complete]**).

   Sobald alle Voraussetzungen ordnungsgemäß installiert sind, können Sie die Data Workbench-Server für die Kommunikation mit dem Dashboard vorbereiten.
