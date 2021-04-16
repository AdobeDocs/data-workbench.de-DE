---
description: Für das Dashboard-Produkt ist eine Lizenz erforderlich, die von Adobe ClientCare bereitgestellt wird.
title: Angeben des Dashboard-Lizenzschlüssels
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# Angeben des Dashboard-Lizenzschlüssels{#add-dashboard-license-key}

Für das Dashboard-Produkt ist eine Lizenz erforderlich, die von Adobe ClientCare bereitgestellt wird.

1. Öffnen Sie **[!UICONTROL SQL Management Studio]** als Administrator.
1. Öffnen Sie die von Dashboard erstellte Datenbank (z. B. thinclientdb).
1. Klicken Sie mit der rechten Maustaste auf die Tabelle **[!UICONTROL Configuration]** und klicken Sie auf **[!UICONTROL Edit Top 200 Rows]**.
1. Suchen Sie das Feld **[!UICONTROL licenseKey]** und geben Sie den von Adobe ClientCare bereitgestellten Schlüssel in die Spalte **[!UICONTROL Value]** ein.
1. Starten Sie **[!UICONTROL Application Pool]** in **[!UICONTROL IIS Manager Console]** neu.
