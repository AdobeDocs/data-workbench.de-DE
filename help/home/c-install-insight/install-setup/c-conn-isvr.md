---
description: Nachdem Sie Ihre Insight-Software und Ihr digitales Zertifikat installiert haben, müssen Sie Insight starten und seine Verbindung mit Insight Server konfigurieren.
title: Verbindung zu Insight Server konfigurieren
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Verbindung zu Insight Server konfigurieren{#configuring-the-connection-to-insight-server}

Nachdem Sie Ihre Insight-Software und Ihr digitales Zertifikat installiert haben, müssen Sie Insight starten und seine Verbindung mit Insight Server konfigurieren.

>[!NOTE]
>
>In einigen Fällen wurde die Verbindung mit Insight Server möglicherweise von Adobe Consulting Services oder Ihrem Systemadministrator vorkonfiguriert. In diesem Fall müssen Sie diese Aufgabe nicht ausführen.

Wenn Sie Insight zum ersten Mal starten, stellt es automatisch eine Verbindung zum Adobe License Server her, um Ihr digitales Zertifikat zu registrieren. Um den Registrierungsprozess erfolgreich abzuschließen, muss Ihr Computer mit dem Internet verbunden sein, wenn Sie die folgenden Schritte ausführen.

>[!NOTE]
>
>Wenn Sie bereits ein gesperrtes Zertifikat angefordert, heruntergeladen und installiert haben, wie unter [Herunterladen und Installieren des digitalen Zertifikats](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9)beschrieben, versucht Insight nicht, eine Verbindung zum Lizenzserver herzustellen, und Sie erhalten keinen Fehler.

**So konfigurieren Sie die Verbindung zum Insight Server**

Beim Arbeiten in einer Clusterumgebung sollte Insight so konfiguriert werden, dass auf den Master Insight-Server zugegriffen wird, um Synchronisierungsprobleme zu vermeiden. In Insight können Sie Informationen zur Verarbeitung [!DNL Insight Servers] im Cluster über den [!DNL Related Servers] Menüpunkt im [Server Manager](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-svrs-mgr.html)anzeigen.

1. Starten Sie Insight.
1. Klicken Sie auf der [!DNL Worktop]Seite auf **[!UICONTROL Admin]** und dann **[!UICONTROL First Steps]**.

1. Klicken Sie auf die **[!UICONTROL Configure Connection to Servers]** Miniaturansicht.

   Die [!DNL Servers Manager]Datei, die [!DNL Insight.cfg] Datei und die Anweisungen zum Konfigurieren der [!DNL Insight.cfg]Datei werden angezeigt.

1. Klicken Sie im [!DNL Insight.cfg] Fenster mit der rechten Maustaste **[!UICONTROL Servers]** und klicken Sie auf **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddChild.png)

1. Vervollständigen oder ändern Sie die Serverparameter, um Insight Zugriff auf Ihren Master Insight-Server zu gewähren. Detaillierte Beschreibungen der Parameter in der Datei Insight.cfg finden Sie unter [Konfigurationsparameter](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-insght-config-param.html).

   ![](assets/cfg_Workstation_AddServer.png)

