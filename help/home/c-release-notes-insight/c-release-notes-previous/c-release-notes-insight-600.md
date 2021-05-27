---
description: Neue Funktionen, die in Data Workbench 6.0.4 eingeführt wurden, einschließlich Fehlerbehebungen und bekannter Probleme.
title: Versionshinweise zu Data Workbench 6.0
uuid: b348425e-3304-4db7-a280-479a34452bdb
exl-id: be69b3be-24e7-4a8c-9dc8-1360a9b6fb3a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1679'
ht-degree: 2%

---

# Versionshinweise zu Data Workbench 6.0

Neue Funktionen, die in Data Workbench 6.0.4 eingeführt wurden, einschließlich Fehlerbehebungen und bekannter Probleme.

## Neue Funktionen {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench (Insight 6.0) umfasst diese neuen Funktionen und Visualisierungen für hinzugefügte Berichterstellungsfunktionen und Werkzeuge für die prädiktive Analyse.

| Funktionen der Data Workbench | Beschreibung |
|---|---|
| [Trichtervisualisierung](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | Mit der Trichtervisualisierung können Sie den sequenziellen Prozessfluss Ihrer Kunden definieren und bei jedem Schritt im Prozess einen Einblick in den Fallout der Besucher bieten. |
| [Besucher-Clustering](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | Mit Clustering können Sie Kundenmerkmale nutzen, um Besucher dynamisch zu kategorisieren und Cluster-Sets basierend auf ausgewählten Dateneingaben für die Kundenanalyse und das Targeting zu generieren. |
| [Korrelationsanalyse](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | Mithilfe der Korrelationsanalyse können Sie schnell relevante Datenbeziehungen identifizieren, um Ihre Analyse zu erweitern und zu verbessern. |
| [Aktualisierte DeviceAtlas-Verteilung](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | Die JSON-Datei DeviceAtlas wird jetzt in einer Bundle-Datei (einer umbenannten .tar.gz-Datei) zusammen mit DeviceAtlas.dll und DeviceAtlas64.dll bereitgestellt. |

## Anforderungen an Client-Upgrades {#section-f316103b48374b6eac77e8feb5c47ecf}

Führen Sie diese Aktualisierungsaufgaben für die Client-Funktionen von Data Workbench (Insight 6.0) aus:

**Aktualisieren der .zbin-Datei für den Client**

Data Workbench unterstützt jetzt einen Eingabemethoden-Editor (IME) als Sekundärtext-Eingabeprozess, mit dem Sie internationale Zeichen über die Tastatur mithilfe eines schwebenden Textfelds eingeben können. Data Workbench unterstützt standardmäßig Englisch, ermöglicht es Ihnen jedoch auch, andere Dateien zu laden, um internationale Sprachen zu unterstützen, z. B. eine virtuelle chinesische Tastatur (Pinyin IME).

Vor der Aktualisierung auf Version 6.0 ist eine neue Wörterbuchdatei (eine .zbin-Datei) von der Clientanwendung erforderlich. Sie können die benötigte .zbin-Datei aus dem Software- und Docs-Profil (Softdocs) abrufen.

Voraussetzungen:

* Vor der Aktualisierung auf den Insight 6.0-Client und Report Server 6.0 muss der Insight-Administrator zunächst auf Insight Server 6.0 aktualisieren.
* Der Insight-Administrator muss eine Zbin-Datei basierend auf der Sprache auswählen (en-us.zbin, zh-cn.zbin), die Sprachdatei kopieren, sie dann in insight.zbin umbenennen und die umbenannte Datei im Stammverzeichnis des Report Server platzieren, wo sich die ausführbare Datei befindet. Starten Sie dann den Insight Report Server neu.

Weitere Informationen zur serverseitigen Aktualisierung finden Sie unter [Anforderungen an die Server-Aktualisierung](../../../home/c-release-notes-insight/release-notes.md) .

**Aktualisieren der zbin-Datei für den Client (von Version 5.x auf 6.0)**

1. Um sicherzustellen, dass der Client während dieses Upgrades nicht vom Insight Server aktualisiert wird, setzen Sie Ihr Insight.cfg-Argument auf false.

   ```
   Update Software = bool: false
   ```

1. Starten Sie den Insight-Client neu.
1. Navigieren Sie zum Profil Software und Dokumente (Profil SoftDocs ) und laden Sie die erforderliche **[!UICONTROL Insight.zbin]** -Datei herunter: [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Kopieren Sie die Datei Insight.zbin in denselben Ordner wie die Datei Insight.exe.
1. Um sicherzustellen, dass der Insight-Client jetzt vom Insight Server aktualisiert wird, ändern Sie das Insight.cfg-Dateiargument in true:

   ```
   Update Software = bool: true
   ```

1. Starten Sie den Client neu.

   Ihr Client wird mit dem Server synchronisiert und Sie erhalten eine Meldung, dass Ihr Client heruntergeladen wird. Nach Abschluss des Downloads erhalten Sie eine Nachricht, in der Sie gefragt werden, ob Sie Ihren Insight-Client neu starten möchten.
1. Klicken Sie auf **OK**, um den Client neu zu starten.

   Der Client startet und aktualisiert auf Version 6.0.

1. Starten Sie den Client erneut neu, damit die Insight.zbin-Client-Synchronisation wirksam wird.

   Wenn Sie die folgende Meldung erhalten, bedeutet dies, dass der Ordner &quot;zbin&quot;nicht neben der Datei &quot;Insight.exe&quot;im richtigen Ordner abgelegt wurde.

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   Um das Problem zu beheben, löschen Sie Insight.exe, benennen Sie die neueste Version von Insight.exe.old in Insight.exe um und beginnen Sie dann erneut mit Schritt 1 oben.

## Anforderungen an die Server-Aktualisierung {#section-d6edba8b36234957ba8d06b555667a5a}

Führen Sie diese Aktualisierungsaufgaben für die Insight 6.0-Serverfunktionen aus:

**Aktualisieren Sie alle Insight Server 6.0-Pakete**. Insight 6.0 enthält Serverpakete, die aktualisiert werden müssen, einschließlich des neuen Predictive Analytics-Profils.

>[!IMPORTANT]
>
>Es wird empfohlen, dass Benutzer beim Aktualisieren ihre Servercluster mit neuen Installationen von Insight Server 6.0 aktualisieren.

Es wird außerdem empfohlen, dass der Client die Servercluster mit der Neuinstallation von Insight Server 6.0 aktualisiert.

## Servercluster aktualisieren

**Bereiten Sie die Sprachdatei (.zbin-Datei) vor.** Der Insight-Administrator wählt die  `<language>.zbin` Datei für die gewünschte Sprache aus (z. B.: en-us.zbin , zh-cn.zbin) im  `/localization/<language>.zbin` Ordner gespeichert. Der Administrator kopiert dann die Sprachdatei und benennt sie in &quot;insight.zbin&quot;um.

Nach der Vorbereitung der Sprachdatei (.zbin) müssen sowohl der Insight Client als auch der Report Server aktualisiert werden. Der Insight Client wird während des [Client-Aktualisierungsprozesses](../../../home/c-release-notes-insight/release-notes.md) aktualisiert, in den meisten Fällen wird der Insight-Administrator jedoch den Report Server aktualisieren.

**Aktualisieren von Report Server mit einer Sprachdatei (.zbin-Datei)**.

Für alle Sprachen erfordert Report Server 6.0 die Datei &quot;insight.zbin&quot;, die in den Stammordner von Report Server kopiert wurde.

Aktualisieren Sie die Sprachdateien des Report Server:

1. Fügen Sie die umbenannte Datei &quot;insight.zbin&quot;zum Stammverzeichnis von ReportServer hinzu.
1. Die Report Server-Konfigurationsdatei (reportserver.cfg) erfordert Schrifteinstellungen für Doppelbyte-Sprachen. Chinesisch erfordert beispielsweise das Hinzufügen von Schriftarten mit SimSun:

   ```
   Report Server.cfg - Add Fonts 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Ein Parameter für Report Server 6.0 muss in der Befehlszeile zur Lokalisierung übergeben werden, z. B.:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Wenn kein Gebietsschema angegeben ist, wird vom Report Server standardmäßig die in der Datei insight.zbin ausgewählte Sprache verwendet.

   Führen Sie die Schritte aus, um den ReportServer als Dienst mit den Locale-Parametern zu starten:

   1. Starten Sie eine Eingabeaufforderung als Administrator.
   1. Navigieren Sie zum Ordner ReportServer-Installation .
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

**Ändern Sie die Profilkonfigurationsdatei für Predictive Analytics**. Der Insight-Administrator muss die benutzerdefinierte Datei profile.cfg ändern, um das Predictive Analytics-Profil einzuschließen, das in Insight verfügbar sein soll.

Beispiel des Eintrags profile.cfg:

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

**Aktualisieren Sie die Datei** PAServer.cfg . Wenn Sie Predictive Analytics-Clustering-Aufträge an Insight Server senden möchten, müssen Sie die Datei PAServer.cfg für die Verarbeitung serverseitiger Clustering-Übermittlungen konfigurieren.

Das benutzerdefinierte Profil sollte die Datei PAServer.cfg vom Predictive Analytics-Profil (Server\Profiles\Predictive Analytics\Dataset) übernehmen. Konfigurieren und speichern Sie die Datei &quot;PAServer.cfg&quot;auf Ihrer Implementierungsseite.

>[!NOTE]
>
>Sobald PAServer.cfg konfiguriert und in einem benutzerdefinierten Profil gespeichert wurde, ist ein Neustart von Insight Server auf der gesamten Site erforderlich.

**Aktualisieren Sie Report Server.** Sie müssen die Schriftarten und Startparameter für Report Server aktualisieren.

Voraussetzungen:

* Vor der Aktualisierung von Report Server 6.0 muss der Insight-Administrator zunächst auf Insight Server 6.0 aktualisieren.
* Für alle Sprachen erfordert Report Server 6.0 das Hinzufügen von Insight.zbin zum Stammordner des Report Server. Stellen Sie sicher, dass `base/localization/<language>.zbin` kopiert und in &quot;insight.zbin&quot;umbenannt wird. Kopieren Sie es in den Stammordner des Report Server-Ordners.

Aktualisieren Sie die Parameter Schriftart und Start:

1. Für den Report Server ist die Schriftart-Einstellung für Doppelbyte erforderlich, um in verschiedene Sprachen ausgegeben zu werden.

   Beispiel:

   Report Server.cfg - Schriftarten hinzufügen

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Der Parameter für Report Server 6.0 muss zur Lokalisierung in der Befehlszeile übergeben werden.

   So starten Sie den Report Server als Dienst mit den Gebietsschemaparametern:

   1. Beenden Sie den Report Server-Dienst.
   1. Starten Sie eine Eingabeaufforderung als Administrator.
   1. Navigieren Sie zum Ordner Report Server-Installation .
   1. Geben Sie den folgenden Befehl ein, um den Dienst zu starten:

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

So überprüfen Sie, ob der Report Server mit den richtigen Parametern ausgeführt wird:

1. Windows Service Manager öffnen
1. Rechtsklick [!DNL Adobe Insight Report Server - Properties].
1. Der Pfad zur ausführbaren Datei enthält die Parameter:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Aktualisieren Sie den SiteCatalyst-Daten-Feed für Insight 6.0**. Das Dateinamenformat des SiteCatalyst-Daten-Feeds für Insight 6.0 wurde geändert.

Aktuelles Dateinamenformat:

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

Neues Dateinamenformat:

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>Diese Änderung betrifft nicht Benutzer, die derzeit mit der *wbench/ecom*-Version des SiteCatalyst-Daten-Feeds bereitgestellt werden.

Die Änderung des Dateinamenformats ermöglicht die vollständige Verwendung der Insight Start- und Endzeitdeklarationen während der Protokollverarbeitung. Dadurch kann der Prozess bewerten, ob der Inhalt der Datei gelesen werden soll, anstatt alle Quelldateien anhand einer Zeilensuche zu filtern.

In den meisten Fällen wurde nach Erhalt der Datei ein Umbenennungsprozess implementiert, um diese Funktion vollständig zu nutzen. Diese Änderung bietet standardmäßig die erforderliche Benennungskonvention, ohne dass ein sekundärer Prozess erforderlich und mit Mehraufwand verbunden sein muss.

So verwenden Sie den neuen SiteCatalyst-Daten-Feed:

1. Ermitteln Sie, wie der Empfangsprozess das neue Dateinamenformat handhabt.

   Die während der Implementierung bereitgestellten standardmäßigen Umbenennungs-/Verschieben-Skripte verschieben die Dateien mit der Erweiterung &quot;.gz&quot; und führen nur einen Umbenennungsvorgang durch, wenn der Dateiname mit dem Dateinamenformat mit der vorherigen RSID übereinstimmt.

   Das neue Dateinamenformat:

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. Überprüfen Sie die definierten Protokollquellenpfade, um sicherzustellen, dass alle Dateien gelesen werden.

   Wenn Sie bereits ein Umbenennungsskript implementiert haben, definieren Sie bereits Ihre Protokollquellen, um dieses neue Dateinamenformat zu lesen.

## Fehlerbehebungen {#section-203f917dd6224114a1f801309c4c2cee}

* Jetzt wurde die Schlüsselkombination zum Verlassen eines Arbeitsbereichs ohne Speichern von Änderungen auf **[!UICONTROL `<Ctrl>`+`<Backspace>`]** aktualisiert. Zuvor haben Sie Änderungen vermieden und einen Arbeitsbereich durch Drücken von `<Ctrl>` + `<Delete>` geschlossen.

## Versionshinweise zu Data Workbench 6.0.4{#data-workbench-release-notes}

Neue Funktionen, die in Data Workbench 6.0.4 eingeführt wurden, einschließlich Fehlerbehebungen und bekannter Probleme.

Informationen zu früheren Funktionen und Fehlerbehebungen, die auf jeder früheren Version basieren, finden Sie in den Archiven der Versionshinweise [a1/>.](https://docs.adobe.com/content/help/de-DE/data-workbench/using/release-notes/release-notes.html)

## Neue Funktionen {#section-2-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.0.4 enthält diese neuen Funktionen und Visualisierungen für hinzugefügte Reporting- und Prognoseanalysetools.

**Visualisierung der Tendenzauswertung**. Data Workbench berechnet die Bewertungen für jeden Besucher als geschätzte Wahrscheinlichkeit, dass ein bestimmtes Ereignis eintritt. Mit der Visualisierung der Besucherbewertung können Sie eine Bewertungsdimension erstellen, die basierend auf den Eingabevariablen eine Wahrscheinlichkeit eines bestimmten Ereignisses für jeden Besucher angibt, der interessiert ist.

![](assets/visitor_scoring_visual.png)

Weitere Informationen zu dieser Funktion finden Sie unter [Tendenzauswertung](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40) .

## Upgrade-Anforderungen {#section-08bd6fe3da8740fcb19688e8cac6f223}

**Die Protokollquellen-ID muss definiert** sein. Ab Version 6.04 erhalten Sie den folgenden Fehler, wenn die Protokollquellen-ID nicht definiert ist:

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

Die Aufzeichnung von Zeilen pro Protokollquelle wurde in Data Workbench 6.0 hinzugefügt und kann im benutzerdefinierten Profil Log Processing.cfg definiert werden, indem eine eindeutige Protokollquellen-ID hinzugefügt wird. Wenn Sie über eine leere Protokollquellen-ID verfügen, können Sie Probleme bei der Protokollverarbeitung sehen, z. B. das unvollständige Lesen der Protokollquelldaten und andere Diskrepanzen.

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

Unter [!DNL Profiles/`<profilename>`/dataset/Cluster.cfg] können Sie jetzt separate File Server Units (FSU) für die Server Normalize und Source List angeben. Diese Dienste sind nicht mehr an das Übergeordnete FSU gebunden.

>[!NOTE]
>
>Wenn der Listenserver nicht angegeben ist, erbt der Listenserver die Konfigurationseinstellungen des Servers normalisieren .

Beispiel in der Datei [!DNL cluster.cfg] .

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

* In Data Workbench 6.0 unterstützten die Korrelationsmatrix und der Cluster-Builder keine Berechnung im Hintergrund. Dieses Problem wurde in Version 6.0.4 behoben.
* Wenn Sie zuvor eine Auswahl für den Trichter hatten und einen Schritt entfernt haben, konnte eine Zugriffsverletzung auftreten. Dies wurde behoben.
* Fehlerkorrektur - Es wurde eine potenzielle Sperrbedingung im Segmentexport behoben, die unter starken Ladebedingungen Probleme verursachen kann.
