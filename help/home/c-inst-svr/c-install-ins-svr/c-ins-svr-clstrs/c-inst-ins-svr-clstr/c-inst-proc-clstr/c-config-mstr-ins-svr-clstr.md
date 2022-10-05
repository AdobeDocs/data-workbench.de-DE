---
description: Informationen zum Konfigurieren des Clusters auf dem Übergeordnet Insight Server, zum Aktualisieren der Zugriffssteuerungsdatei für einen Cluster und mehr.
title: Konfigurieren des Master-Insight-Servers für das Clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Konfigurieren des Master-Insight-Servers für das Clustering{#configuring-the-master-insight-server-for-clustering}

{{eol}}

Informationen zum Konfigurieren des Clusters auf dem Übergeordnet Insight Server, zum Aktualisieren der Zugriffssteuerungsdatei für einen Cluster und mehr.

Um den Cluster zu konfigurieren, führen Sie die folgenden Schritte auf dem Übergeordneten [!DNL Insight Server]:

* Verarbeitung hinzufügen [!DNL Insight Servers’] allgemeine Namen und Adressen in der Adressdatei.
* Fügen Sie alle [!DNL Insight Servers] zur Gruppe der Cluster-Server in der [!DNL Access Control.cfg] -Datei.

* Aktualisieren Sie die [!DNL Synchronize.cfg] -Datei im Verzeichnis &quot;Components for Processing Servers&quot;auf den Übergeordneten [!DNL Insight Server].

* Ändern Sie bei Bedarf die [!DNL Disk Files.cfg] -Datei im Verzeichnis &quot;Components for Processing Servers&quot;, um den Speicherort der [!DNL temp.db] -Datei in der Verarbeitung [!DNL Insight Servers].

Um diese Schritte auszuführen, müssen Sie die allgemeinen Namen kennen (wie in den digitalen Zertifikaten für die einzelnen [!DNL Insight Server]) und die IP-Adressen der einzelnen [!DNL Insight Server] im Cluster. Wenn Sie noch nicht über diese Informationen verfügen, rufen Sie sie ab, bevor Sie fortfahren.

>[!NOTE]
>
>Die in diesem Abschnitt beschriebenen Verfahren erfordern [!DNL Insight]. Wenn Sie nicht installiert haben [!DNL Insight]folgen Sie den Anweisungen in **[!DNL Insight]Benutzerhandbuch** vor dem Fortfahren.

## Hinzufügen der verarbeitenden Insight Server zur Adressdatei {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Gehen Sie wie folgt vor, um die Verarbeitung hinzuzufügen [!DNL Insight Servers’] allgemeine Namen und IP-Adressen für die Adressdatei auf Übergeordneten [!DNL Insight Server]. (Obwohl die Adressdatei verwaltet und Übergeordnet verwaltet wird [!DNL Insight Server], wird sie von allen [!DNL Insight Servers] im Cluster).

>[!NOTE]
>
>Im Folgenden wird davon ausgegangen, dass die Adressdatei bereits für die Übergeordneten [!DNL Insight Server]. Wenn Sie die Übergeordneten [!DNL Insight Server’s] IP-Adresse(n) in die Adressdatei eingeben, das in [Definieren des Netzwerkstandorts des Servers](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) bevor Sie beginnen.

**Hinzufügen der Verarbeitung [!DNL Insight Servers] in die Adressdatei**

1. Starten [!DNL Insight] und laden Sie das Konfigurationsprofil (sofern es noch nicht geöffnet ist), indem Sie mit der rechten Maustaste auf die Titelleiste klicken und auf **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Übergeordneten **[!UICONTROL Insight Server]** und klicken Sie auf **[!UICONTROL Server Files]**.

1. Im [!DNL Server Files Manager], öffnen Sie das Verzeichnis Adressen und führen Sie die folgenden Schritte aus, um [!DNL Insight Server’s] Adressdatei:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* Spalte und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Inhalt der [!DNL Locations] Struktur und erweitern Sie dann NetworkLocation 0, Adressen und AddressDefinition.
1. Gehen Sie wie folgt vor, um eine AddressDefinition zu NetworkLocation 0 für jede Verarbeitung hinzuzufügen [!DNL Insight Server] im Cluster:

   1. Rechtsklick **[!UICONTROL AddressDefinition]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Geben Sie im Parameter Name die Verarbeitung an [!DNL Insight Server’s] allgemeiner Name.
   1. Geben Sie im Parameter Adresse die Verarbeitung an [!DNL Insight Server’s] IP-Adresse.

      Sie können ein Sternchen als Platzhalter im Feld Adresse verwenden, z. B. 10.10.116.&#42;, um das Clustering zu vereinfachen. Siehe [Grundlagen zu Zugriffsebenen](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      Im folgenden Beispiel wird ein Cluster mit zwei [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Wenn die Server mit mehreren Netzwerken verbunden sind, wiederholen Sie Schritt 6, um die Verarbeitung hinzuzufügen. [!DNL Insight Servers] an die Netzwerkstandorte für diese Netzwerke.

   Das folgende Beispiel zeigt einen Cluster von vier [!DNL Insight Servers] an zwei Netze (&quot;Corporate Intranet&quot; und &quot;Internet&quot;) angebunden.

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL Temp] und wählen Sie **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Aktualisieren der Datei &quot;Zugriffskontrolle&quot;für ein Cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Verwendung [!DNL Insight Servers] in einem Cluster [!DNL Insight Server] im Cluster (einschließlich des Übergeordneten [!DNL Insight Server]) muss zur Zugriffskontrollgruppe der Cluster-Server gehören. Die Gruppe Cluster-Server identifiziert die Server (nach IP-Adresse), die für die Teilnahme am Cluster berechtigt sind. Obwohl diese Datei verwaltet und Übergeordnet verwaltet wird [!DNL Insight Server], wird sie von allen [!DNL Insight Servers] im Cluster.

