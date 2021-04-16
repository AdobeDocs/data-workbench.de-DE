---
description: Informationen zu webspezifischen Einstellungen, die in Transformation DataSet definiert sind Schließen Sie Dateien ein, die mit Adobe-Profilen für Site bereitgestellt werden.
title: Web-spezifische Einstellungen für Umwandlungen
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 1%

---

# Web-spezifische Einstellungen für Umwandlungen{#web-specific-settings-for-transformation}

Informationen zu webspezifischen Einstellungen, die in Transformation DataSet definiert sind Schließen Sie Dateien ein, die mit Adobe-Profilen für Site bereitgestellt werden.

Die Bedingungen, Dimensionen und Parameter, die durch diese Einstellungen definiert werden, werden während der Umwandlungsphase der Datensatzkonstruktion erstellt.

* [Seitenansicht-Bedingung](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [URI-Dimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Werber Dimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Sitzungsparameter](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Seitenansicht-Bedingung {#section-cc2807a12a88492f8b64a43234a1f835}

Das [!DNL Page View Condition] ist ein Bedingungsvorgang, der bestimmt, ob ein bestimmter Protokolleintrag (d. h. eine Seitenanforderung) in die Daten zum Seitenverlauf eines Besuchers aufgenommen werden soll. Wenn der Protokolleintrag den Wert [!DNL Page View Condition] erfüllt, wird er zu einem Element der zählbaren Dimension &quot;Ansicht&quot;. Wenn ein Protokolleintrag den Wert [!DNL Page View Condition] nicht erfüllt, sind seine Datenfelder auch für andere Dimensionen zugänglich. Zusätzlich zur Dimension &quot;Ansicht der Seite&quot;können die folgenden Dimensionen durch die Ergebnisse von [!DNL Page View Condition] beeinflusst werden:

* **[!DNL URI]und  [!DNL Page]:** Diese Dimensionen sind direkt von der  [!DNL Page View Condition]betroffen. Wenn die angegebene Seite das [!DNL Page View Condition,] nicht übergibt, wird sie nicht in die URI- oder Seitendimensionen einbezogen.

* **[!DNL Visitor Page Views]und  [!DNL Session Page Views]:** Die Dimensionen &quot;Ansichten der Besucher-Seite&quot;und &quot;Ansichten der Sitzungsseite&quot;stellen die Anzahl der Seiten dar, die ein Besucher zu bzw. in einer bestimmten Sitzung anzeigt. Seiten, die von [!DNL Page View Condition] herausgefiltert werden, sind nicht Teil dieser Zählung.

* **Sitzung Nr.:** Die Dimension &quot;Sitzungsnummer&quot; [!DNL Page View Condition] hat indirekte Auswirkungen. Die Dimension &quot;Sitzungsnummer&quot;wird vor dem [!DNL Page View Condition] erstellt. Daher ist es möglich, dass bei der Betrachtung von [!DNL Session Number] in Bezug auf [!DNL Page Views] Sitzungen ohne Ansichten der Seite stattfinden.

Ihre Standardimplementierung von [!DNL Site] enthält eine [!DNL Transformation Dataset Include]-Ansicht, in der die zählbare Dimension und die zugehörige [!DNL Page View Condition] definiert sind.

Weitere Informationen zu zählbaren Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**So bearbeiten Sie die Konfigurationseinstellungen für die Seitenbedingung &quot;Ansicht&quot;**

1. Öffnen Sie die Datei [!DNL Profile Manager] in Ihrem DataSet-Profil und öffnen Sie die Datei [!DNL Dataset\Transformation\Traffic\Page View.cfg].

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter von [!DNL Page View Condition] nach Bedarf. Verwenden Sie das folgende Beispiel als Anleitung. In dieser Datei wird [!DNL Page View Condition] durch eine [!DNL Copy]-Transformation definiert. Beachten Sie, dass diese Ansicht auch die zählbare Dimension der Seite enthält.

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Weitere Informationen zu zählbaren Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Informationen zur [!DNL Copy]-Transformation finden Sie unter [Datentransformationen](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und dann auf **[!UICONTROL Save]** klicken.

1. Um die lokal vorgenommenen Änderungen zu übernehmen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei Profil der Name des Datensatzes oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil, da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.

## URI-Dimension {#section-348f7e9099d049d197a7cdcbc8a6c234}

Wenn Sie mit [!DNL Site] arbeiten, müssen Sie die URI-Dimension definieren, deren Elemente die URI-Stile der angezeigten Webseiten sind. Ihre Standardimplementierung enthält eine [!DNL Transformation Dataset Include]-Datei, in der die einfache URI-Dimension definiert ist.

Informationen zu einfachen Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**So bearbeiten Sie die Konfigurationseinstellungen für die URI-Dimension**

1. Öffnen Sie die Datei [!DNL Profile Manager] in Ihrem DataSet-Profil und öffnen Sie die Datei [!DNL Dataset\Transformation\Traffic\URI.cfg].

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter der Datei nach Bedarf. Verwenden Sie das folgende Beispiel und Informationen als Anleitungen.

![](assets/cfg_WebParameters_URI.png)

Die Konfigurationseinstellungen für die URI-Dimension umfassen die folgenden beiden Parameter:

* **Groß-/Kleinschreibung beachten:** True oder false. Wenn &quot;true&quot;, wird die Groß-/Kleinschreibung bei der Identifizierung individueller Seiten berücksichtigt. Der Standardwert ist true.
* **Maximale Elemente:** Die maximale Anzahl von Elementen (d. h. URIs) für die URI-Dimension. Der Standardwert lautet 32768.

   >[!NOTE]
   >
   >Eine Änderung dieses Werts kann zu ernsthaften Leistungsproblemen führen. Ändern Sie diesen Wert nicht ohne vorherige Adobe.

* Speichern Sie die Datei [!DNL URI.cfg], indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und dann auf **[!UICONTROL Save]** klicken.

* Um die lokal vorgenommenen Änderungen zu übernehmen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei Profil der Name des Datensatzes oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil, da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.

## Werber-Dimension {#section-8a97ec34d18b4814b5f95495ac4f8638}

Wenn Sie mit [!DNL Site] arbeiten, müssen Sie die Dimension &quot;Werber&quot;definieren, deren Elemente aus den Domänen der zweiten Ebene des Werbers der ersten Protokolleinträge in allen Sitzungen bestehen. Ihre Standardimplementierung enthält eine [!DNL Transformation Dataset Include]-Datei, in der die Dimension &quot;Werber&quot; definiert ist.

Informationen zu einfachen Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**So bearbeiten Sie die Konfigurationseinstellungen für die Dimension &quot;Werber&quot;**

1. Öffnen Sie die Datei [!DNL Profile Manager] in Ihrem DataSet-Profil und öffnen Sie die Datei [!DNL Dataset\Transformation\Traffic\Referrer.cfg].

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter der Datei nach Bedarf. Verwenden Sie das folgende Beispiel und Informationen als Anleitungen.

   ![](assets/cfg_WebParameters_Referrer.png)

   Die Konfigurationseinstellungen für die Dimension &quot;Werber&quot;enthalten den Parameter &quot;Maximale Elemente&quot;, der die maximale Elementanzahl (d. h. die maximale Elementanzahl) für die Dimension &quot;Werber&quot;angibt. Der Standardwert lautet 32768.

   >[!NOTE]
   >
   >Im obigen Beispiel ist der Parameter [!DNL Maximum Elements] auf 0 gesetzt. Wenn dieser Parameter auf 0 gesetzt ist, verwendet der Data Workbench-Server seinen internen Standardwert 32768.

1. Speichern Sie die Datei [!DNL Referrer.cfg], indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und dann auf **[!UICONTROL Save]** klicken.

1. Um die lokal vorgenommenen Änderungen zu übernehmen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei Profil der Name des Datensatzes oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil, da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.

## Sitzungsparameter {#section-0a209b0c504041a5801f7f71a963c8b1}

Wenn Sie mit [!DNL Site] arbeiten, können Sie Parameter angeben, die die Sitzungsgrenzen eines Besuchers auf einer Website definieren. Diese Parameter sind nur gültig, wenn sie in einer [!DNL Transformation Dataset Include]-Datei innerhalb Ihrer [!DNL Site]-Implementierung definiert sind.

Die folgenden Parameter sind eindeutig, da sie Mitglieder des [!DNL Transformation Dataset Include]-Vektors der Datei [!DNL Parameters] sein können oder als einzelne Parameter in der Datei [!DNL Transformation.cfg]aufgeführt werden können. Ein Parameter kann genau einmal definiert werden. Daher werden diese Parameter entweder in der Datei [!DNL Transformation.cfg]oder im Vektor [!DNL Parameters] des Datensatzes enthalten - nicht in beiden Dateien.
**Maximale Sitzungsdauer und Sitzungszeitlimit**

Die maximale Sitzungsdauer und der maximale Sitzungszeitlimit sind Zeichenfolgenparameter, die die Dauer der Sitzung eines Besuchers definieren. Diese Parameter arbeiten mit dem Parameter &quot;Interne Domänen&quot;, um die Sitzungslänge zu bestimmen.

Die maximale Sitzungsdauer gibt die längste Sitzungsdauer vor dem Starten einer neuen Sitzung an. Dadurch werden Webseiten mit automatischem Inhalt von beliebig langen Sitzungen aktualisiert. Wenn der Werber eines Klicks auf einen der Einträge im Parameter &quot;Interne Domänen&quot;festgelegt ist, wird dieser Timeout verwendet, um das Ende einer Sitzung zu definieren. Keine Sitzung darf länger als die angegebene maximale Sitzungsdauer sein, unabhängig davon, wie viele Klicks sie enthält. Der empfohlene Wert beträgt 48 Stunden.

Sitzungs-Timeout gibt an, wie viel Zeit zwischen den Protokolleinträgen eines bestimmten Besuchers verstreichen muss, um das Ende einer Sitzung und den Beginn einer neuen Sitzung zu bestimmen (d. h. der typische Timeout, mit dem eine Benutzersitzung definiert wird). Der empfohlene Wert dieses Parameters beträgt 30 Minuten. Wenn der Werber eines Klicks im Parameter &quot;Interne Domänen&quot;nicht auf einen der Werber festgelegt ist, wird dieser Timeout zur Definition der Sitzung verwendet. Wenn sich cs(Werber-Domäne) für einen Protokolleintrag in der Liste interner Domänen befindet, bestimmt die maximale Sitzungsdauer, ob der aktuelle Protokolleintrag Teil einer vorhandenen Sitzung oder der Beginn einer neuen Sitzung ist.

Betrachten Sie eine Situation, in der ein Besucher für einen Zeitraum, der länger als das Sitzungs-Timeout ist, von seinem Computer weg angerufen wird, während er sich mitten auf der Site befindet. Nach seiner Rückkehr surft er weiter, wo er aufgehört hat. Da der Besucher die Site nie verlässt oder seinen Browser schließt, ist die cs(Werber-Domäne) seines nächsten Klick die gleiche wie die interne Domäne und seine ursprüngliche Sitzung bleibt aktiv, solange die Einstellung für die maximale Sitzungsdauer nicht erreicht wird. Wenn die Domäne der Site als interne Domäne aufgelistet ist und der maximale Timeout-Wert nicht erreicht wird, wird die Interaktion des Besuchers als eine Sitzung und nicht als zwei separate Sitzungen angezeigt. Wenn der Besucher jedoch zu seinem Computer zurückkehrt und der nächste Klick einen externen (oder leeren) Werber aufweist, beginnt eine neue Sitzung.

>[!NOTE]
>
>Das [!DNL Sessionize]-Konvertierungsprogramm [!DNL Timeout Condition] spielt auch eine Rolle bei der Bestimmung der Sitzungslänge eines Besuchers. Wenn Sitzungs-Timeout und maximale Sitzungsdauer nicht angewendet werden, wird das [!DNL Timeout Condition] überprüft, um zu bestimmen, ob ein Protokolleintrag als Beginn einer neuen Sitzung betrachtet werden soll. Weitere Informationen finden Sie unter [Datentransformationen](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**So bearbeiten Sie die Parameter für die maximale Sitzungsdauer und das maximale Sitzungszeitlimit**

Wenn Sie mit [!DNL Site] arbeiten, enthält Ihre Standardimplementierung wahrscheinlich eine [!DNL Transformation Dataset Include]-Datei, in der die Namen und empfohlenen Werte dieser Parameter angegeben werden.

1. Öffnen Sie das [!DNL Profile Manager] in Ihrem DataSet-Profil und gehen Sie zu [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der diese Parameter definiert werden, von dem beschriebenen Speicherort unterscheiden.

1. Bearbeiten Sie die Werte der Parameter nach Wunsch. Stellen Sie sicher, dass Sie die gewünschten Einheiten (Minuten, Stunden usw.) angeben.

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Speichern Sie die Datei [!DNL Session Parameters.cfg], indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und auf **[!UICONTROL Save]** klicken.

1. Um die lokal vorgenommenen Änderungen zu übernehmen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, wobei Profil der Name des Datensatzes oder das geerbte Profil ist, zu dem die Datensatzeinschlussdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil, da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.

**[!DNL Internal Domains]**

[!DNL Internal Domains] ist ein Vektorparameter, der Hosts auf Domänenebene (interne Werber) Liste, die als Teil einer bestimmten Website behandelt werden sollten. Diese Hosts werden aus der Dimension &quot;Werber&quot;entfernt (was eine Liste der Informationen zu externen Werbern ist). Wenn cs(Werber-domain) mit einer der im Satz der internen Domänen aufgelisteten Zeichenfolgen übereinstimmt, wird das Sitzungszeitlimit ignoriert und die maximale Sitzungsdauer wird zur Bestimmung der Sitzungslänge verwendet.

Der Parameter &quot;Interne Domänen&quot;kann auch verwendet werden, um den Beginn einer neuen Sitzung zu verhindern, wenn Besucher zwischen mehreren Domänen einer Firma wechseln, die in einer Weise zugeordnet sind, die den Sitzungs-Timeout überschreitet. Betrachten Sie beispielsweise eine Firma, deren Sitebereiche auf zwei Domänen aufgeteilt sind: einer wird protokolliert ( [!DNL xyz.com]), der andere nicht protokolliert ( [!DNL xyz-unlogged.com]). Wenn diese Sites so integriert sind, dass der Traffic nahtlos über die beiden Domänen verläuft, ist es nicht wünschenswert, bei jedem Wechsel des Besuchers von der Domäne [!DNL xyz-unlogged.com] zurück zur Domäne [!DNL xyz.com] eine andere Sitzung zu generieren. Durch Auflisten von [!DNL xyz-unlogged.com] als interne Domäne wird verhindert, dass Sitzungen aufgrund des Traffics über diese beiden Domänen in mehrere Sitzungen aufgeteilt werden, solange die Einstellung &quot;Maximale Sitzungsdauer&quot;nicht erreicht wird.

**So fügen Sie eine interne Domäne hinzu**

Wenn Sie mit [!DNL Site] arbeiten, enthält Ihre Standardimplementierung eine [!DNL Transformation Dataset Include]-Datei zum Definieren des Parameters &quot;Interne Domänen&quot;. In dieser Datei wird der Parameter benannt. Geben Sie einfach die internen Domänen ein, die Sie einbeziehen möchten, und speichern Sie die aktualisierte Datei.

1. Öffnen Sie das [!DNL Profile Manager] in Ihrem DataSet-Profil und gehen Sie zu [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von [!DNL Site] angepasst haben, kann sich die Datei, in der der Parameter &quot;Interne Domänen&quot;definiert ist, von dem beschriebenen Speicherort unterscheiden.

1. Klicken Sie mit der rechten Maustaste auf **[!UICONTROL Value]** für den Vektor-Parameter &quot;Interne Domänen&quot;und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Bearbeiten Sie die Werte wie gewünscht.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Speichern Sie die Datei [!DNL Internal Domains.cfg], indem Sie mit der rechten Maustaste auf **[!UICONTROL (modified)]** oben im Fenster klicken und auf **[!UICONTROL Save]** klicken.

1. Um die lokal vorgenommenen Änderungen zu übernehmen, klicken Sie in der Spalte [!DNL Profile Manager] mit der rechten Maustaste auf das Häkchen für die Datei in der Spalte [!DNL User] und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, wobei Profil der Name des Datensatzes oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von der Adobe bereitgestellten internen Profil, da Ihre Änderungen bei der Installation von Updates auf diesen Profilen überschrieben werden.
