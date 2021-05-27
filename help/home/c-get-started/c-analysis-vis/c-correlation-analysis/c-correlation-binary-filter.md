---
description: Mit einem binären Filter in der Korrelationsmatrix können Sie Werte für eine oder beide korrelierte Metriken einschränken, um den Vergleich besser zu fokussieren.
title: Binärfilter in der Korrelationsmatrix
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# Binärfilter in der Korrelationsmatrix{#binary-filter-in-the-correlation-matrix}

Mit einem binären Filter in der Korrelationsmatrix können Sie Werte für eine oder beide korrelierte Metriken einschränken, um den Vergleich besser zu fokussieren.

So legen Sie einen Binärfilter für eine Korrelationsmatrix fest:

1. Klicken Sie in der Korrelationsmatrix mit der rechten Maustaste auf einen Metriknamen.
1. Wählen Sie **Metrikdetails bearbeiten** aus.

   ![](assets/correlation_matrix_binary_filter.png)

   Das Fenster **[!UICONTROL Edit Correlation Metric Details]** wird geöffnet.

   ![](assets/correlation_matrix_metric_details.png)

1. Richten Sie einen Binärfilter ein.

   Klicken Sie zunächst auf die Einstellung **[!UICONTROL Inactive]** . Es wird umgeschaltet, den Filter auf **[!UICONTROL Active]** festzulegen und die Felder **Vergleich** und **Wert** anzuzeigen.

   Wählen Sie dann einen **[!UICONTROL Comparison]** -Operator und legen Sie dessen **[!UICONTROL Value]** fest, um einen Filter für die ausgewählte Metrik einzurichten.

>[!IMPORTANT]
>
>Der Binärfilter für Data Workbench 6.2 wurde mit neuen Funktionen aktualisiert, sodass Sie jede Korrelationsmatrix mit einem in früheren Versionen erstellten Binärfilter neu erstellen müssen.

## Hinzufügen von Dimension-Elementen {#section-f19f4e0368ca488e92d1e28bcc24417c}

Sie können auch ein Dimensionselement hinzufügen, um eine Metrik einzuschränken. Einer Metrik kann nur ein Element zugeordnet sein.

![](assets/correlation_matrix_element.png)

Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **Tabelle** aus. Öffnen Sie eine Dimension mit ihren Elementen und ziehen Sie im Fenster Korrelationsmetrikdetails bearbeiten zur Einstellung **[!UICONTROL Element]** oder legen Sie eine Metrik in der Korrelationsmatrix ab.
