---
description: Segmente mithilfe des Segmentexportassistenten exportieren
title: Assistent für den Segmentexport
uuid: 705bdf00-54e5-4992-8978-91afda8c7543
exl-id: 6f42c5c6-a158-4ddd-8949-4ef55a44ed1c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 6%

---

# Assistent für den Segmentexport{#segment-export-wizard}

Segmente mithilfe des Segmentexportassistenten exportieren

Der Segmentexportassistent bietet einen schrittweisen Prozess zum Konfigurieren und Exportieren von Segmenten, anstatt [Segmente aus einer Detailtabelle](https://experienceleague.adobe.com/docs/data-workbench/using/client/export-data/c-sgmt-expt.html) zu exportieren.

## Segmente mithilfe des Assistenten exportieren {#section-b30f2699dbc7490bad18512b91cb0cb3}

Um den Assistenten zu öffnen, klicken Sie mit der rechten Maustaste in einen Arbeitsbereich und wählen Sie **Admin** > **Assistenten** > **Assistent zum Segmentexport** aus.

>[!NOTE]
>
>Es werden nur die Segmente erfasst, die vor dem Öffnen des Assistenten angewendet wurden. Außerdem können die über den Assistenten erstellten Segmentexporte keine externen Befehle erzeugen.

1. Wählen Sie die verschiedenen übergeordneten Ebenen der Dimensionen und Metriken aus, die zum Export hinzugefügt werden sollen.

   Die angezeigten Ebenen hängen vom ausgewählten Profil ab. Sie können mehrere Dimensionsebenen basierend auf dem Profil auswählen.

   ![](assets/seg_wizard_1.png)

1. Klicken Sie auf **Weiter**.
1. Wählen Sie die Dimension und die Metriken für die ausgewählten Ebenen aus.

   Nachdem Sie beispielsweise Seitenansicht als übergeordnete Ebene ausgewählt haben, können Sie die zu exportierenden untergeordneten Dimensionen und Metriken auswählen.

1. Klicken Sie auf **Weiter**.

   ![](assets/seg_wizard_2.png)

   ![](assets/seg_wizard_2_1.png)

1. Wählen Sie das Exportformat aus und geben Sie einen Namen für die Exportdatei ein.

   ![](assets/seg_wizard_3.png)

   CSV-, TSV-, Segmentexport- und Segmentexport mit Header-Typen müssen nicht gesondert konfiguriert werden. Die Konfigurationen für Profile und Zielgruppenexport, benutzerdefinierten Datensatzdienst und Adobe Target Export müssen jedoch in Schritt 3 vorgenommen werden. Sehen Sie sich beispielsweise die Konfigurationsfelder für Profile und Zielgruppenexport an. Konfigurieren Sie diese Exporttypen und klicken Sie auf **Weiter**.

   ![](assets/seg_wizard_3_1.png)

   ![](assets/seg_wizard_3_2.png)

   ![](assets/seg_wizard_3_3.png)

1. Konfigurieren Sie den ausgewählten Exporttyp.

   Kopfzeile: Wenn die Kopfzeile &quot;True&quot;ist, benennen Sie das Feld **Ausgabedatei** .

   Escape-Feld: Legen Sie **True** oder **False** fest.

   Reihenfolge der Felder : Wählen Sie ein Feld aus und verschieben Sie es nach oben oder unten, um die Reihenfolge in der Exportdatei festzulegen.

   ![](assets/seg_wizard_4.png)

   Klicken Sie auf **Weiter**.

1. Zeigen Sie die Ebene und die angewendeten Filter in diesem Dialogfeld an. Klicken Sie auf **Weiter**. ![](assets/seg_wizard_5.png)

1. Wenn **CSV**, **TSV**, **Segmentexport** oder **Segmentexport mit Header** ausgewählt ist, gibt es drei Optionen:

   Allgemeiner Export - Die Ausgabedatei wird vom Server im Ordner Server/Export generiert.

   ![](assets/seg_wizard_6.png)

   FTP-Export - Die Ausgabedatei wird auf den ausgewählten Server übertragen. (Die Liste des Servers wird aus der Datei FTPServerInfo.cfg ausgewählt.)

   ![](assets/seg_wizard_6_1.png)

   SFTP-Export : Die Ausgabedatei wird sicher auf den ausgewählten Server übertragen.

1. Klicken Sie auf **Weiter**

   **Hinweis:** Wenn der ausgewählte Exporttyp  **Profile und Zielgruppenexport**,  **Benutzerdefinierter Datensatzdienst** und  **Adobe Target Export** ist, ist der Text basierend auf dem ausgewählten Export statisch.

1. Konfigurieren Sie die Planungsparameter.

   **Ein** Shot kann auf True oder False festgelegt werden.

   **Die erweiterte** Planung kann durch Klicken auf die Schaltfläche Erweiterte Planungskonfiguration aktiviert oder deaktiviert werden.

   ![](assets/seg_wizard_7.png)

   Wie beim Exportieren aus der Detailtabelle verschwindet &quot;One Shot&quot;, wenn die erweiterte Einstellung aktiviert ist. Klicken Sie auf **Weiter**.

1. Zeigen Sie eine Vorschau der Exportdatei an und klicken Sie auf **Export ausführen**.

   ![](assets/seg_wizard_8.png)

   ![](assets/seg_wizard_8_1.png)

Die folgenden Exporttypen sind über den Assistenten verfügbar:

**Segmentexporttypen**

* Generisch  
* FTP
* SFTP

**Segmentexport mit Kopfzeile**

* Generisch  
* FTP
* SFTP

**CSV-Export**

* Generisch  
* FTP
* SFTP

**TSV-Export**

* Generisch  
* FTP
* SFTP
