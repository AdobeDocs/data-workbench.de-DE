---
description: Informationen zu webspezifischen Einstellungen, die in Datensatzumwandlungsdateien definiert sind Einschließen von Dateien, die mit Adobe-Profilen für Site bereitgestellt werden.
title: Web-spezifische Einstellungen für Umwandlungen
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 1%

---

# Web-spezifische Einstellungen für Umwandlungen{#web-specific-settings-for-transformation}

Informationen zu webspezifischen Einstellungen, die in Datensatzumwandlungsdateien definiert sind Einschließen von Dateien, die mit Adobe-Profilen für Site bereitgestellt werden.

Die durch diese Einstellungen definierten Bedingungen, Dimensionen und Parameter werden während der Umwandlungsphase der Datensatzerstellung erstellt.

* [Seitenansicht-Bedingung](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [URI-Dimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Referrer-Dimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Sitzungsparameter](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Seitenansicht-Bedingung {#section-cc2807a12a88492f8b64a43234a1f835}

[!DNL Page View Condition] ist ein Bedingungsvorgang, der bestimmt, ob ein bestimmter Protokolleintrag (d. h. eine Seitenanfrage) in die Daten aufgenommen werden soll, die über den Seitenansichtsverlauf eines Besuchers erfasst wurden. Wenn der Protokolleintrag den Wert [!DNL Page View Condition] erfüllt, wird er zum Element der zählbaren Dimension &quot;Seitenansicht&quot;. Wenn ein Protokolleintrag die [!DNL Page View Condition] nicht erfüllt, sind seine Datenfelder auch für andere Dimensionen zugänglich. Zusätzlich zur Dimension &quot;Seitenansicht&quot;können die Ergebnisse von [!DNL Page View Condition] die folgenden Dimensionen beeinflussen:

* **[!DNL URI]und  [!DNL Page]:** Diese Dimensionen sind direkt von  [!DNL Page View Condition]betroffen. Wenn die angegebene Seite die [!DNL Page View Condition,] nicht übergibt, ist sie nicht in den URI- oder Seitendimensionen enthalten.

* **[!DNL Visitor Page Views]und  [!DNL Session Page Views]:** Die Dimensionen &quot;Besucherseitenansichten&quot;und &quot;Sitzungsseitenansichten&quot;entsprechen der Anzahl der Seiten, die ein Besucher in oder in einer bestimmten Sitzung aufgerufen hat. Seiten, die von [!DNL Page View Condition] herausgefiltert wurden, sind nicht Teil dieser Zählung.

* **Sitzungsnummer:** Die Dimension &quot;Sitzungsnummer&quot; [!DNL Page View Condition] hat einen indirekten Effekt. Die Dimension Sitzungsnummer wird vor [!DNL Page View Condition] erstellt. Daher ist es bei der Betrachtung von [!DNL Session Number] im Verhältnis zu [!DNL Page Views] möglich, Sitzungen ohne Seitenansichten zu haben.

Ihre Standardimplementierung von [!DNL Site] enthält eine [!DNL Transformation Dataset Include] -Datei, in der die zählbare Dimension &quot;Seitenansicht&quot;und die zugehörige [!DNL Page View Condition] definiert sind.

Informationen zu zählbaren Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**So bearbeiten Sie die Konfigurationseinstellungen für die Seitenansichtsbedingung**

1. Öffnen Sie [!DNL Profile Manager] in Ihrem Datensatzprofil und öffnen Sie die Datei [!DNL Dataset\Transformation\Traffic\Page View.cfg] .

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, vom beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter von [!DNL Page View Condition] nach Bedarf. Verwenden Sie das folgende Beispiel als Anleitung. In dieser Datei wird [!DNL Page View Condition] durch eine [!DNL Copy]-Umwandlung definiert. Beachten Sie, dass diese Datei auch die Definition der zählbaren Dimension &quot;Seitenansicht&quot;enthält.

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Informationen zu zählbaren Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Informationen zur Umwandlung von [!DNL Copy] finden Sie unter [Datenumwandlungen](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Speichern Sie die Datei, indem Sie oben im Fenster mit der rechten Maustaste auf **[!UICONTROL (modified)]** klicken und dann auf **[!UICONTROL Save]** klicken.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## URI-Dimension {#section-348f7e9099d049d197a7cdcbc8a6c234}

Wenn Sie mit [!DNL Site] arbeiten, müssen Sie die URI-Dimension definieren, deren Elemente die URI-Stile der angezeigten Website-Seiten sind. Ihre Standardimplementierung enthält eine [!DNL Transformation Dataset Include]-Datei, in der die URI-einfache Dimension definiert ist.

Informationen zu einfachen Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**So bearbeiten Sie die Konfigurationseinstellungen für die URI-Dimension**

1. Öffnen Sie [!DNL Profile Manager] in Ihrem Datensatzprofil und öffnen Sie die Datei [!DNL Dataset\Transformation\Traffic\URI.cfg] .

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, vom beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter der Datei nach Bedarf. Verwenden Sie das folgende Beispiel und Informationen als Anleitungen.

![](assets/cfg_WebParameters_URI.png)

Die Konfigurationseinstellungen für die URI-Dimension umfassen die folgenden beiden Parameter:

* **Groß-/Kleinschreibung:** Wahr oder falsch. Wenn &quot;true&quot;, wird die Groß-/Kleinschreibung bei der Identifizierung eindeutiger Seiten berücksichtigt. Der Standardwert ist &quot;true&quot;.
* **Maximale Elemente:** Die maximale Anzahl von Elementen (d. h. URIs) für die URI-Dimension. Der Standardwert lautet 32768.

   >[!NOTE]
   >
   >Eine Änderung dieses Werts kann zu schwerwiegenden Leistungsproblemen führen. Ändern Sie diesen Wert nicht, ohne die Adobe zu konsultieren.

* Speichern Sie die Datei [!DNL URI.cfg], indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und dann auf **[!UICONTROL Save]** klicken.

* Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## Referrer-Dimension {#section-8a97ec34d18b4814b5f95495ac4f8638}

Wenn Sie mit [!DNL Site] arbeiten, müssen Sie die Dimension Referrer definieren, deren Elemente aus den Domänen der zweiten Ebene der Referrer der ersten Protokolleinträge in allen Sitzungen bestehen. Ihre Standardimplementierung enthält eine [!DNL Transformation Dataset Include]-Datei, in der die einfache Dimension Referrer definiert ist.

Informationen zu einfachen Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**So bearbeiten Sie die Konfigurationseinstellungen für die Dimension &quot;Referrer&quot;**

1. Öffnen Sie [!DNL Profile Manager] in Ihrem Datensatzprofil und öffnen Sie die Datei [!DNL Dataset\Transformation\Traffic\Referrer.cfg] .

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, vom beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter der Datei nach Bedarf. Verwenden Sie das folgende Beispiel und Informationen als Anleitungen.

   ![](assets/cfg_WebParameters_Referrer.png)

   Die Konfigurationseinstellungen für die Dimension &quot;Referrer&quot;umfassen den Parameter &quot;Maximale Elemente&quot;, der die maximale Anzahl von Elementen (d. h. Referrern) für die Dimension &quot;Referrer&quot;angibt. Der Standardwert lautet 32768.

   >[!NOTE]
   >
   >Im obigen Beispiel ist der Parameter [!DNL Maximum Elements] auf 0 gesetzt. Wenn dieser Parameter auf 0 gesetzt ist, verwendet der Data Workbench-Server den internen Standardwert 32768.

1. Speichern Sie die Datei [!DNL Referrer.cfg], indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und dann auf **[!UICONTROL Save]** klicken.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## Sitzungsparameter {#section-0a209b0c504041a5801f7f71a963c8b1}

Wenn Sie mit [!DNL Site] arbeiten, können Sie Parameter angeben, die die Grenzen einer Besuchersitzung auf einer Website definieren. Diese Parameter sind nur gültig, wenn sie in einer [!DNL Transformation Dataset Include]-Datei innerhalb Ihrer [!DNL Site]-Implementierung definiert sind.

Die folgenden Parameter sind insofern eindeutig, als sie Mitglieder des [!DNL Transformation Dataset Include]-Vektors der Datei [!DNL Parameters] sein können oder als einzelne Parameter in der Datei [!DNL Transformation.cfg]aufgeführt werden können. Ein Parameter kann genau einmal definiert werden. Daher werden diese Parameter entweder in der Datei [!DNL Transformation.cfg]oder im Vektor [!DNL Parameters] des Datensatzes definiert und nicht in beiden Dateien.
**Maximale Sitzungsdauer und Sitzungs-Timeout**

Maximale Sitzungsdauer und Sitzungs-Timeout sind Zeichenfolgenparameter, die die Dauer der Sitzung eines Besuchers definieren. Diese Parameter funktionieren mit dem Parameter Interne Domänen , um die Sitzungslänge zu bestimmen.

Die maximale Sitzungsdauer gibt die längste Sitzungsdauer an, bevor eine neue Sitzung gestartet wird. Dadurch wird verhindert, dass Webseiten mit automatischer Inhaltsaktualisierung Sitzungen erstellen, die beliebig lang sind. Wenn der Referrer eines Klicks auf einen der Einträge im Parameter &quot;Interne Domänen&quot;festgelegt ist, wird dieser Timeout verwendet, um das Ende einer Sitzung zu definieren. Keine Sitzung darf die angegebene maximale Sitzungsdauer überschreiten, unabhängig von der Anzahl der darin enthaltenen Klicks. Der empfohlene Wert beträgt 48 Stunden.

Sitzungs-Timeout gibt die Zeit an, die zwischen den Protokolleinträgen eines bestimmten Besuchers verstreichen muss, um das Ende einer Sitzung und den Beginn einer neuen Sitzung zu bestimmen (d. h. die typische Zeitüberschreitung, die zur Definition einer Benutzersitzung verwendet wird). Der empfohlene Wert für diesen Parameter beträgt 30 Minuten. Wenn der Referrer eines Klicks nicht auf einen der Referrer im Parameter &quot;Interne Domänen&quot;festgelegt ist, wird diese Zeitüberschreitung zur Definition der Sitzung verwendet. Wenn cs (referrer-domain) für einen Protokolleintrag in der Liste der internen Domänen enthalten ist, bestimmt die maximale Sitzungsdauer, ob der aktuelle Protokolleintrag Teil einer vorhandenen Sitzung oder des Beginns einer neuen Sitzung ist.

Stellen Sie sich eine Situation vor, in der ein Besucher während des Site-Durchsuchens für einen längeren Zeitraum als das Sitzungs-Timeout von seinem Computer weg angerufen wird. Nach seiner Rückkehr durchsuchte er weiter, wo er aufgehört hatte. Da der Besucher die Site nie verlässt oder seinen Browser schließt, ist die cs (Referrer-Domäne) seines nächsten Klicks mit der internen Domäne identisch. Die ursprüngliche Sitzung bleibt aktiv, solange die Einstellung Maximale Sitzungsdauer nicht erreicht wird. Wenn die Domäne der Site als interne Domäne aufgelistet ist und die maximale Zeitüberschreitung nicht erreicht wird, wird die Interaktion des Besuchers als einzelne Sitzung und nicht als zwei separate Sitzungen angezeigt. Wenn der Besucher jedoch zu seinem Computer zurückkehrt und sein nächster Klick einen externen (oder leeren) Referrer aufweist, beginnt eine neue Sitzung.

>[!NOTE]
>
>Die [!DNL Sessionize]-Transformation von [!DNL Timeout Condition] spielt auch eine Rolle bei der Bestimmung der Länge der Sitzung eines Besuchers. Wenn Sitzungs-Timeout und maximale Sitzungsdauer nicht zutreffen, wird [!DNL Timeout Condition] überprüft, um zu bestimmen, ob ein Protokolleintrag als Beginn einer neuen Sitzung betrachtet werden soll. Weitere Informationen finden Sie unter [Datenumwandlungen](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**So bearbeiten Sie die Parameter &quot;Maximale Sitzungsdauer&quot;und &quot;Sitzungs-Timeout&quot;**

Wenn Sie mit [!DNL Site] arbeiten, enthält Ihre Standardimplementierung wahrscheinlich eine [!DNL Transformation Dataset Include]-Datei, in der die Namen und empfohlenen Werte dieser Parameter angegeben sind.

1. Öffnen Sie [!DNL Profile Manager] in Ihrem Datensatzprofil und navigieren Sie zu [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der diese Parameter definiert sind, vom beschriebenen Speicherort unterscheiden.

1. Bearbeiten Sie die Werte der Parameter nach Bedarf. Stellen Sie sicher, dass Sie die gewünschten Einheiten (Minuten, Stunden usw.) angeben.

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Speichern Sie die Datei [!DNL Session Parameters.cfg], indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und **[!UICONTROL Save]** klicken.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

**[!DNL Internal Domains]**

[!DNL Internal Domains] ist ein Vektorparameter, der Hosts auf Domänenebene (interne Referrer) auflistet, die als Teil einer bestimmten Website behandelt werden sollten. Diese Hosts werden aus der Dimension der verweisenden Stelle entfernt (bei der es sich um eine Liste der externen Referrer-Informationen handelt). Wenn cs (Referrer-Domäne) mit einer der im Satz der internen Domänen aufgelisteten Zeichenfolgen übereinstimmt, wird die Sitzungs-Timeout-Funktion ignoriert und die maximale Sitzungsdauer wird verwendet, um die Sitzungslänge zu bestimmen.

Der Parameter &quot;Interne Domänen&quot;kann auch verwendet werden, um den Start einer neuen Sitzung zu verhindern, wenn Besucher zwischen mehreren Domänen eines Unternehmens wechseln, die auf eine Weise zugeordnet sind, die das Sitzungs-Timeout überschreitet. Angenommen, ein Unternehmen hat Teile seiner Website auf zwei Domänen aufgeteilt: einer wird protokolliert ( [!DNL xyz.com]), der andere nicht protokolliert ( [!DNL xyz-unlogged.com]). Wenn diese Sites so integriert sind, dass der nahtlose Traffic über die beiden Domänen hinweg erleichtert wird, ist es nicht wünschenswert, bei jedem Wechsel der Besucher von der Domäne [!DNL xyz-unlogged.com] zur Domäne [!DNL xyz.com] eine andere Sitzung zu generieren. Durch die Auflistung von [!DNL xyz-unlogged.com] als interne Domäne wird verhindert, dass Sitzungen aufgrund des Traffics auf diesen beiden Domänen in mehrere Sitzungen aufgeteilt werden, solange die Einstellung Maximale Sitzungsdauer nicht erreicht wird.

**So fügen Sie eine interne Domäne hinzu**

Wenn Sie mit [!DNL Site] arbeiten, enthält Ihre Standardimplementierung eine [!DNL Transformation Dataset Include]-Datei zum Definieren des Parameters &quot;Interne Domänen&quot;. In dieser Datei wird der Parameter benannt. Geben Sie einfach die internen Domänen ein, die Sie einbeziehen möchten, und speichern Sie die aktualisierte Datei.

1. Öffnen Sie [!DNL Profile Manager] in Ihrem Datensatzprofil und navigieren Sie zu [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der der Parameter &quot;Interne Domänen&quot;definiert ist, vom beschriebenen Speicherort unterscheiden.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Value]** für den Vektorparameter &quot;Interne Domänen&quot;und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Bearbeiten Sie die Werte nach Bedarf.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Speichern Sie die Datei [!DNL Internal Domains.cfg], indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und **[!UICONTROL Save]** klicken.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzaufnahme gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.