1. Wiederholen Sie Schritt 4 und Schritt 5 für jeden Insight-Server, für den Sie eine Verbindung konfigurieren möchten.
1. Um die Konfigurationsänderungen zu speichern, klicken Sie mit der rechten Maustaste **[!UICONTROL Insight.cfg (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save as Insight.cfg]**.

   Insight versucht, eine Verbindung mit den [!DNL Insight Server(s)] angegebenen Einstellungen herzustellen. Wird eine Verbindung hergestellt, wird in der [!DNL Servers Manager] wie auf der folgenden Seite dargestellt eine grüne Node angezeigt.

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **Grün:** Gibt an, dass die Verbindung zum Insight-Server aktiv ist.
   * **Hellrot:** Gibt ein potenzielles Problem mit dem Server an, z. B. einen Abfluss bei der Serververarbeitung, eine hohe Speicherbelegung oder einen niedrigen Festplattenspeicher.
   * **Rot:** Gibt an, dass die Verbindung zum Insight-Server nicht aktiv ist.
   Wenn Insight keine Verbindung mit den angegebenen Einstellungen herstellen kann, wird ein roter Knoten im [!DNL Servers Manager]Bildschirm angezeigt. In diesem Fall finden Sie weitere Informationen unter [Verbindungsfehlerbehebung](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b).

<!--
c_dir_crt_setup.xml
-->

Wenn Sie ein zu verwendendes Profil auswählen, werden die Profilinformationen (einschließlich der zugehörigen Daten und der für das Profil definierten Arbeitsbereiche oder Visualisierungen) auf Ihren Computer heruntergeladen. Beim Herunterladen jedes Profils erstellt Insight einen Ordner im Installationsordner unter Verwendung des Profilnamens.

Wenn Sie beispielsweise ein Profil mit dem Namen Sales auswählen, wird ein Ordner mit dem Namen Sales im Insight-Ordner angezeigt. Dieser Ordner enthält die Metriken, Dimensionen, Arbeitsbereiche und Visualisierungen, die im Verkaufsprofil definiert sind. Nach dem ersten Laden des Profils kann das Profil verwendet werden, wenn es offline funktioniert. Siehe [Offline- und Online](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-off-on.html)-Arbeit.

Wenn Sie außerdem zum ersten Mal über Insight eine Verbindung zu Insight Server herstellen, erstellt Insight Server die folgenden Ordner im Insight-Installationsordner.

* **[!DNL Trace]directory:**Innerhalb des[!DNL Trace]Ordners befindet sich die Insight-Protokolldatei ([!DNL insight.log]). Wenn die[!DNL Insight.log]Datei 100 MB groß ist, wird die Datei in[!DNL insight-1.log]umbenannt. Wenn eine Datei mit dem Namen[!DNL insight-1.log]bereits vorhanden ist,[!DNL insight-1.log]wird sie in[!DNL insight-2.log]usw. umbenannt, mit einem Maximum von[!DNL insight-9.log]. Die Datei enthält[!DNL insight.log]immer die neuesten Protokollinformationen und[!DNL insight-max.log]enthält die ältesten.

* **[!DNL User]directory:**Innerhalb des[!DNL User]Ordners befinden sich Ordner, die jedem bis dato verwendeten Profil entsprechen, und in jedem Profilordner befinden sich die Ordner[!DNL Work]und[!DNL Workspaces]. Der Ordner`User\*profile name*\Workspaces`ist der Standardspeicherort, in dem Insight Workspace-Dateien gespeichert werden.`User\*profile name*\Work`ist der Standardspeicherort, an dem Insight-Visualisierungen und andere benutzerdefinierte Arbeiten des Insight-Benutzers gespeichert werden.

In der folgenden Tabelle sind die Standardspeicherorte häufig aufgerufener Komponenten aufgeführt.

<table id="table_0254A8C25AF5400F89F87A242746D07E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Komponente </th> 
   <th colname="col2" class="entry"> Ordnerpfad </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gespeicherte Visualisierungen </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>Profilname</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gespeicherte <span class="wintitle"> Arbeitsflächen</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>Profilname</i>\Workspaces\<i>Registerkartenname</i>\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gespeicherte<span class="filepath"> PNG</span> -Dateien </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>Profilname</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datencache </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Insight.log</span> -Datei </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

Sie können nach Schlüsselname, Schlüsseltyp oder Wert suchen, um einen Eintrag schnell zu finden, sodass kein Bildlauf durch erweiterte, große Dateien für verschachtelte Informationen erforderlich ist. Sie können Dimensionsnamen, Servernamen usw. suchen. Das folgende Beispiel zeigt Übereinstimmungen für eine Suche in der Phrasenzuordnung.

![](assets/cfg_search.PNG)

Geben Sie einen Suchbegriff in dieses Feld ein, um die Daten zu suchen. Je nach Erfolg einer Übereinstimmung ändert sich die Feldfarbe. Übereinstimmungen werden hervorgehoben und Nichtübereinstimmungen abgeblendet angezeigt. Wenn keine Übereinstimmung vorliegt, wird der Hintergrund des Suchfelds rot. Wenn Sie die Eingabetaste drücken, erweitert der Konfigurationsbaum jeden Ort, an dem eine Übereinstimmung vorliegt, und reduziert den Punkt, an dem keine Übereinstimmung vorliegt.

Sie können auch reguläre Ausdrücke im [!DNL Search] Feld verwenden. Sie können beispielsweise Folgendes verwenden: [!DNL *zip.*]für alle Einträge mit dem Wort &quot;zip&quot;.

Um eine Suche zu löschen, drücken Sie **[!UICONTROL Escape]**.
