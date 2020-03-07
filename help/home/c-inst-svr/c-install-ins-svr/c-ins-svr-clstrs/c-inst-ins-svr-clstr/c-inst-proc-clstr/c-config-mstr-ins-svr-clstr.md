---
description: Informationen zum Konfigurieren des Clusters auf dem Master Insight-Server, zum Aktualisieren der Zugriffssteuerungsdatei für einen Cluster und mehr.
solution: Insight
title: Konfigurieren des Master Insight-Servers für das Clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurieren des Master Insight-Servers für das Clustering{#configuring-the-master-insight-server-for-clustering}

Informationen zum Konfigurieren des Clusters auf dem Master Insight-Server, zum Aktualisieren der Zugriffssteuerungsdatei für einen Cluster und mehr.

Um den Cluster zu konfigurieren, führen Sie die folgenden Schritte auf dem Master aus [!DNL Insight Server]:

* Fügen Sie der Adressdatei die [!DNL Insight Servers’] allgemeinen Verarbeitungsnamen und -adressen hinzu.
* Fügen Sie alle Elemente [!DNL Insight Servers] zur Gruppe Cluster-Server in der [!DNL Access Control.cfg] Datei hinzu.

* Aktualisieren Sie die [!DNL Synchronize.cfg] Datei im Ordner &quot;Komponenten für Verarbeitungsserver&quot;so, dass sie auf den Master verweist [!DNL Insight Server].

* Ändern Sie bei Bedarf die [!DNL Disk Files.cfg] Datei im Ordner &quot;Komponenten für Verarbeitungsserver&quot;, um den Speicherort der [!DNL temp.db] Datei in der Verarbeitung anzugeben [!DNL Insight Servers].

Um diese Schritte auszuführen, müssen Sie die allgemeinen Namen (wie in den digitalen Zertifikaten für die betreffende Person angegeben [!DNL Insight Server]) und die IP-Adressen jeder Gruppe [!DNL Insight Server] im Cluster kennen. Wenn Sie noch nicht über diese Informationen verfügen, holen Sie diese vor dem Fortfahren ab.

>[!NOTE]
>
>Die in diesem Abschnitt beschriebenen Verfahren erfordern [!DNL Insight]. Wenn Sie noch nicht installiert haben, befolgen Sie [!DNL Insight]die Anweisungen im **[!DNL Insight]Benutzerhandbuch **, bevor Sie fortfahren.

## Hinzufügen der Processing Insight-Server zur Adressdatei {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Verwenden Sie das folgende Verfahren, um der Adressdatei auf dem Master die [!DNL Insight Servers’] allgemeinen Verarbeitungsnamen und IP-Adressen hinzuzufügen [!DNL Insight Server]. (Obwohl die Adressdatei auf dem Master verwaltet und verwaltet wird, [!DNL Insight Server]wird sie von allen [!DNL Insight Servers] im Cluster verwendet.)

>[!NOTE]
>
>Im Folgenden wird davon ausgegangen, dass die Adressdatei bereits für den Master konfiguriert wurde [!DNL Insight Server]. Wenn Sie die Master- [!DNL Insight Server’s] IP-Adresse(n) noch nicht zur Adressdatei hinzugefügt haben, führen Sie das unter [Definieren des Netzwerkspeicherorts](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) des Servers beschriebene Verfahren aus, bevor Sie beginnen.

**So fügen Sie die Verarbeitung[!DNL Insight Servers]der Adressdatei hinzu**

1. Starten [!DNL Insight] und laden Sie das Konfigurationsprofil (sofern es noch nicht geöffnet ist), indem Sie mit der rechten Maustaste auf die Titelleiste klicken und auf **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Masterbilds **[!UICONTROL Insight Server]** und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie im Ordner &quot; [!DNL Server Files Manager]Adressen&quot;den Ordner &quot;Addresses&quot;und führen Sie zum Öffnen der [!DNL Insight Server’s] Adressdatei die folgenden Schritte aus:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie den Inhalt der [!DNL Locations] Struktur und erweitern Sie dann NetworkLocation 0, Addresses und AddressDefinition.
1. Führen Sie die folgenden Schritte aus, um eine AddressDefinition zu NetworkLocation 0 für jede Verarbeitung [!DNL Insight Server] im Cluster hinzuzufügen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL AddressDefinition]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Geben Sie im Parameter Name den [!DNL Insight Server’s] allgemeinen Verarbeitungsnamen an.
   1. Geben Sie im Parameter Adresse die verarbeitende [!DNL Insight Server’s] IP-Adresse an.

      Sie können ein Sternchen als Platzhalter im Feld &quot;Adresse&quot;verwenden, z. B. 10.10.116.* zur Vereinfachung des Clustering. Siehe [Die Zugriffsebenen](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      Im folgenden Beispiel wird ein Cluster definiert, der zwei [!DNL Insight Servers]enthält:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Wenn die Server mit mehreren Netzwerken verbunden sind, wiederholen Sie Schritt 6, um die Verarbeitung für diese Netzwerke [!DNL Insight Servers] zu den NetworkLocations hinzuzufügen.

   Das folgende Beispiel zeigt einen Cluster mit vier Elementen, die an zwei Netzwerke [!DNL Insight Servers] angeschlossen sind (&quot;Corporate Intranet&quot;und &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Server Files Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei und wählen Sie [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

## Aktualisieren der Zugriffssteuerungsdatei für einen Cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Zur Verwendung [!DNL Insight Servers] in einem Cluster muss jeder [!DNL Insight Server] im Cluster (einschließlich Master [!DNL Insight Server]) zur Zugriffskontrollgruppe Cluster-Server gehören. Die Gruppe Cluster-Server identifiziert die Server (nach IP-Adresse), die am Cluster teilnehmen dürfen. Diese Datei wird zwar auf dem Master verwaltet und verwaltet, [!DNL Insight Server]wird aber von allen im Cluster [!DNL Insight Servers] verwendeten verwendet.

**So bearbeiten Sie die Zugriffssteuerungsdatei**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Masterbilds [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie im [!DNL Server Files Manager]Ordner Zugriffssteuerung.
1. Führen Sie zum Öffnen der [!DNL Access Control.cfg] Datei die folgenden Schritte aus:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie die Struktur Zugriffssteuerungsgruppen und erweitern Sie dann AccessGroup (Cluster-Server).
1. Führen Sie für jeden [!DNL Insight Server] im Cluster (einschließlich Master [!DNL Insight Server]) folgende Schritte aus:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Members]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Geben Sie die [!DNL Insight Server’s] IP-Adresse (ihre numerische IP-Adresse, nicht ihren Namen) an. Wenn die [!DNL Insight Servers] mit mehreren Netzwerken verbunden sind, sollte diese AccessGroup nur die internen Adressen enthalten, die für die Kommunikation zwischen Servern im Cluster verwendet werden [!DNL Insight Servers] .

      Im Folgenden sehen Sie die AccessGroup (Cluster Servers) für einen Cluster von vier [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie in der [!DNL Server Files Manager]Spalte mit der rechten Maustaste auf das Häkchen für die Datei in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Synchronisierungsdatei konfigurieren {#section-d23e751771c84da6bab6a34a8db867bc}

Mit dem folgenden Verfahren können Sie die zentrale Kopie der [!DNL Synchronize.cfg] Datei konfigurieren. Die zentrale Kopie dieser Datei wird auf dem Master gespeichert [!DNL Insight Server]. Die Verarbeitung [!DNL Insight Servers] im Cluster initiiert eine Kommunikation mit dem Master, [!DNL Insight Server] um eine aktualisierte Kopie dieser Datei abzurufen.

Die [!DNL Synchronize.cfg] Datei gibt den Speicherort des Masterbilds an [!DNL Insight Server]. Er identifiziert außerdem den Satz von Verwaltungsdateien, die von jeder Verarbeitung [!DNL Insight Servers] im Cluster vom Master abgerufen werden [!DNL Insight Server]. Die Verarbeitung lädt diese Dateien [!DNL Insight Servers] automatisch vom Master herunter, [!DNL Insight Server] sobald sie beginnen. Außerdem werden aktualisierte Kopien dieser Dateien dynamisch vom Master abgerufen, [!DNL Insight Server] wenn sich die Dateien ändern.

>[!NOTE]
>
>Obwohl Sie die [!DNL Synchronize.cfg] Datei auf dem Master konfigurieren, [!DNL Insight Server]verwendet der Master [!DNL Insight Server] diese Datei nicht. Sie aktualisieren diese Datei auf dem Master, [!DNL Insight Server] sodass sie beim Abrufen der Datei durch die Verarbeitung ordnungsgemäß konfiguriert [!DNL Insight Servers] ist.

**So aktualisieren Sie die Datei &quot;Synchronize.cfg&quot;auf dem Master[!DNL Insight Server]**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Masterbilds [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie [!DNL Server Files Manager]den Ordner &quot; **[!UICONTROL Components]** Verarbeitungsserver&quot;.

1. Führen Sie zum Öffnen die folgenden Schritte aus [!DNL Synchronize.cfg]:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das [!DNL Temp] Häkchen und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie die Komponentenstruktur.
1. Geben Sie im Parameter Primär-Serveradresse des Clusters die IP-Adresse des Masterservers an (primär) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_(CentralCopy).png)

   Um ein Protokoll zu erstellen, das jedes Mal, wenn eine Synchronisierung zwischen Master [!DNL Insight Server] und Verarbeitung stattfindet, aufzeichnet, stellen Sie sicher, dass der Parameter &quot;Synchronisierungsprotokoll aktivieren&quot;auf &quot;true&quot;eingestellt ist [!DNL Insight Servers].

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie [!DNL Server Files Manager]mit der rechten Maustaste auf das Häkchen für die Datei in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Speicherort des Datensatzes konfigurieren (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Führen Sie das folgende Verfahren aus, wenn die Verarbeitung [!DNL Insight Servers] in einem Verzeichnis oder einem Laufwerk, das sich vom Standardspeicherort unterscheidet, [!DNL temp.db] (dem Datensatz) gespeichert werden soll, oder wenn Sie die Verteilung über mehrere Laufwerke [!DNL temp.db] hinweg durchführen möchten.

>[!NOTE]
>
>Da die Verarbeitung [!DNL Insight Servers] [!DNL Disk Files.cfg]alle dieselbe Datei verwenden, müssen sie alle die Dateispeicherorte unterstützen, die Sie in dieser Datei angeben. Wenn Sie beispielsweise [!DNL temp.db] dem E Folgendes zuweisen: -Laufwerk, muss jede Verarbeitung [!DNL Insight Server] im Cluster ein E haben: Laufwerk.

**So konfigurieren Sie den Speicherort von &quot;temp.db&quot;**

1. Klicken Sie [!DNL Insight]auf der Registerkarte [!DNL Admin] > [!DNL Dataset and Profile] auf die **[!UICONTROL Servers Manager]** Miniaturansicht, um den Arbeitsbereich &quot;Server Manager&quot;zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das Symbol des Masterbilds [!DNL Insight Server] und klicken Sie auf **[!UICONTROL Server Files]**.

1. Öffnen Sie im [!DNL Server Files Manager]Ordner den **[!UICONTROL Components for Processing Servers]** .

1. Führen Sie zum Öffnen die folgenden Schritte aus [!DNL Disk Files.cfg]:

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der Spalte *Servername* und klicken Sie auf **[!UICONTROL Make Local]**.

   1. Klicken Sie mit der rechten Maustaste auf das Häkchen in der [!DNL Temp]Spalte und klicken Sie auf **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Erweitern Sie die Struktur DiskSpaceManagerComponent und erweitern Sie dann die Liste Disk Files.
1. Bearbeiten Sie den Eintrag 0, um den Speicherort der [!DNL temp.db] Datei zu ändern.
1. Wenn Sie [!DNL temp.db] über mehrere Laufwerke verteilen möchten, führen Sie die folgenden Schritte aus, um einen zusätzlichen Eintrag für jedes zusätzliche Laufwerk zu erstellen.

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Disk Files]** und klicken Sie auf **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Geben Sie im neuen Eintrag den Ort an, an dem Sie [!DNL temp.db] schreiben möchten.
   Die folgende Abbildung zeigt, wie sie auf vier Laufwerken [!DNL temp.db] geschrieben wurde.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Speichern Sie Ihre Änderungen auf dem Server, indem Sie folgende Schritte ausführen:

   1. Klicken Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters und klicken Sie auf **[!UICONTROL Save]**.

   1. Klicken Sie [!DNL Server Files Manager]mit der rechten Maustaste auf das Häkchen für die Datei in der [!DNL Temp] Spalte und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

