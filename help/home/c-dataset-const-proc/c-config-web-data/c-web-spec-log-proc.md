---
description: Informationen zu webspezifischen Einstellungen, die im Datensatz zur Protokollverarbeitung definiert sind Schließen Sie Dateien ein, die mit Adobe-Profilen für die Site bereitgestellt werden.
solution: Analytics
title: Webspezifische Einstellungen für die Protokollverarbeitung
topic: Data workbench
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Webspezifische Einstellungen für die Protokollverarbeitung{#web-specific-settings-for-log-processing}

Informationen zu webspezifischen Einstellungen, die im Datensatz zur Protokollverarbeitung definiert sind Schließen Sie Dateien ein, die mit Adobe-Profilen für die Site bereitgestellt werden.

Die von diesen Einstellungen definierte Filterung erfolgt, nachdem die Protokolleinträge die Decoder verlassen und die Transformationen angewendet werden, jedoch vor der Auswertung durch die [!DNL Log Entry Condition].

* [HTTP-Statusfilter](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [Roboterfilter](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## HTTP-Statusfilter {#section-ac66acdcb6aa467d81c3721199e540fd}

Sie können Ihre Implementierung von konfigurieren, [!DNL Site] um Protokolleinträge mit sc-status-Codes von 400 oder höher aus dem Datensatz zu entfernen. Erfolgreiche Anforderungen haben Statuscodes von unter 400. Ihre Standardimplementierung umfasst eine [!DNL Log Processing Dataset Include] Datei, in der die HTTP-Statusfilterung konfiguriert ist.

**So bearbeiten Sie die Konfigurationseinstellungen für die HTTP-Statusfilterung**

1. Öffnen Sie die Datei [!DNL Profile Manager] im Datenaset-Profil und öffnen Sie die [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg] Datei.

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von angepasst haben, [!DNL Site]kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter der Datei nach Bedarf. Verwenden Sie das folgende Beispiel als Anleitung.

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   Informationen zur [!DNL Range] Bedingung finden Sie unter [Bedingungen](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).

1. Speichern Sie die [!DNL HTTP Status Filter.cfg] Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster auf klicken **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## Roboterfilter {#section-7f43681dfbc64b969619cb88f97d5ad5}

Sie können Ihre Implementierung so konfigurieren, dass Lookup-Dateien zum Entfernen von Protokolleinträgen verwendet werden, die von bekannten Robotern, Testskripten und IP-Adressen für interne Benutzer aus Ihrem Datensatz generiert wurden. [!DNL Site] Ihre Standardimplementierung umfasst eine [!DNL Log Processing Dataset Include] Datei, in der die Roboterfilterung konfiguriert ist.

**So bearbeiten Sie die Konfigurationseinstellungen für die Roboterfilterung**

1. Öffnen Sie die Datei [!DNL Profile Manager] im Datenaset-Profil und öffnen Sie die [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg] Datei.

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von angepasst haben, [!DNL Site]kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Parameter der Datei anhand des folgenden Beispiels und Informationen als Handbücher:

   ![](assets/cfg_WebParameters_RobotFilter.png)

   Die Datei enthält einen Parameter, [!DNL NotRobotCondition] der durch die folgenden drei Parameter definiert wird:

   * **Groß-/Kleinschreibung beim Robot-Filter:** True oder false. Wenn &quot;true&quot;, wird die Groß-/Kleinschreibung (oben/unten) bei der Roboterfilterung nicht berücksichtigt.
   * **Robot-Suchdatei, Grundlinie:** Pfad und Dateiname der Textdatei, die eine Liste der Browser-Benutzeragenten enthält, die bekannte Roboter sind und aus dem Datensatz herausgefiltert werden sollen. Adobe stellt die grundlegende Suchdatei für Roboter bereit. Wenn Sie keinen Pfad angeben, sucht der Data Workbench-Server im Ordner &quot;Suchen&quot;des Installationsordners des Data Workbench-Servers nach dieser Datei.
   * **Robot-Suchdatei, erweitert:** Der Pfad und der Dateiname einer optionalen Textdatei, die eine Liste der Browser-Benutzeragenten oder IP-Adressen enthält, die für Ihre Implementierung spezifische Roboter definieren. Diese Liste kann interne Überwachungsroboter, Testskripte und IP-Adressen für interne Benutzer enthalten, die aus dem Datensatz herausgefiltert werden sollten. Wenn Sie keinen Pfad angeben, sucht der Data Workbench-Server im Ordner &quot;Suchen&quot;des Installationsordners des Data Workbench-Servers nach dieser Datei.
   Wenn der Browser-Benutzeragent eines Protokolleintrags nicht in einer der beiden Nachschlagedateien aufgeführt ist, wird der Protokolleintrag als von einem echten Besucher generiert betrachtet und nicht aus dem Datensatz gefiltert.

   >[!NOTE]
   >
   >Die Übereinstimmung in den Roboter-Lookup-Dateien verwendet Unterzeichenfolgen zum Vergleich mit den Protokollfeldern c-ip und cs(user-agent). Wenn die Suchzeichenfolge mit &quot;$&quot;beginnt, muss sie mit der Vorderseite der zu testenden Zeichenfolge übereinstimmen, und wenn sie mit &quot;$&quot;endet, muss die Suchzeichenfolge mit dem Ende der zu testenden Zeichenfolge übereinstimmen. Wenn die Suchzeichenfolge mit &quot;$&quot;beginnt und mit &quot;$&quot;endet, müssen die Zeichenfolgen exakt übereinstimmen, damit der Protokolleintrag herausgefiltert werden kann. Um beispielsweise alle IP-Adressen in einem Block der Klasse C zu testen, würden Sie eine Zeichenfolge wie $231.78.123 verwenden. , um eine Übereinstimmung am Anfang der Zeichenfolge zu erzwingen. Dies würde mit den Adressen 231.78.123.0 bis 231.78.123.255 übereinstimmen.

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters klicken und auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

   >[!NOTE]
   >
   >Wenn es wichtig ist, dass sich die zum Erstellen eines Datensatzes verwendeten zugrunde liegenden Protokolleinträge nicht ändern (auch wenn sich die für die Erstellung und Aktualisierung des Datensatzes verwendeten Transformationen und seine Dimensionen ändern), sollten die Robot-Suchdatei, die Baseline und die Robot-Suchdatei (Extended) versionsgesteuert werden. Durch Platzierung einer Versionsnummer auf diesen Dateien wird sichergestellt, dass Aktualisierungen der standardmäßigen Roboter-Lookup-Dateien nicht versehentlich zu einer Änderung zuvor erstellter Berichtsdatensätze führen, indem Einträge in diesen Dateien hinzugefügt oder gelöscht werden.

