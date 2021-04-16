---
description: Richten Sie die Datei "insight.zbin"ein, um die Sprache der Clientanwendung festzulegen.
title: Einrichten lokalisierter Sprachen
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Einrichten lokalisierter Sprachen{#setting-up-localized-languages}

Richten Sie die Datei &quot;insight.zbin&quot;ein, um die Sprache der Clientanwendung festzulegen.

## Aktualisieren der Data Workbench-Serverkomponenten {#section-5d07a081befc4eaa8fdf7fea904e0d48}

Der Administrator muss zunächst die folgenden Aufgaben ausführen, um diese Serverkomponenten zu aktualisieren:

1. **Aktualisierung auf Data Workbench-Server 6.x.** Sie müssen den Data Workbench-Server zur lokale Anpassung aktualisieren, indem Sie die  [!DNL base\localization\*.zbin] Datei aktualisieren. Diese [!DNL insight.zbin]-Datei wird dann auf den Client kopiert.

   Neben der Datei [!DNL insight.exe] befindet sich eine Datei [!DNL insight.zbin] im Installationsordner. Wenn Sie eine Verbindung zu einem Server herstellen, der Ihnen keine sprachspezifischen [!DNL .zbin]-Dateien bereitstellt, dann verwendet Data Workbench diese Datei weiter.

   Die Backup-Datei [!DNL insight.zbin] kann in jeder Sprache bereitgestellt werden. Wenn Sie also Data Workbench auf Chinesisch verwenden und eine Verbindung zu einem Server herstellen, der diese Sprache nicht unterstützt, dann befindet sich Ihr Data Workbench-Client weiterhin auf Chinesisch, auch wenn der Server Ihr Basisverzeichnis ändert und Ihre [!DNL .zbin]-Profile aus dem Ordner [!DNL Base/Localization] entfernt.

1. **Aktualisieren Sie den Data Workbench-Berichtsserver.** Der  [!DNL insight.zbin] Stammordner des Data Workbench-Berichtsservers wird standardmäßig in Englisch angezeigt. Als Administrator müssen Sie die Datei [!DNL .zbin] aus dem aktualisierten Report Server-Paket auswählen und kopieren und im Stammverzeichnis des Data Workbench-Berichtsservers ablegen. Wie der Client erfordert der Berichtsserver auch die richtigen Argumente für die ausgewählte Sprache, z. B. [!DNL Insight.exe -zh-cn]

   1. Beenden Sie die Berichtsserverdienste.
   1. Kopieren Sie den Ordner [!DNL Localization] aus dem neuen Report Server-Paket.
   1. Kopieren Sie im Ordner [!DNL Localization] die Datei [!DNL Insight.zbin] und platzieren Sie sie im Stammverzeichnis des Berichtsservers, auf dem sich [!DNL Insight.exe] befindet.

   1. hinzufügen aller erforderlichen Argumente, z. B. [!DNL insight.exe -zh-cn]
   1. Starten Sie den Berichtsserver neu.

## Aktualisieren Sie den Data Workbench-Client {#section-9653d3fcaf2a4337a97b685857e7aeac}

Führen Sie nach der Aktualisierung des Servers die folgenden Schritte aus, um jeden Client zu aktualisieren.

1. Um sicherzustellen, dass der Client während dieser Aktualisierung nicht vom Server aktualisiert wird, setzen Sie das [!DNL Insight.cfg]-Argument auf False.

   ```
   Update Software = bool: false
   ```

1. Starten Sie den Client neu.
1. Navigieren Sie zum Profil Software and Docs (SoftDocs-Profil) und laden Sie die erforderliche **[!UICONTROL insight.zbin]**-Datei aus dem Clientpaket herunter: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Verschieben Sie die Datei [!DNL insight.zbin] in den Ordner, in dem sich [!DNL insight.exe] befindet.

1. Um sicherzustellen, dass die Clientdateien jetzt vom Server aktualisiert werden, ändern Sie das Dateiargument [!DNL Insight.cfg] in True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Ihr Client wird mit dem Server synchronisiert, und es wird eine Meldung angezeigt, dass er aktualisiert wird. Nach Abschluss des Downloads erhalten Sie eine Nachricht, in der Sie gefragt werden, ob Sie Ihren Client neu starten möchten.

1. Klicken Sie auf **OK**, um den Client neu zu starten.

Wenn Sie die folgende Meldung erhalten, bedeutet dies, dass die Datei [!DNL zbin] nicht am selben Speicherort wie [!DNL Insight.exe] platziert wurde.

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
