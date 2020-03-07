---
description: Eine kurze Anleitung für die Mindestanforderungen, die zum Überprüfen und Einrichten von Verlaufsdaten-Feeds erforderlich sind.
title: Validieren von historischen Datenfeeds
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Validieren von historischen Datenfeeds{#validating-historical-data-feeds}

Eine kurze Anleitung für die Mindestanforderungen, die zum Überprüfen und Einrichten von Verlaufsdaten-Feeds erforderlich sind.

## Validierungsschritte für die Konsistenz von Datenfeeds {#section-777b2c627a354627a02feb9461e23038}

1. Anmelden bei *DRUCC* (https://oasis.omniture.com/drteeth/)
1. Gehen Sie zu SiteCatalyst Admin -> Data Feed-Definition(neu)
1. Springen zum Serverstandort (z. B. Dallas, London..) Je nachdem, wo sich Ihr Unternehmen befindet.
1. Geben Sie RSID an, wählen Sie den Feed-Typ Insight und klicken Sie auf die *Suche*.

   ![](assets/dwb_impl_historical.png)

1. Identifizieren Sie den tatsächlichen Feed-Namen für Ihren Client.
1. Klicken Sie im Abschnitt Aktionen auf Verlauf. ![](assets/dwb_impl_historical1.png)

   Überprüfen Sie das Statusfeld auf Fehler. Falls sich ein Feed im Fehlerstatus befindet, wählen Sie den Feed aus und klicken Sie auf &quot;Neu verarbeiten&quot;. Wenn der Fehler bei mehreren Anforderungen auftrat, senden Sie eine E-Mail zur erneuten Verarbeitung an *`dataworkbench@adobe.com`* die mit Feed-ID und Report Suite-Details.

1. Nach der Überprüfung werden die Protokolle im Rohordner des NAS-Speicherorts überprüft.