**So bearbeiten Sie die Zugriffssteuerungsdatei**

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Übergeordneten [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Im [!DNL Server Files Manager], öffnen Sie den Ordner Zugriffskontrolle .
1. Gehen Sie wie folgt vor, um die [!DNL Access Control.cfg] Datei:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* Spalte und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie die Struktur Zugriffssteuerungsgruppen und erweitern Sie dann AccessGroup (Cluster-Server).
1. Für jeden [!DNL Insight Server] im Cluster (einschließlich des Übergeordneten [!DNL Insight Server]), führen Sie die folgenden Schritte aus:

   1. Rechtsklick **[!UICONTROL Members]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Geben Sie die [!DNL Insight Server’s] IP-Adresse (ihre numerische IP-Adresse, nicht ihr Name). Wenn die Variable [!DNL Insight Servers] mit mehreren Netzwerken verbunden sind, sollte diese AccessGroup nur die internen Adressen enthalten, die die [!DNL Insight Servers] für die Kommunikation zwischen Servern im Cluster verwenden.

      Im Folgenden sehen Sie die AccessGroup (Cluster-Server) für einen Cluster von vier [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. Im [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Konfigurieren der Synchronisierungsdatei {#section-d23e751771c84da6bab6a34a8db867bc}

Sie können die zentrale Kopie der [!DNL Synchronize.cfg] -Datei. Die zentrale Kopie dieser Datei wird auf der Übergeordneten [!DNL Insight Server]. Die Verarbeitung [!DNL Insight Servers] im Cluster Kommunikation mit dem Übergeordneten initiieren [!DNL Insight Server] , um eine aktualisierte Kopie dieser Datei abzurufen.

Die [!DNL Synchronize.cfg] -Datei gibt den Speicherort des Übergeordneten [!DNL Insight Server]. Er identifiziert auch den Satz von Verwaltungsdateien, die bei jeder Verarbeitung verwendet werden [!DNL Insight Servers] im Cluster vom Übergeordneten [!DNL Insight Server]. Die Verarbeitung [!DNL Insight Servers] diese Dateien automatisch von der Übergeordneten [!DNL Insight Server] wenn sie beginnen. Außerdem werden aktualisierte Kopien dieser Dateien dynamisch aus dem Übergeordneten abgerufen [!DNL Insight Server] wenn sich die Dateien ändern.

>[!NOTE]
>
>Obwohl die [!DNL Synchronize.cfg] -Datei auf der Übergeordneten [!DNL Insight Server], der Übergeordneten [!DNL Insight Server] selbst verwendet diese Datei nicht. Sie aktualisieren diese Datei auf Übergeordneten [!DNL Insight Server] damit sie beim Verarbeiten ordnungsgemäß konfiguriert werden [!DNL Insight Servers] Rufen Sie die -Datei ab.

**Aktualisieren der Datei &quot;Synchronize.cfg&quot;auf dem Übergeordneten[!DNL Insight Server]**

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Übergeordneten [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], öffnen Sie die **[!UICONTROL Components]** für den Ordner &quot;Verarbeitungsserver&quot;.

1. Führen Sie folgende Schritte aus, um [!DNL Synchronize.cfg]:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* Spalte und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf die [!DNL Temp] Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie die Komponentenstruktur.
1. Geben Sie im Parameter Primäre Serveradresse des Clusters die IP-Adresse des Übergeordneten (primären) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   So erstellen Sie ein Protokoll, das jedes Mal, wenn eine Synchronisierung zwischen den Übergeordneten erfolgt, aufzeichnet [!DNL Insight Server] und der Verarbeitung [!DNL Insight Servers]müssen Sie sicherstellen, dass der Parameter Synchronisierungsprotokoll aktivieren auf &quot;true&quot;gesetzt ist.

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Konfigurieren des Datensatzstandorts (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Führen Sie die folgenden Schritte aus, wenn Sie die Verarbeitung durchführen möchten [!DNL Insight Servers] die [!DNL temp.db] (Datensatz) in einem Verzeichnis oder Laufwerk, das sich vom Standardspeicherort unterscheidet, oder wenn Sie [!DNL temp.db] über mehrere Laufwerke hinweg.

>[!NOTE]
>
>Da die Verarbeitung [!DNL Insight Servers] alle gleich [!DNL Disk Files.cfg], müssen sie alle die Dateispeicherorte unterstützen, die Sie in dieser Datei angeben. Wenn Sie beispielsweise [!DNL temp.db] an die EU: Laufwerk, jede Verarbeitung [!DNL Insight Server] im Cluster muss eine E aufweisen: Laufwerk.

**So konfigurieren Sie den Speicherort von &quot;temp.db&quot;**

1. In [!DNL Insight]auf [!DNL Admin] > [!DNL Dataset and Profile] klicken Sie auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Übergeordneten [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Im [!DNL Server Files Manager], öffnen Sie die **[!UICONTROL Components for Processing Servers]** Verzeichnis.

1. Führen Sie folgende Schritte aus, um [!DNL Disk Files.cfg]:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen im *Servername* Spalte und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen im [!DNL Temp]Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie die Struktur DiskSpaceManagerComponent und erweitern Sie dann die Liste Disk Files .
1. Eintrag 0 bearbeiten , um den Speicherort der [!DNL temp.db] -Datei.
1. Wenn Sie [!DNL temp.db] Verwenden Sie für mehrere Laufwerke die folgenden Schritte, um einen zusätzlichen Eintrag für jedes zusätzliche Laufwerk zu erstellen.

   1. Rechtsklick **[!UICONTROL Disk Files]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Geben Sie im neuen Eintrag den Speicherort an, an dem Sie [!DNL temp.db] geschrieben.
   Folgendes zeigt [!DNL temp.db] auf vier Laufwerke geschrieben.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie Folgendes ausführen:

   1. Rechtsklick **[!UICONTROL (modified)]** Klicken Sie oben im Fenster auf **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
