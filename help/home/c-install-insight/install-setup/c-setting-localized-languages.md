---
description: Richten Sie die Datei insight.zbin ein, um die Sprache der Clientanwendung festzulegen.
title: Einrichten lokalisierter Sprachen
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Einrichten lokalisierter Sprachen{#setting-up-localized-languages}

Richten Sie die Datei insight.zbin ein, um die Sprache der Clientanwendung festzulegen.

## Aktualisieren der Data Workbench-Serverkomponenten {#section-5d07a081befc4eaa8fdf7fea904e0d48}

Der Administrator muss zunächst diese Aufgaben ausführen, um diese Serverkomponenten zu aktualisieren:

1. **Aktualisierung auf Data Workbench-Server 6.x.** Sie müssen den Data Workbench-Server für die Lokalisierung aktualisieren, indem Sie die  [!DNL base\localization\*.zbin] Datei aktualisieren. Diese [!DNL insight.zbin]-Datei wird dann in den Client kopiert.

   Eine [!DNL insight.zbin] -Datei ist im Installationsordner neben der [!DNL insight.exe] -Datei enthalten. Wenn Sie eine Verbindung zu einem Server herstellen, der Ihnen keine sprachspezifischen [!DNL .zbin]-Dateien bereitstellt, wird Data Workbench mit der Verwendung dieser Datei fortfahren.

   Die Backup-Datei [!DNL insight.zbin] kann in jeder beliebigen Sprache bereitgestellt werden. Wenn Sie also Data Workbench auf Chinesisch verwenden und eine Verbindung zu einem Server herstellen, der diese Sprache nicht unterstützt, ist Ihr Data Workbench-Client weiterhin auf Chinesisch, auch wenn der Server Ihr Basisprofil ändert und Ihre [!DNL .zbin]-Dateien aus dem Ordner [!DNL Base/Localization] entfernt.

1. **Aktualisieren Sie den Data Workbench-Berichtsserver.** Der Ordner  [!DNL insight.zbin] im Stammordner des Data Workbench-Berichtsservers wird standardmäßig in englischer Sprache angezeigt. Als Administrator müssen Sie die Datei [!DNL .zbin] aus dem aktualisierten Report Server-Paket auswählen und kopieren und im Stammverzeichnis des Data Workbench-Berichtsservers ablegen. Wie der Client erfordert auch der Berichtsserver die richtigen Argumente für die ausgewählte Sprache, z. B. [!DNL Insight.exe -zh-cn]

   1. Beenden Sie die Berichtsserverdienste.
   1. Kopieren Sie den Ordner [!DNL Localization] aus dem neuen Report Server-Paket.
   1. Kopieren Sie aus dem Ordner [!DNL Localization] die Datei [!DNL Insight.zbin] und legen Sie sie im Stammverzeichnis des Berichtsservers ab, auf dem sich [!DNL Insight.exe] befindet.

   1. Fügen Sie alle erforderlichen Argumente hinzu, z. B. [!DNL insight.exe -zh-cn]
   1. Starten Sie den Berichtsserver neu.

## Aktualisieren des Data Workbench-Clients {#section-9653d3fcaf2a4337a97b685857e7aeac}

Führen Sie nach der Aktualisierung des Servers die folgenden Schritte aus, um jeden Client zu aktualisieren.

1. Um sicherzustellen, dass der Client während dieser Aktualisierung nicht vom Server aktualisiert wird, setzen Sie Ihr [!DNL Insight.cfg]-Argument auf &quot;False&quot;.

   ```
   Update Software = bool: false
   ```

1. Starten Sie den Client neu.
1. Navigieren Sie zum Profil Software und Dokumente (Profil SoftDocs ) und laden Sie die erforderliche **[!UICONTROL insight.zbin]**-Datei aus dem Client-Paket herunter: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Verschieben Sie die Datei [!DNL insight.zbin] in den Ordner, in dem sich [!DNL insight.exe] befindet.

1. Um sicherzustellen, dass die Clientdateien jetzt vom Server aktualisiert werden, ändern Sie das [!DNL Insight.cfg]-Dateiargument in True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Ihr Client wird mit dem Server synchronisiert und Sie werden eine Meldung erhalten, dass er aktualisiert wird. Nach Abschluss des Downloads erhalten Sie eine Nachricht, in der Sie gefragt werden, ob Sie Ihren Client neu starten möchten.

1. Klicken Sie auf **OK**, um den Client neu zu starten.

Wenn Sie die folgende Meldung erhalten, bedeutet dies, dass die [!DNL zbin]-Datei nicht am selben Speicherort wie die [!DNL Insight.exe] platziert wurde.

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Lokalisierte Startbildschirme**

Data Workbench sucht nach den folgenden Begrüßungsbildschirmdateien:

* Englisch (Standard): [!DNL Base/Images/<version_product> Splash.png]
* Chinesisch (bei Beginn mit -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

Wenn ein Begrüßungsbildschirm angefordert wird, aber fehlt, greift Data Workbench standardmäßig auf den englischen Begrüßungsbildschirm zu.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
