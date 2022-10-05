---
description: Für das Dashboard-Produkt ist eine von Adobe ClientCare bereitgestellte Lizenz erforderlich.
title: Angeben des Dashboard-Lizenzschlüssels
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# Angeben des Dashboard-Lizenzschlüssels{#add-dashboard-license-key}

{{eol}}

Für das Dashboard-Produkt ist eine von Adobe ClientCare bereitgestellte Lizenz erforderlich.

1. Öffnen **[!UICONTROL SQL Management Studio]** als Administrator.
1. Öffnen Sie die vom Dashboard erstellte Datenbank (z. B. thinclientdb).
1. Klicken Sie mit der rechten Maustaste auf die **[!UICONTROL Configuration]** Tabelle und klicken Sie auf **[!UICONTROL Edit Top 200 Rows]**.
1. Suchen Sie die **[!UICONTROL licenseKey]** und geben Sie den von Adobe ClientCare bereitgestellten Schlüssel in das Feld **[!UICONTROL Value]** Spalte.
1. Starten Sie den **[!UICONTROL Application Pool]** im **[!UICONTROL IIS Manager Console]**.
