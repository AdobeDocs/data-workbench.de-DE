---
description: Richten Sie die Datei "insight.zbin"ein, um die Sprache der Clientanwendung festzulegen.
solution: Analytics
title: Lokalisierte Sprachen einrichten
topic: Data workbench
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lokalisierte Sprachen einrichten{#setting-up-localized-languages}

Richten Sie die Datei &quot;insight.zbin&quot;ein, um die Sprache der Clientanwendung festzulegen.

## Aktualisieren der Data Workbench-Serverkomponenten {#section-5d07a081befc4eaa8fdf7fea904e0d48}

Der Administrator muss zunächst die folgenden Aufgaben ausführen, um diese Serverkomponenten zu aktualisieren:

1. **Aktualisierung auf Data Workbench Server 6.x.** Sie müssen den Data Workbench-Server für die Lokalisierung aktualisieren, indem Sie die [!DNL base\localization\*.zbin] Datei aktualisieren. Diese [!DNL insight.zbin] Datei wird dann in den Client kopiert.

   Neben der [!DNL insight.zbin] Datei befindet sich eine Datei im Installationsordner [!DNL insight.exe] . Wenn Sie eine Verbindung zu einem Server herstellen, der Ihnen keine sprachspezifischen [!DNL .zbin] Dateien bereitstellt, verwendet Data Workbench diese Datei weiter.

   Die Backup- [!DNL insight.zbin] Datei kann in jeder Sprache bereitgestellt werden. Wenn Sie daher Data Workbench auf Chinesisch verwenden und eine Verbindung zu einem Server herstellen, der diese Sprache nicht unterstützt, dann befindet sich Ihr Data Workbench-Client weiterhin auf Chinesisch, auch wenn der Server Ihr Basisprofil ändert und Ihre [!DNL .zbin] Dateien aus dem [!DNL Base/Localization] Ordner entfernt.

1. **Aktualisieren Sie den Data Workbench-Berichtsserver.** Der [!DNL insight.zbin] Stammordner des Data Workbench-Berichtsservers wird standardmäßig in Englisch angezeigt. Als Administrator müssen Sie die [!DNL .zbin] Datei aus dem aktualisierten Report Server-Paket auswählen und kopieren und im Stammverzeichnis des Data Workbench-Berichtsservers ablegen. Wie der Client erfordert der Berichtsserver auch die richtigen Argumente für die ausgewählte Sprache, wie zum Beispiel [!DNL Insight.exe -zh-cn]

   1. Beenden Sie die Berichtsserverdienste.
   1. Kopieren Sie den [!DNL Localization] Ordner aus dem neuen Report Server-Paket.
   1. Kopieren Sie die [!DNL Localization] Datei aus dem [!DNL Insight.zbin] Ordner in den Stammordner des Berichtsservers, auf dem sich der [!DNL Insight.exe] Ordner befindet.

   1. Fügen Sie alle erforderlichen Argumente hinzu, z. B. [!DNL insight.exe -zh-cn]
   1. Starten Sie den Berichtsserver neu.

## Data Workbench-Client aktualisieren {#section-9653d3fcaf2a4337a97b685857e7aeac}

Führen Sie nach der Aktualisierung des Servers die folgenden Schritte aus, um jeden Client zu aktualisieren.

1. Um sicherzustellen, dass der Client während dieser Aktualisierung nicht vom Server aktualisiert wird, setzen Sie Ihr [!DNL Insight.cfg] Argument auf False.

   ```
   Update Software = bool: false
   ```

1. Starten Sie den Client neu.
1. Navigieren Sie zum Profil Software und Docs (SoftDocs-Profil) und laden Sie die erforderliche **[!UICONTROL insight.zbin]** Datei aus dem Clientpaket herunter: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Verschieben Sie die [!DNL insight.zbin] Datei in den Ordner, in dem sich [!DNL insight.exe] befindet.

1. Um sicherzustellen, dass die Clientdateien jetzt vom Server aktualisiert werden, ändern Sie das [!DNL Insight.cfg] Dateiargument in True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Ihr Client wird mit dem Server synchronisiert, und es wird eine Meldung angezeigt, dass er aktualisiert wird. Nach Abschluss des Downloads erhalten Sie eine Nachricht, in der Sie gefragt werden, ob Sie Ihren Client neu starten möchten.

1. Klicken Sie auf **OK** , um den Client neu zu starten.

Wenn Sie die folgende Meldung erhalten, bedeutet dies, dass die [!DNL zbin] Datei nicht am selben Speicherort wie die Datei platziert wurde [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Lokalisierte Startbildschirme**

Data Workbench sucht nach den folgenden Startbildschirmdateien:

* Englisch (Standard): [!DNL Base/Images/<version_product> Splash.png]
* Chinesisch (wenn mit -zh-cn begonnen wird): [!DNL Base/Images/<version_product> Splash zh-cn.png].

Wenn ein Begrüßungsbildschirm angefordert, aber fehlt, greift Data Workbench standardmäßig auf den englischen Begrüßungsbildschirm zu.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

