---
description: Informationen zu webspezifischen Einstellungen, die in Transformation DataSet definiert sind Schließen Sie Dateien ein, die mit Adobe-Profilen für Site bereitgestellt werden.
solution: Analytics
title: Webspezifische Einstellungen für Transformation
topic: Data workbench
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Webspezifische Einstellungen für Transformation{#web-specific-settings-for-transformation}

Informationen zu webspezifischen Einstellungen, die in Transformation DataSet definiert sind Schließen Sie Dateien ein, die mit Adobe-Profilen für Site bereitgestellt werden.

Die Bedingungen, Dimensionen und Parameter, die durch diese Einstellungen definiert werden, werden während der Umwandlungsphase der Datensatzkonstruktion erstellt.

* [Seitenansichtsbedingung](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [URI-Dimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Referrer-Dimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Sitzungsparameter](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Seitenansichtsbedingung {#section-cc2807a12a88492f8b64a43234a1f835}

Der [!DNL Page View Condition] Bedingungsvorgang bestimmt, ob ein bestimmter Protokolleintrag (d. h. eine Seitenanforderung) in die Daten über den Seitenansichtsverlauf eines Besuchers aufgenommen werden soll. Wenn der Protokolleintrag den Wert [!DNL Page View Condition]erfüllt, wird er ein Element der zählbaren Dimension &quot;Seitenansicht&quot;. Wenn ein Protokolleintrag die Anforderungen nicht erfüllt, [!DNL Page View Condition]sind seine Datenfelder auch für andere Dimensionen zugänglich. Zusätzlich zur Dimension &quot;Seitenansicht&quot;können die Ergebnisse der folgenden Dimensionen beeinflusst werden [!DNL Page View Condition]:

* **[!DNL URI]und[!DNL Page]:**Diese Dimensionen sind direkt von der[!DNL Page View Condition]betroffen. Wenn die angegebene Seite die URL- oder Seitendimensionen nicht übergibt, wird[!DNL Page View Condition,]sie nicht berücksichtigt.

* **[!DNL Visitor Page Views]und[!DNL Session Page Views]:**Die Dimensionen &quot;Seitenansichten des Besuchers&quot;und &quot;Seitenansichten der Sitzung&quot;sind eine Zählung der Anzahl der Seiten, die ein Besucher in einer bestimmten Sitzung bzw. in einer bestimmten Sitzung aufruft. Seiten, die von der Seite herausgefiltert werden,[!DNL Page View Condition]sind nicht Teil dieser Zählung.

* **Sitzung Nr.:** Der [!DNL Page View Condition] Effekt wirkt sich indirekt auf die Dimension &quot;Sitzungsnummer&quot;aus. Die Dimension &quot;Sitzungsnummer&quot;wird vor dem [!DNL Page View Condition]Szenario erstellt. Daher ist es möglich, Sitzungen ohne Seitenansichten zu haben, wenn [!DNL Session Number] in Bezug auf die [!DNL Page Views]Frage nachgedacht wird.

Ihre Standardimplementierung von [!DNL Site] enthält eine [!DNL Transformation Dataset Include] Datei, in der die zählbare Dimension &quot;Seitenansicht&quot;und die zugehörige Dimension definiert [!DNL Page View Condition] sind.

Weitere Informationen zu zählbaren Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**So bearbeiten Sie die Konfigurationseinstellungen für die Seitenansichtsbedingung**

1. Öffnen Sie die Datei [!DNL Profile Manager] im Datenaset-Profil und öffnen Sie die [!DNL Dataset\Transformation\Traffic\Page View.cfg] Datei.

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von angepasst haben, [!DNL Site]kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter der [!DNL Page View Condition] Variablen nach Bedarf. Verwenden Sie das folgende Beispiel als Anleitung. In dieser Datei [!DNL Page View Condition] wird der Wert durch eine [!DNL Copy] Transformation definiert. Beachten Sie, dass diese Datei auch die Definition der zählbaren Dimension &quot;Seitenansicht&quot;enthält.

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Weitere Informationen zu zählbaren Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Informationen zur [!DNL Copy] Transformation finden Sie unter [Datentransformationen](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** am oberen Rand des Fensters klicken und dann auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## URI-Dimension {#section-348f7e9099d049d197a7cdcbc8a6c234}

Wenn Sie mit arbeiten, [!DNL Site]müssen Sie die URI-Dimension definieren, deren Elemente die URI-Stile der angezeigten Webseiten sind. Ihre Standardimplementierung enthält eine [!DNL Transformation Dataset Include] Datei, in der die einfache URI-Dimension definiert ist.

Informationen zu einfachen Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**So bearbeiten Sie die Konfigurationseinstellungen für die URI-Dimension**

1. Öffnen Sie die Datei [!DNL Profile Manager] im Datenaset-Profil und öffnen Sie die [!DNL Dataset\Transformation\Traffic\URI.cfg] Datei.

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von angepasst haben, [!DNL Site]kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter der Datei nach Bedarf. Verwenden Sie das folgende Beispiel und Informationen als Anleitungen.

![](assets/cfg_WebParameters_URI.png)

Die Konfigurationseinstellungen für die URI-Dimension umfassen die folgenden beiden Parameter:

* **Groß-/Kleinschreibung:** True oder false. Wenn &quot;true&quot;, wird die Groß-/Kleinschreibung bei der Identifizierung individueller Seiten berücksichtigt. Der Standardwert ist true.
* **Maximale Elemente:** Die maximale Anzahl von Elementen (d. h. URIs) für die URI-Dimension. Der Standardwert lautet 32768.

   >[!NOTE]
   >
   >Eine Änderung dieses Werts kann zu ernsthaften Leistungsproblemen führen. Ändern Sie diesen Wert nicht ohne Rücksprache mit Adobe.

* Speichern Sie die [!DNL URI.cfg] Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster klicken und dann auf **[!UICONTROL Save]**.

* Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## Referrer-Dimension {#section-8a97ec34d18b4814b5f95495ac4f8638}

Wenn Sie mit arbeiten, müssen Sie [!DNL Site]die Dimension &quot;Referrer&quot;definieren, deren Elemente aus den Domänen der zweiten Ebene der Referrer der ersten Protokolleinträge in allen Sitzungen bestehen. Ihre Standardimplementierung enthält eine [!DNL Transformation Dataset Include] Datei, in der die einfache Dimension &quot;Referrer&quot;definiert ist.

Informationen zu einfachen Dimensionen finden Sie unter [Erweiterte Dimensionen](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**So bearbeiten Sie die Konfigurationseinstellungen für die Dimension &quot;Referrer&quot;**

1. Öffnen Sie die Datei [!DNL Profile Manager] im Datenaset-Profil und öffnen Sie die [!DNL Dataset\Transformation\Traffic\Referrer.cfg] Datei.

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von angepasst haben, [!DNL Site]kann sich die Datei, in der diese Konfigurationseinstellungen vorhanden sind, von dem beschriebenen Speicherort unterscheiden.

1. Überprüfen oder bearbeiten Sie die Werte der Parameter der Datei nach Bedarf. Verwenden Sie das folgende Beispiel und Informationen als Anleitungen.

   ![](assets/cfg_WebParameters_Referrer.png)

   Die Konfigurationseinstellungen für die Dimension &quot;Referrer&quot;enthalten den Parameter &quot;Maximum Elements&quot;, der die maximale Anzahl von Elementen (d. h. verweisende Stellen) für die Dimension &quot;Referrer&quot;angibt. Der Standardwert lautet 32768.

   >[!NOTE]
   >
   >Im obigen Beispiel wird der [!DNL Maximum Elements] Parameter auf 0 gesetzt. Wenn dieser Parameter auf 0 gesetzt ist, verwendet der Data Workbench-Server seinen internen Standardwert 32768.

1. Speichern Sie die [!DNL Referrer.cfg] Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster klicken und dann auf **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

## Sitzungsparameter {#section-0a209b0c504041a5801f7f71a963c8b1}

Wenn Sie mit [!DNL Site]arbeiten, können Sie Parameter angeben, die die Grenzen einer Besuchersitzung auf einer Website definieren. Diese Parameter sind nur gültig, wenn sie in einer [!DNL Transformation Dataset Include] Datei innerhalb Ihrer [!DNL Site] Implementierung definiert sind.

Die folgenden Parameter sind eindeutig, da sie Mitglieder des [!DNL Transformation Dataset Include] Vektor der [!DNL Parameters] Datei sein können oder als einzelne Parameter in der [!DNL Transformation.cfg]Datei aufgeführt werden können. Ein Parameter kann genau einmal definiert werden. Daher werden diese Parameter entweder in der [!DNL Transformation.cfg]Datei oder im [!DNL Parameters] Vektor des Datensatzes einschließlich der Datei definiert - nicht in beiden Dateien.
**Maximale Sitzungsdauer und Sitzungszeitlimit**

Die maximale Sitzungsdauer und der maximale Sitzungszeitlimit sind Zeichenfolgenparameter, die die Länge der Sitzung eines Besuchers definieren. Diese Parameter arbeiten mit dem Parameter &quot;Interne Domänen&quot;, um die Sitzungslänge zu bestimmen.

Die maximale Sitzungsdauer gibt die längste Sitzungsdauer vor dem Starten einer neuen Sitzung an. Dadurch werden Webseiten mit automatischem Inhalt von beliebig langen Sitzungen aktualisiert. Wenn die verweisende Stelle eines Klicks auf einen der Einträge im Parameter &quot;Interne Domänen&quot;gesetzt ist, wird dieser Timeout verwendet, um das Ende einer Sitzung zu definieren. Keine Sitzung darf länger als die angegebene maximale Sitzungsdauer sein, unabhängig davon, wie viele Klicks sie enthält. Der empfohlene Wert beträgt 48 Stunden.

Sitzungs-Timeout gibt die Zeit an, die zwischen den Protokolleinträgen eines Besuchers verstreichen muss, um das Ende einer Sitzung und den Beginn einer neuen Sitzung zu bestimmen (d. h. den typischen Timeout, mit dem eine Benutzersitzung definiert wird). Der empfohlene Wert dieses Parameters beträgt 30 Minuten. Wenn die verweisende Stelle eines Klicks im Parameter &quot;Interne Domänen&quot;nicht auf eine der verweisenden Stellen festgelegt ist, wird diese Zeitüberschreitung zur Definition der Sitzung verwendet. Wenn sich cs(referrer-domain) für einen Protokolleintrag in der Liste der internen Domänen befindet, bestimmt die maximale Sitzungsdauer, ob der aktuelle Protokolleintrag Teil einer vorhandenen Sitzung oder der Beginn einer neuen Sitzung ist.

Betrachten Sie eine Situation, in der ein Besucher während des Durchsuchens der Site für einen Zeitraum, der länger als das Sitzungs-Timeout ist, von seinem Computer weg angerufen wird. Nach seiner Rückkehr surft er weiter, wo er aufgehört hat. Da der Besucher die Site nie verlässt oder seinen Browser schließt, ist die cs(referrer-domain) des nächsten Klick die gleiche wie die interne Domäne und seine ursprüngliche Sitzung bleibt aktiv, solange die Einstellung für die maximale Sitzungsdauer nicht erreicht wird. Wenn die Domäne der Site als interne Domäne aufgelistet ist und der maximale Timeout nicht erreicht wird, wird die Benutzerinteraktion als einzelne Sitzung und nicht als zwei separate Sitzungen angezeigt. Wenn der Besucher jedoch zu seinem Computer zurückkehrt und bei seinem nächsten Klick eine externe (oder leere) verweisende Stelle vorhanden ist, beginnt eine neue Sitzung.

>[!NOTE]
>
>Die [!DNL Sessionize] Transformation spielt [!DNL Timeout Condition] auch eine Rolle bei der Bestimmung der Dauer einer Besuchersitzung. Wenn Sitzungszeitlimit und maximale Sitzungsdauer nicht angewendet werden, [!DNL Timeout Condition] wird überprüft, ob ein Protokolleintrag als Beginn einer neuen Sitzung betrachtet werden soll. For more information, see [Data Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**So bearbeiten Sie die Parameter für die maximale Sitzungsdauer und das maximale Sitzungszeitlimit**

Wenn Sie mit [!DNL Site]arbeiten, enthält Ihre Standardimplementierung wahrscheinlich eine [!DNL Transformation Dataset Include] Datei, in der die Namen und empfohlenen Werte dieser Parameter angegeben werden.

1. Öffnen Sie die Datei [!DNL Profile Manager] in Ihrem DataSet-Profil und gehen Sie zu [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von angepasst haben, [!DNL Site]kann sich die Datei, in der diese Parameter definiert sind, von dem beschriebenen Speicherort unterscheiden.

1. Bearbeiten Sie die Werte der Parameter nach Wunsch. Stellen Sie sicher, dass Sie die gewünschten Einheiten (Minuten, Stunden usw.) angeben.

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Speichern Sie die [!DNL Session Parameters.cfg] Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster auf klicken **[!UICONTROL Save]**.

1. Damit die lokal vorgenommenen Änderungen wirksam werden, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > **[!UICONTROL profile name]**. Dabei steht der Profilname für den Namen des Datensatzprofils oder des geerbten Profils, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

**[!DNL Internal Domains]**

[!DNL Internal Domains] ist ein Vektorparameter, der Hosts auf Domänenebene (interne Referrer) auflistet, die als Teil einer bestimmten Website behandelt werden sollten. Diese Hosts werden aus der Dimension der verweisenden Stelle entfernt (bei der es sich um eine Liste der Informationen der externen verweisenden Stelle handelt). Wenn cs(referrer-domain) mit einer der im Satz der internen Domänen aufgelisteten Zeichenfolgen übereinstimmt, wird das Sitzungszeitlimit ignoriert und die maximale Sitzungsdauer wird zur Bestimmung der Sitzungslänge verwendet.

Der Parameter &quot;Interne Domänen&quot;kann auch verwendet werden, um den Start einer neuen Sitzung zu verhindern, wenn Besucher zu mehreren Domänen eines Unternehmens wechseln, die in einer Weise zugeordnet sind, die den Sitzungs-Timeout überschreitet. Angenommen, ein Unternehmen hat Teile seiner Website auf zwei Domänen aufgeteilt: einer wird protokolliert ( [!DNL xyz.com]), der andere nicht protokolliert ( [!DNL xyz-unlogged.com]). Wenn diese Sites so integriert sind, dass der Traffic nahtlos über die beiden Domänen hinweg bewegt werden kann, ist es nicht wünschenswert, bei jedem Wechsel des Besuchers von der [!DNL xyz-unlogged.com] Domäne zurück zur [!DNL xyz.com] Domäne eine andere Sitzung zu generieren. Durch die [!DNL xyz-unlogged.com] Aufnahme als interne Domäne wird verhindert, dass Sitzungen aufgrund des Traffics über diese beiden Domänen in mehrere Sitzungen aufgeteilt werden, solange die Einstellung &quot;Maximale Sitzungsdauer&quot;nicht erreicht wird.

**So fügen Sie eine interne Domäne hinzu**

Wenn Sie mit [!DNL Site]arbeiten, enthält Ihre Standardimplementierung eine [!DNL Transformation Dataset Include] Datei zum Definieren des Parameters &quot;Interne Domänen&quot;. In dieser Datei wird der Parameter benannt. Geben Sie einfach die internen Domänen ein, die Sie einbeziehen möchten, und speichern Sie die aktualisierte Datei.

1. Öffnen Sie die [!DNL Profile Manager] Datei im Datenaset-Profil und gehen Sie zu [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Wenn Sie Ihre Implementierung von angepasst haben, [!DNL Site]kann sich die Datei, in der der Parameter &quot;Interne Domänen&quot;definiert ist, vom beschriebenen Speicherort unterscheiden.

1. Klicken Sie mit der rechten Maustaste **[!UICONTROL Value]** auf den Vektorparameter &quot;Interne Domänen&quot;und klicken Sie auf **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Bearbeiten Sie die Werte wie gewünscht.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Speichern Sie die [!DNL Internal Domains.cfg] Datei, indem Sie mit der rechten Maustaste **[!UICONTROL (modified)]** oben im Fenster auf klicken **[!UICONTROL Save]**.

1. Um die lokal vorgenommenen Änderungen in Kraft zu setzen, klicken Sie mit der [!DNL Profile Manager]rechten Maustaste auf das Häkchen für die Datei in der [!DNL User] Spalte und klicken Sie dann auf **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, wobei der Profilname der Name des Datensatzprofils oder das geerbte Profil ist, zu dem die Datensatzdatei gehört.

   >[!NOTE]
   >
   >Speichern Sie die geänderte Konfigurationsdatei nicht in einem der von Adobe bereitgestellten internen Profile, da Ihre Änderungen bei der Installation von Updates für diese Profile überschrieben werden.

