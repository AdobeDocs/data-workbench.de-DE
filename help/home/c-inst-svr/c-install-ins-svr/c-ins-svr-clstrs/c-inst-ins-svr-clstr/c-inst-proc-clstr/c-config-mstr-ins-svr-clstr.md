---
description: Informationen zum Konfigurieren des Clusters auf dem Übergeordnet Insight Server, zum Aktualisieren der Zugriffssteuerungsdatei für einen Cluster und mehr.
title: Konfigurieren des Master-Insight-Servers für das Clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Konfigurieren des Master-Insight-Servers für das Clustering{#configuring-the-master-insight-server-for-clustering}

Informationen zum Konfigurieren des Clusters auf dem Übergeordnet Insight Server, zum Aktualisieren der Zugriffssteuerungsdatei für einen Cluster und mehr.

Um den Cluster zu konfigurieren, führen Sie die folgenden Schritte für den Übergeordneten Ordner [!DNL Insight Server] aus:

* Fügen Sie der Adressdatei die [!DNL Insight Servers’] allgemeinen Namen und Adressen der Verarbeitung hinzu.
* Fügen Sie alle [!DNL Insight Servers] zur Gruppe der Cluster-Server in der Datei [!DNL Access Control.cfg] hinzu.

* Aktualisieren Sie die Datei [!DNL Synchronize.cfg] im Verzeichnis &quot;Components for Processing Servers&quot;, um auf den Übergeordneten Ordner [!DNL Insight Server] zu verweisen.

* Ändern Sie bei Bedarf die Datei [!DNL Disk Files.cfg] im Verzeichnis &quot;Components for Processing Servers&quot;, um den Speicherort der Datei [!DNL temp.db] für die Verarbeitung [!DNL Insight Servers] anzugeben.

Um diese Schritte durchzuführen, müssen Sie die allgemeinen Namen (wie in den digitalen Zertifikaten für die Person [!DNL Insight Server] angegeben) und die IP-Adressen der einzelnen [!DNL Insight Server] im Cluster kennen. Wenn Sie noch nicht über diese Informationen verfügen, rufen Sie sie ab, bevor Sie fortfahren.

>[!NOTE]
>
>Die in diesem Abschnitt beschriebenen Verfahren erfordern [!DNL Insight]. Wenn Sie [!DNL Insight] nicht installiert haben, befolgen Sie die Anweisungen im **[!DNL Insight]Benutzerhandbuch**, bevor Sie fortfahren.

## Hinzufügen der verarbeitenden Insight Server zur Adressdatei {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Gehen Sie wie folgt vor, um die Verarbeitungs-[!DNL Insight Servers’]-allgemeinen Namen und IP-Adressen zur Adressdatei im Übergeordneten [!DNL Insight Server] hinzuzufügen. (Obwohl die Adressdatei auf dem Übergeordneten [!DNL Insight Server] verwaltet wird, wird sie von allen [!DNL Insight Servers] im Cluster verwendet.)

>[!NOTE]
>
>Im Folgenden wird davon ausgegangen, dass die Adressdatei bereits für das Übergeordnete [!DNL Insight Server] konfiguriert wurde. Wenn Sie die Übergeordneten [!DNL Insight Server’s] IP-Adressen noch nicht zur Adressdatei hinzugefügt haben, führen Sie das unter [Definieren des Netzwerkstandorts des Servers](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) beschriebene Verfahren aus, bevor Sie beginnen.

**Hinzufügen der Verarbeitung  [!DNL Insight Servers] zur Adressdatei**

1. Starten Sie [!DNL Insight] und laden Sie das Konfigurationsprofil (sofern es noch nicht geöffnet ist), indem Sie mit der rechten Maustaste auf die Titelleiste klicken und **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]** klicken.

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Übergeordneten **[!UICONTROL Insight Server]** und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie im Verzeichnis [!DNL Server Files Manager] das Verzeichnis Adressen und öffnen Sie die Adressdatei [!DNL Insight Server’s] wie folgt:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie den Inhalt der [!DNL Locations]-Struktur und erweitern Sie dann NetworkLocation 0, Addresses und AddressDefinition.
1. Gehen Sie wie folgt vor, um eine AddressDefinition zu NetworkLocation 0 für jede Verarbeitung von [!DNL Insight Server] im Cluster hinzuzufügen:

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL AddressDefinition]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Geben Sie im Parameter &quot;Name&quot;den allgemeinen Verarbeitungsnamen [!DNL Insight Server’s] an.
   1. Geben Sie im Parameter Adresse die IP-Adresse für die Verarbeitung der [!DNL Insight Server’s] an.

      Sie können ein Sternchen als Platzhalter im Feld Adresse verwenden, z. B. 10.10.116.*, um das Clustering zu vereinfachen. Siehe [Grundlegendes zu Zugriffsebenen](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      Das folgende Beispiel definiert einen Cluster, der zwei [!DNL Insight Servers] enthält:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Wenn die Server mit mehreren Netzwerken verbunden sind, wiederholen Sie Schritt 6, um die Verarbeitung [!DNL Insight Servers] zu den NetworkLocations für diese Netzwerke hinzuzufügen.

   Das folgende Beispiel zeigt einen Cluster von vier [!DNL Insight Servers], die an zwei Netzwerke (&quot;Corporate Intranet&quot; und &quot;Internet&quot;) angeschlossen sind.

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Aktualisieren der Zugriffssteuerungsdatei für einen Cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Um [!DNL Insight Servers] in einem Cluster zu verwenden, muss jede [!DNL Insight Server] im Cluster (einschließlich der Übergeordneten [!DNL Insight Server]) zur Zugriffskontrollgruppe für Cluster-Server gehören. Die Gruppe Cluster-Server identifiziert die Server (nach IP-Adresse), die für die Teilnahme am Cluster berechtigt sind. Obwohl diese Datei auf dem Übergeordneten [!DNL Insight Server] verwaltet und verwaltet wird, wird sie von allen [!DNL Insight Servers] im Cluster verwendet.

**So bearbeiten Sie die Zugriffssteuerungsdatei**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Übergeordneten [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie im Ordner [!DNL Server Files Manager] den Ordner Zugriffskontrolle .
1. Gehen Sie wie folgt vor, um die Datei [!DNL Access Control.cfg] zu öffnen:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie die Struktur Zugriffssteuerungsgruppen und erweitern Sie dann AccessGroup (Cluster-Server).
1. Führen Sie für jeden [!DNL Insight Server] im Cluster (einschließlich der Übergeordneten [!DNL Insight Server]) folgende Schritte aus:

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Members]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Geben Sie die IP-Adresse [!DNL Insight Server’s] (ihre numerische IP-Adresse, nicht den Namen) an. Wenn die [!DNL Insight Servers] mit mehreren Netzwerken verbunden sind, sollte diese AccessGroup nur die internen Adressen enthalten, die die [!DNL Insight Servers] für die Kommunikation zwischen Servern im Cluster verwenden.

      Im Folgenden sehen Sie die AccessGroup (Cluster-Server) für einen Cluster von vier [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der Spalte [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Konfigurieren der Synchronisierungsdatei {#section-d23e751771c84da6bab6a34a8db867bc}

Sie können das folgende Verfahren verwenden, um die zentrale Kopie der Datei [!DNL Synchronize.cfg] zu konfigurieren. Die zentrale Kopie dieser Datei wird auf dem Übergeordneten [!DNL Insight Server] aufbewahrt. Die Verarbeitung [!DNL Insight Servers] im Cluster initiiert die Kommunikation mit dem Übergeordneten [!DNL Insight Server], um eine aktualisierte Kopie dieser Datei abzurufen.

Die Datei [!DNL Synchronize.cfg] gibt den Speicherort des Übergeordneten [!DNL Insight Server] an. Er gibt auch den Satz von Verwaltungsdateien an, die von jeder Verarbeitung von [!DNL Insight Servers] im Cluster aus dem Übergeordneten [!DNL Insight Server] abgerufen werden. Die Verarbeitung [!DNL Insight Servers] lädt diese Dateien automatisch vom Übergeordneten [!DNL Insight Server] herunter, wenn sie beginnt. Außerdem werden aktualisierte Kopien dieser Dateien dynamisch aus dem Übergeordneten [!DNL Insight Server] abgerufen, wenn sich die Dateien ändern.

>[!NOTE]
>
>Obwohl Sie die Datei [!DNL Synchronize.cfg] auf dem Übergeordneten [!DNL Insight Server] konfigurieren, verwendet das Übergeordnete [!DNL Insight Server] selbst diese Datei nicht. Sie aktualisieren diese Datei auf dem Übergeordneten [!DNL Insight Server], sodass sie ordnungsgemäß konfiguriert ist, wenn die Verarbeitung [!DNL Insight Servers] die Datei abruft.

**Aktualisieren der Datei &quot;Synchronize.cfg&quot;auf dem Übergeordneten[!DNL Insight Server]**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Übergeordneten [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie in [!DNL Server Files Manager] den Ordner **[!UICONTROL Components]** für Verarbeitungsserver .

1. Gehen Sie wie folgt vor, um [!DNL Synchronize.cfg] zu öffnen:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen [!DNL Temp] und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie die Komponentenstruktur.
1. Geben Sie im Parameter Primäre Serveradresse des Clusters die IP-Adresse des Übergeordneten (primären) **[!UICONTROL Insight Server]** an.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Um ein Protokoll zu erstellen, das jedes Mal, wenn eine Synchronisation zwischen dem Übergeordneten [!DNL Insight Server] und der Verarbeitung von [!DNL Insight Servers] erfolgt, stellen Sie sicher, dass der Parameter Synchronisierungsprotokoll aktivieren auf &quot;true&quot;gesetzt ist.

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Konfigurieren des Datensatzstandorts (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Führen Sie das folgende Verfahren aus, wenn Sie möchten, dass die Verarbeitung von [!DNL Insight Servers] [!DNL temp.db] (den Datensatz) in einem Verzeichnis oder Laufwerk verbleibt, das sich vom Standardspeicherort unterscheidet, oder wenn Sie [!DNL temp.db] über mehrere Laufwerke verteilen möchten.

>[!NOTE]
>
>Da die Verarbeitung von [!DNL Insight Servers] alle denselben [!DNL Disk Files.cfg]-Pfad aufweisen, müssen sie alle den/die Dateispeicherort(e) unterstützen, den/die Sie in dieser Datei angeben. Wenn Sie beispielsweise [!DNL temp.db] dem E zuweisen: Laufwerk, muss jede Verarbeitung von [!DNL Insight Server] im Cluster einen E-Wert aufweisen: Laufwerk.

**So konfigurieren Sie den Speicherort von &quot;temp.db&quot;**

1. Klicken Sie in [!DNL Insight] auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die Miniaturansicht **[!UICONTROL Servers Manager]** , um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Übergeordneten [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie im Verzeichnis [!DNL Server Files Manager] das Verzeichnis **[!UICONTROL Components for Processing Servers]** .

1. Gehen Sie wie folgt vor, um [!DNL Disk Files.cfg] zu öffnen:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte [!DNL Temp]und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie die Struktur DiskSpaceManagerComponent und erweitern Sie dann die Liste Disk Files .
1. Bearbeiten Sie Eintrag 0 , um den Speicherort der Datei [!DNL temp.db] zu ändern.
1. Wenn Sie [!DNL temp.db] über mehrere Laufwerke verteilen möchten, führen Sie die folgenden Schritte aus, um einen zusätzlichen Eintrag für jedes zusätzliche Laufwerk zu erstellen.

   1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Disk Files]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Geben Sie im neuen Eintrag den Speicherort an, an dem [!DNL temp.db] geschrieben werden soll.
   Die folgende Abbildung zeigt [!DNL temp.db], die über vier Laufwerke geschrieben wurde.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Klicken Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in [!DNL Server Files Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL Temp] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
