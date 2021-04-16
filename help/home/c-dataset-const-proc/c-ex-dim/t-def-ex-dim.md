---
description: Schritte zum Definieren erweiterter Dimensionen.
title: Definieren erweiterter Dimensionen
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# Definieren erweiterter Dimensionen{#defining-extended-dimensions}

Schritte zum Definieren erweiterter Dimensionen.

1. Öffnen Sie beim Arbeiten im DataSet-Profil das [!DNL Profile Manager] und klicken Sie auf **[!UICONTROL Dataset]**, um den Inhalt anzuzeigen.
1. Öffnen Sie die Datei [!DNL Transformation.cfg] oder die Datei [!DNL Transformation Dataset Include], in der Sie die erweiterte Dimension definieren möchten.

   * (Empfohlen) Informationen zum Öffnen einer Include-Datei für einen Datensatz finden Sie unter [Data Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >Adobe empfiehlt, erweiterte Dimensionen in einer oder mehreren neuen [!DNL Transformation Dataset Include]-Dateien zu definieren. Weitere Informationen finden Sie unter [Erstellen eines neuen Datensatzes einschließlich Dateien](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e).

   * Informationen zum Öffnen der Datei [!DNL Transformation.cfg] finden Sie unter [Bearbeiten der Transformationskonfigurationsdatei](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Transformations]** und klicken Sie auf **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]***.
1. Geben Sie die entsprechenden Informationen für Ihre erweiterte Dimension ein. Beschreibungen der Transformationstypen und Informationen zu ihren Parametern finden Sie in den folgenden Abschnitten:

   * [Zählbare Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [Einfache Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [Viele-zu-viele-Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [Numerische Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [Denormale Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [Zeitdimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      Für alle von Ihnen definierten erweiterten Dimensionen können Sie dem Parameter &quot;Kommentare&quot;eine oder mehrere Kommentarzeilen hinzufügen, um die Dimension weiter zu beschreiben oder Anmerkungen zur Verwendung hinzuzufügen. Um einen Kommentar hinzuzufügen, klicken Sie mit der rechten Maustaste auf die Beschriftung **[!UICONTROL Comments]** und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. Nachdem Sie die erweiterte(n) Dimension(en) in der Konfigurationsdatei definiert haben, speichern Sie die Datei lokal und speichern Sie sie im DataSet-Profil auf dem Data Workbench-Server.
