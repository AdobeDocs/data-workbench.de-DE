---
description: Informationen zu webspezifischen Einstellungen, die im Datensatzdokument zur Protokollverarbeitung definiert sind Include-Adoben, die mit Seitenprofilen für Site bereitgestellt werden.
title: Web-spezifische Einstellungen für die Protokollverarbeitung
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
exl-id: abb6e6a7-011f-40d6-b778-16da2332af72
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# Web-spezifische Einstellungen für die Protokollverarbeitung{#web-specific-settings-for-log-processing}

{{eol}}

Informationen zu webspezifischen Einstellungen, die im Datensatzdokument zur Protokollverarbeitung definiert sind Include-Adoben, die mit Seitenprofilen für Site bereitgestellt werden.

Die durch diese Einstellungen definierte Filterung erfolgt, nachdem die Protokolleinträge die Decoder verlassen und die Transformationen angewendet werden, jedoch vor der Auswertung durch die [!DNL Log Entry Condition].

* [HTTP-Statusfilterung](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [Roboterfilterung](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## HTTP-Statusfilterung {#section-ac66acdcb6aa467d81c3721199e540fd}

Sie können Ihre Implementierung von [!DNL Site] , um Protokolleinträge mit sc-status-Codes von 400 oder höher aus dem Datensatz zu entfernen. Erfolgreiche Anfragen haben Status-Codes, die kleiner als 400 sind. Ihre Standardimplementierung umfasst eine [!DNL Log Processing Dataset Include] Datei, in der die HTTP-Statusfilterung konfiguriert ist.

**So bearbeiten Sie die Konfigurationseinstellungen für die HTTP-Statusfilterung**

1. Öffnen Sie die [!DNL Profile Manager] in Ihrem Datensatzprofil und öffnen Sie die [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg] -Datei.

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site]angegeben ist, kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter der Datei nach Bedarf. Verwenden Sie das folgende Beispiel als Anleitung.

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   Informationen zum [!DNL Range] -Bedingung, siehe [Bedingungen](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).

1. Speichern Sie die [!DNL HTTP Status Filter.cfg] Datei durch Rechtsklick **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, finden Sie im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme-Datei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## Roboterfilterung {#section-7f43681dfbc64b969619cb88f97d5ad5}

Sie können Ihre Implementierung von [!DNL Site] , um Lookup-Dateien zu verwenden, um Protokolleinträge zu entfernen, die von bekannten Robotern, Testskripten und IP-Adressen für interne Benutzer aus Ihrem Datensatz generiert wurden. Ihre Standardimplementierung umfasst eine [!DNL Log Processing Dataset Include] -Datei, in der die Roboterfilterung konfiguriert ist.

**So bearbeiten Sie die Konfigurationseinstellungen für die Roboterfilterung**

1. Öffnen Sie die [!DNL Profile Manager] in Ihrem Datensatzprofil und öffnen Sie die [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg] -Datei.

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site]angegeben ist, kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Parameter der Datei mit dem folgenden Beispiel und Informationen als Handbücher:

   ![](assets/cfg_WebParameters_RobotFilter.png)

   Die Datei enthält eine [!DNL NotRobotCondition] wird durch die folgenden drei Parameter definiert:

   * **Groß-/Kleinschreibung - Robot-Filterung:** True oder false. Wenn &quot;true&quot;, wird die Groß-/Kleinschreibung bei der Roboterfilterung nicht berücksichtigt.
   * **Robot-Lookup-Datei, Grundlinie:** Pfad und Dateiname der Textdatei, die eine Liste der Browser-Benutzeragenten enthält, die bekannte Roboter sind und aus dem Datensatz gefiltert werden sollen. Adobe stellt die Grundlinien-Suchdatei für Roboter bereit. Wenn Sie keinen Pfad angeben, sucht der Data Workbench-Server im Ordner &quot;Suchen&quot;des Installationsordners des Data Workbench-Servers nach dieser Datei.
   * **Robot-Lookup-Datei, erweitert:** Pfad und Dateiname einer optionalen Textdatei, die eine Liste von Browser-Benutzeragenten oder IP-Adressen enthält, die für Ihre Implementierung spezifische Roboter definieren. Diese Liste kann interne Überwachungsrobots, Testskripte und IP-Adressen für interne Benutzer enthalten, die aus dem Datensatz gefiltert werden sollen. Wenn Sie keinen Pfad angeben, sucht der Data Workbench-Server im Ordner &quot;Suchen&quot;des Installationsordners des Data Workbench-Servers nach dieser Datei.

   Wenn der Browser-Benutzeragent eines Protokolleintrags in keiner der Lookup-Dateien aufgeführt ist, gilt der Protokolleintrag als von einem echten Besucher generiert und wird nicht aus dem Datensatz gefiltert.

   >[!NOTE]
   >
   >Beim Abgleichen in den Roboter-Lookup-Dateien werden Unterzeichenfolgen verwendet, um sie mit den Protokollfeldern c-ip und cs(user-agent) zu vergleichen. Wenn die Suchzeichenfolge mit &quot;$&quot;beginnt, muss sie mit der Vorderseite der getesteten Zeichenfolge übereinstimmen und wenn sie mit &quot;$&quot;endet, muss die Suchzeichenfolge mit dem Ende der getesteten Zeichenfolge übereinstimmen. Wenn die Suchzeichenfolge sowohl mit &quot;$&quot;als auch mit &quot;$&quot;beginnt, müssen die Zeichenfolgen genau übereinstimmen, damit der Protokolleintrag herausgefiltert werden kann. Um beispielsweise für alle IP-Adressen in einem Block der Klasse C zu testen, verwenden Sie eine Zeichenfolge wie $231.78.123. , um eine Übereinstimmung vor der Zeichenfolge zu erzwingen. Dies entspricht den Adressen 231.78.123.0 bis 231.78.123.255.

1. Speichern Sie die Datei durch Rechtsklick **[!UICONTROL (modified)]** oben im Fenster und klicken Sie auf **[!UICONTROL Save]**.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, finden Sie im [!DNL Profile Manager]klicken Sie mit der rechten Maustaste auf das Häkchen für die Datei im [!DNL User] und klicken Sie auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme-Datei gehört.

   Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

   >[!NOTE]
   >
   >Wenn es wichtig ist, dass sich die zugrunde liegenden Protokolleinträge, die zum Erstellen eines Datensatzes verwendet werden, nicht ändern (auch wenn sich die zur Erstellung und Aktualisierung des Datensatzes verwendeten Umwandlungen und seine Dimensionen ändern), sollten die Robot Lookup-Datei, die Baseline und die Robot Lookup-Datei (erweitert) versionsgesteuert werden. Durch die Platzierung einer Versionsnummer auf diesen Dateien wird sichergestellt, dass Aktualisierungen an den standardmäßigen Roboter-Lookup-Dateien nicht versehentlich zuvor erstellte Berichtsdatensätze ändern, indem Einträge in diesen Dateien hinzugefügt oder gelöscht werden.
