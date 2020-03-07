---
description: Neue Funktionen, die in Data Workbench 6.0.4 eingeführt wurden, einschließlich Fehlerbehebungen und bekannten Problemen.
solution: Analytics
title: Data Workbench 6.0 - Versionshinweise
topic: Data workbench
uuid: b348425e-3304-4db7-a280-479a34452bdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Data Workbench 6.0 - Versionshinweise

Neue Funktionen, die in Data Workbench 6.0.4 eingeführt wurden, einschließlich Fehlerbehebungen und bekannten Problemen.

## Neue Funktionen {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench (Insight 6.0) umfasst diese neuen Funktionen und Visualisierungen für zusätzliche Berichtsfunktionen und Prognoseanalysetools.

| Data Workbench-Funktionen | Beschreibung |
|---|---|
| [Trichtervisualisierung](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | Mit der Trichtervisualisierung können Sie den sequenziellen Prozessfluss Ihrer Kunden definieren und bei jedem Schritt des Prozesses einen Einblick in den Besucherabgang geben. |
| [Besucheraufteilung](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | Durch Clustering können Sie Kundenmerkmale nutzen, um Besucher dynamisch zu kategorisieren und Cluster-Sets zu erstellen, die auf ausgewählten Dateneingaben für die Kundenanalyse und das Targeting basieren. |
| [Korrelationsanalyse](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | Mit der Korrelationsanalyse können Sie schnell relevante Datenbeziehungen identifizieren, um Ihre Analyse zu erweitern und zu verbessern. |
| [Aktualisierte DeviceAtlas-Distribution](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | Die JSON-Datei von DeviceAtlas wird jetzt in einer Bundle-Datei (mit dem Namen .tar.gz) zusammen mit DeviceAtlas.dll und DeviceAtlas64.dll verteilt. |

## Anforderungen an Client-Upgrades {#section-f316103b48374b6eac77e8feb5c47ecf}

Führen Sie die folgenden Aktualisierungsaufgaben für Data Workbench (Insight 6.0)-Clientfunktionen aus:

**Aktualisieren der ZAR-Datei für den Client**

Data Workbench unterstützt jetzt einen Eingabemethoden-Editor (IME) als sekundären Texteingabeprozess, mit dem Sie internationale Zeichen über die Tastatur mit einem schwebenden Textfeld eingeben können. Data Workbench unterstützt standardmäßig Englisch, ermöglicht Ihnen aber auch, andere Dateien zu laden, um internationale Sprachen zu unterstützen, wie z.B. eine virtuelle chinesische Tastatur (Pinyin IME).

Eine neue Wörterbuchdatei (eine Zbin-Datei) wird von der Clientanwendung benötigt, bevor sie auf Version 6.0 aktualisiert wird. Sie können die benötigte .zbin-Datei aus dem Software- und Docs-Profil (Software) abrufen.

Voraussetzungen:

* Vor der Aktualisierung auf den Insight 6.0-Client und Report Server 6.0 muss der Insight-Administrator zunächst auf Insight Server 6.0 aktualisieren.
* Der Insight-Administrator muss eine auf Sprache basierende Zbin-Datei auswählen (en-us.zbin, zh-cn.zbin), die Sprachdatei kopieren, sie dann in &quot;insight.zbin&quot;umbenennen und die umbenannte Datei im Stammverzeichnis des Berichtsservers ablegen, wo sich die ausführbare Datei befindet. Starten Sie dann den Insight-Berichtsserver neu.

Weitere Informationen zur serverseitigen Aktualisierung finden Sie unter [Serveraktualisierungsanforderungen](../../../home/c-release-notes-insight/release-notes.md) .

**So aktualisieren Sie die zbin-Datei für den Client (von Version 5.x auf Version 6.0)**

1. Um sicherzustellen, dass der Client während dieser Aktualisierung nicht vom Insight-Server aktualisiert wird, setzen Sie das Insight.cfg-Argument auf &quot;false&quot;.

   ```
   Update Software = bool: false
   ```

1. Starten Sie den Insight-Client neu.
1. Navigieren Sie zum Profil Software und Docs (SoftDocs-Profil) und laden Sie die erforderliche **[!UICONTROL Insight.zbin]** Datei herunter: [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Kopieren Sie die Datei Insight.zbin in denselben Ordner wie die Datei Insight.exe.
1. Um sicherzustellen, dass der Insight-Client jetzt vom Insight-Server aktualisiert wird, ändern Sie das Insight.cfg-Dateiargument in true:

   ```
   Update Software = bool: true
   ```

1. Starten Sie den Client neu.

   Ihr Client wird mit dem Server synchronisiert, und es wird eine Meldung angezeigt, dass Ihr Client heruntergeladen wird. Nach Abschluss des Downloads erhalten Sie eine Nachricht, in der Sie gefragt werden, ob Sie Ihren Insight-Client neu starten möchten.
1. Klicken Sie auf **OK** , um den Client neu zu starten.

   Der Client startet und aktualisiert auf Version 6.0.

1. Starten Sie den Client erneut neu, damit die Insight.zbin-Clientsynchronisierung wirksam wird.

   Wenn Sie die folgende Meldung erhalten, bedeutet dies, dass der Zbin nicht neben der Datei Insight.exe im richtigen Ordner abgelegt wurde.

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   Um das Problem zu beheben, löschen Sie Insight.exe und benennen Sie die neueste Version von Insight.exe.old in Insight.exe um. Starten Sie dann erneut mit Schritt 1.

## Anforderungen an die Serveraktualisierung {#section-d6edba8b36234957ba8d06b555667a5a}

Führen Sie die folgenden Aktualisierungsaufgaben für die Insight 6.0-Serverfunktionen aus:

**Aktualisieren Sie alle Insight Server 6.0-Pakete**. Insight 6.0 enthält Serverpakete, die aktualisiert werden müssen, einschließlich des neuen Predictive Analytics-Profils.

>[!IMPORTANT]
>
>Es wird empfohlen, dass Benutzer ihre Servercluster bei der Aktualisierung mit neuen Installationen von Insight Server 6.0 aktualisieren.

Es wird außerdem empfohlen, dass Client ihre Server-Cluster mit einer Neuinstallation von Insight Server 6.0 aktualisiert.

## Servercluster aktualisieren

**Bereiten Sie die Sprachdatei (.zbin-Datei) vor.** Der Insight-Administrator wählt die `<language>.zbin` Datei für die gewünschte Sprache aus (z. B.: en-us.zbin , zh-cn.zbin) im `/localization/<language>.zbin` Ordner. Der Administrator kopiert dann die Sprachdatei und benennt sie in &quot;insight.zbin&quot;um.

Nach dem Vorbereiten der Sprachdatei (.zbin) müssen sowohl der Insight-Client als auch der Report Server aktualisiert werden. Der Insight-Client wird während des [Client-Aktualisierungsprozesses](../../../home/c-release-notes-insight/release-notes.md)aktualisiert, aber in den meisten Fällen wird der Insight-Administrator den Report Server aktualisieren.

**Aktualisieren Sie Report Server mit einer Sprachdatei (.zbin-Datei)**.

Für alle Sprachen ist für Report Server 6.0 die Datei &quot;insight.zbin&quot;erforderlich, die in den Berichtsserver-Stammordner kopiert wird.

Aktualisieren Sie die Sprachdateien für den Report Server:

1. Fügen Sie die umbenannte Datei &quot;insight.zbin&quot;dem Stammordner von ReportServer hinzu.
1. Die Berichtsserver-Konfigurationsdatei (reportserver.cfg) erfordert Schrifteinstellungen für Doppelbyte-Sprachen. Beispielsweise erfordert Chinesisch das Hinzufügen von Schriftarten mit SimSun:

   ```
   Report Server.cfg - Add Fonts 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Ein Parameter für Report Server 6.0 muss in der Befehlszeile für die Lokalisierung übergeben werden, z. B.:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Wenn kein Gebietsschema angegeben ist, verwendet der Berichtsserver standardmäßig die in der Datei &quot;insight.zbin&quot;ausgewählte Sprache.

   Führen Sie die folgenden Schritte aus, um den ReportServer als Dienst mit den Locale-Parametern zu starten:

   1. Starten Sie eine Eingabeaufforderung als Administrator.
   1. Navigieren Sie zum Installationsordner von ReportServer.
   1. Geben Sie den folgenden Befehl ein, um den Dienst zu starten:

      * Englisch: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Für Chinesisch: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. So überprüfen Sie, ob der ReportServer mit den richtigen Parametern ausgeführt wird:

   1. Öffnen Sie Windows Service Manager.
   1. Rechtsklick [!DNL Adobe Insight Report Server - Properties].
   Der Pfad zur ausführbaren Datei enthält die Parameter:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Ändern Sie die Profilkonfigurationsdatei für Predictive Analytics**. Insight-Administrator muss die benutzerdefinierte Datei &quot;profile.cfg&quot;ändern, um das Predictive Analytics-Profil einzuschließen, das in Insight verfügbar sein soll.

Beispiel für den Eintrag profile.cfg:

```
Example ("profile.cfg"): 
Profile = profileInfo:  
  Active = bool: true 
  Directories = vector: 5 items 
    0 = string: Base\\  
    1 = string: Predictive Analytics\\ 
    2 = string: Geography\\ 
    3 = string: Adobe SC\\ 
    4 = string: Custom Profile\\ 
```

**Aktualisieren Sie die Datei** PAServer.cfg. Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight-Server senden möchten, müssen Sie die Datei &quot;PAServer.cfg&quot;für die Verarbeitung serverseitiger Clustering-Übermittlungen konfigurieren.

Das benutzerdefinierte Profil sollte die Datei PAServer.cfg aus dem Predictive Analytics-Profil (Server\Profiles\Predictive Analytics\Dataset) übernehmen. Konfigurieren und speichern Sie die Datei &quot;PAServer.cfg&quot;pro Implementierungssite.

>[!NOTE]
>
>Sobald PAServer.cfg konfiguriert und im benutzerdefinierten Profil gespeichert wurde, ist ein Neustart des Insight-Servers für die gesamte Site erforderlich.

**Report Server aktualisieren** Sie müssen die Schriftarten und die Startparameter für Report Server aktualisieren.

Voraussetzungen:

* Vor der Aktualisierung von Report Server 6.0 muss der Insight-Administrator zunächst auf Insight Server 6.0 aktualisieren.
* Für alle Sprachen erfordert Report Server 6.0 die Hinzufügung von Insight.zbin zum Stammordner des Berichtsservers. Vergewissern Sie sich, dass der Text kopiert und in &quot;insight.zbin&quot;umbenannt `base/localization/<language>.zbin` wird. Kopieren Sie es in den Stammordner des Berichtsserverordners.

Aktualisieren Sie die Parameter &quot;Schriftarten&quot;und &quot;Start&quot;:

1. Report Server erfordert die Schriftarteinstellung für Doppelbyte, um in verschiedenen Sprachen ausgegeben werden zu können,

   Beispiel:

   Report Server.cfg - Schriftarten hinzufügen

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Parameter für Report Server 6.0 müssen zu Lokalisierungszwecken in die Befehlszeile übergeben werden.

   So starten Sie den Berichtsserver als Dienst mit den Gebietsschema-Parametern:

   1. Beenden Sie den Berichtsserver-Dienst.
   1. Starten Sie eine Eingabeaufforderung als Administrator.
   1. Navigieren Sie zum Installationsordner für Report Server.
   1. Geben Sie den folgenden Befehl ein, um den Dienst zu starten:

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

So überprüfen Sie, ob der Berichtsserver mit den richtigen Parametern ausgeführt wird:

1. Windows Service Manager öffnen
1. Rechtsklick [!DNL Adobe Insight Report Server - Properties].
1. Der Pfad zur ausführbaren Datei enthält die Parameter:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Aktualisieren Sie den SiteCatalyst-Datenfeed für Insight 6.0**. Das Dateiformat des SiteCatalyst-Datenfeeds für Insight 6.0 wurde geändert.

Format des aktuellen Dateinamens:

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

Neues Dateiformat:

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>Diese Änderung betrifft keine Benutzer, die derzeit mit der *wbench/ecom* -Version des SiteCatalyst-Datenfeeds bereitgestellt werden.

Die Änderung des Dateiformats ermöglicht die vollständige Verwendung der Insight Start- und Endzeitdeklarationen während der Protokollverarbeitung. Dadurch kann der Prozess bewerten, ob der Inhalt der Datei gelesen werden soll, anstatt alle Quelldateien mit einer Zeilensuche zu filtern.

In den meisten Fällen wurde nach Erhalt der Datei ein Umbenennungsprozess implementiert, um diese Funktion vollständig zu nutzen. Diese Änderung stellt standardmäßig die erforderliche Benennungskonvention ohne zusätzlichen Aufwand bereit.

So verwenden Sie den neuen SiteCatalyst-Datenfeed:

1. Legen Sie fest, wie der empfangende Prozess mit dem neuen Dateiformat umgehen soll.

   Die während der Implementierung bereitgestellten Standardskripte zum Umbenennen/Verschieben verschieben die Dateien mit der Erweiterung &quot;.gz&quot;und führen nur dann einen Umbenennungsvorgang durch, wenn der Dateiname dem Format des Dateinamens mit der vorherigen RSID übereinstimmt.

   Das neue Dateiformat:

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. Bewerten Sie die definierten Protokollquellenpfade, um sicherzustellen, dass alle Dateien gelesen werden.

   Wenn Sie bereits ein Umbenennungsskript implementiert haben, definieren Sie Ihre Protokollquellen bereits, um dieses neue Dateiformat zu lesen.

## Fehlerkorrekturen {#section-203f917dd6224114a1f801309c4c2cee}

* Jetzt wurde die Tastenkombination zum Verlassen eines Arbeitsbereichs ohne Speichern der Änderungen auf **[!UICONTROL `<Ctrl>`+`<Backspace>`]**aktualisiert. Zuvor haben Sie Änderungen vermieden und eine Arbeitsfläche durch Drücken von`<Ctrl>`+ geschlossen`<Delete>`.

## Data Workbench 6.0.4 Release Notes{#data-workbench-release-notes}

Neue Funktionen, die in Data Workbench 6.0.4 eingeführt wurden, einschließlich Fehlerbehebungen und bekannten Problemen.

Informationen zu früheren Funktionen und Fehlerbehebungen, die für jede frühere Version verwendet wurden, finden Sie in den Archiven der [Versionshinweise](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html).

## Neue Funktionen {#section-2-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.0.4 umfasst diese neuen Funktionen und Visualisierungen für zusätzliche Berichterstattungsfunktionen und Prognoseanalysetools.

**Visualisierung** der Tendenzauswertung. Data Workbench berechnet die Ergebnisse für jeden Besucher als geschätzte Wahrscheinlichkeit, dass ein bestimmtes Ereignis eintritt. Die Visualisierung der Besucherauswertung ermöglicht es Ihnen, eine Bewertungsdimension zu erstellen, die basierend auf den Eingabevariablen die Wahrscheinlichkeit eines bestimmten Ereignisses für jeden Besucher mit Interesse festlegt.

![](assets/visitor_scoring_visual.png)

Weitere Informationen zu dieser Funktion finden Sie unter [Tendenzauswertung](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40) .

## Upgrade-Anforderungen {#section-08bd6fe3da8740fcb19688e8cac6f223}

**Protokollquellen-ID muss definiert** werden. Wenn ab Version 6.04 die Protokollquelle-ID nicht definiert ist, erhalten Sie den folgenden Fehler:

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

Die Aufzeichnung von Zeilen pro Protokollquelle wurde in Data Workbench 6.0 hinzugefügt und kann in dem benutzerdefinierten Profil Log Processing.cfg definiert werden, indem eine eindeutige Protokollquellen-ID hinzugefügt wird. Wenn Sie über eine leere Protokollquellen-ID verfügen, können Probleme bei der Protokollverarbeitung wie das unvollständige Lesen der Protokollquellendaten und andere Diskrepanzen auftreten.

```
Log Processing.cfg 
Log Sources = vector: 2 items 
  0 = VisualSensor: 
    Compressed = bool: false 
    Log Paths = vector: 1 items 
      0 = Path: \some path\ 
    Log Server = serverInfo:  
      Address = string:  
      Name = string:  
      Port = int: 80 
      Proxy Address = string:  
      Proxy Password = string:  
      Proxy Port = int: 8080 
      Proxy User Name = string:  
      SSL Client Certificate = string: Certificates\\server_cert.pem 
      SSL Server Common Name = string:  
      Use SSL = bool: false 
     
Log Source ID = string: <Name your ID Here>
    Name = string:  
    Recursive = bool: false
```

**Möglichkeit zur Delegierung von FSU-Ressourcen**

Unter [!DNL Profiles/`<profilename>`/dataset/Cluster.cfg]können Sie jetzt separate File Server Units (FSU) für die Server Normalize und Source List angeben. Diese Dienste sind nicht mehr an das Master-FSU gebunden.

>[!NOTE]
>
>Wenn der Listenserver nicht angegeben ist, übernimmt der Listenserver die Konfigurationseinstellungen des Servers &quot;Normalisieren&quot;.

Example in the [!DNL cluster.cfg] file.

```
Cluster = ClusterConfig: 
  Normalize Server = serverInfo: 
    Address = string: normalizeserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false 
  List Server = serverInfo: 
    Address = string: sourcelistserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false
```

## Behobene Fehler {#section-3b4b85a35f534288adf8a5246ef028cc}

* In Data Workbench 6.0 unterstützten die Korrelationsmatrix und der Cluster-Builder keine &quot;Im Hintergrund berechnen&quot;. Dieses Problem wurde in Version 6.0.4 behoben.
* Wenn Sie zuvor eine Auswahl für den Trichter hatten und einen Schritt entfernt haben, kann es zu einer Zugriffsverletzung kommen. Dies wurde behoben.
* Es wurde eine potenzielle Sperrbedingung im Segmentexport behoben, die unter hohen Lasten Probleme verursachen kann.
