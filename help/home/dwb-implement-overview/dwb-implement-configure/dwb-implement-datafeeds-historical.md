---
description: Eine kurze Anleitung für die erforderlichen Mindestschritte zum Validieren und Einrichten von historischen Daten-Feeds.
title: Validieren historischer Daten-Feeds
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
exl-id: 5a5e2cca-2fab-48a0-b58d-a8c46114b9a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 5%

---

# Validieren historischer Daten-Feeds{#validating-historical-data-feeds}

{{eol}}

Eine kurze Anleitung für die erforderlichen Mindestschritte zum Validieren und Einrichten von historischen Daten-Feeds.

## Validierungsschritte für die Konsistenz von Daten-Feeds {#section-777b2c627a354627a02feb9461e23038}

1. Anmelden bei *Zahnfleisch* (https://oasis.omniture.com/drteeth/)
1. Navigieren Sie zu SiteCatalyst Admin -> Daten-Feed-Definition (neu).
1. Wechseln Sie zum Server-Speicherort (z. B. Dallas, London..) Je nachdem, wo sich Ihr Unternehmen befindet.
1. Geben Sie RSID an, wählen Sie den Feed-Typ Insight aus und klicken Sie auf *suchen*.

   ![](assets/dwb_impl_historical.png)

1. Identifizieren Sie den tatsächlichen Feed-Namen für Ihren Client.
1. Klicken Sie im Abschnitt Aktionen auf Verlauf . ![](assets/dwb_impl_historical1.png)

   Überprüfen Sie das Statusfeld auf Fehler. Falls ein Feed einen Fehlerstatus aufweist, wählen Sie den Feed aus und klicken Sie auf &quot;Neu verarbeiten&quot;. Wenn der Fehler bei mehreren Anfragen aufgetreten ist, senden Sie eine E-Mail an *`dataworkbench@adobe.com`* mit Feed-ID- und Report Suite-Details zur erneuten Verarbeitung.

1. Nach der Validierung werden die Protokolle im Rohordner des NAS-Speicherorts überprüft.
