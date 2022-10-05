---
description: Mit einem binären Filter in der Korrelationsmatrix können Sie Werte für eine oder beide korrelierte Metriken einschränken, um den Vergleich besser zu fokussieren.
title: Binärfilter in der Korrelationsmatrix
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# Binärfilter in der Korrelationsmatrix{#binary-filter-in-the-correlation-matrix}

{{eol}}

Mit einem binären Filter in der Korrelationsmatrix können Sie Werte für eine oder beide korrelierte Metriken einschränken, um den Vergleich besser zu fokussieren.

So legen Sie einen Binärfilter für eine Korrelationsmatrix fest:

1. Klicken Sie in der Korrelationsmatrix mit der rechten Maustaste auf einen Metriknamen.
1. Auswählen **Metrikdetails bearbeiten**.

   ![](assets/correlation_matrix_binary_filter.png)

   Die **[!UICONTROL Edit Correlation Metric Details]** wird geöffnet.

   ![](assets/correlation_matrix_metric_details.png)

1. Richten Sie einen Binärfilter ein.

   Klicken Sie zunächst auf die **[!UICONTROL Inactive]** -Einstellung. Dadurch wird der Filter umgeschaltet als **[!UICONTROL Active]** und zeigen Sie die **Vergleich** und **Wert** -Felder.

   Wählen Sie anschließend eine **[!UICONTROL Comparison]** -Operator und legen Sie **[!UICONTROL Value]** , um einen Filter für die ausgewählte Metrik einzurichten.

>[!IMPORTANT]
>
>Der Binärfilter für Data Workbench 6.2 wurde mit neuen Funktionen aktualisiert, sodass Sie jede Korrelationsmatrix mit einem in früheren Versionen erstellten Binärfilter neu erstellen müssen.

## Hinzufügen von Dimension-Elementen {#section-f19f4e0368ca488e92d1e28bcc24417c}

Sie können auch ein Dimensionselement hinzufügen, um eine Metrik einzuschränken. Einer Metrik kann nur ein Element zugeordnet sein.

![](assets/correlation_matrix_element.png)

Klicken Sie mit der rechten Maustaste in den Arbeitsbereich und wählen Sie **Verzeichnis**. Öffnen Sie eine Dimension mit ihren Elementen und ziehen Sie sie auf die **[!UICONTROL Element]** im Fenster Korrelationsmetrikdetails bearbeiten oder eine Metrik in der Korrelationsmatrix ablegen.
