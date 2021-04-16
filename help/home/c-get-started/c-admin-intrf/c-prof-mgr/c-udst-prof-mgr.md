---
description: Die Ordner- und Dateinamen in Ihrer Implementierung werden links im Profil Manager angezeigt.
title: Profil-Manager
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# Profil-Manager{#profile-manager}

Die Ordner- und Dateinamen in Ihrer Implementierung werden links im Profil Manager angezeigt.

Die Profil, aus denen Ihre Anwendung besteht, werden als die einzelnen Spalten im [!DNL Profile Manager] angezeigt. Zu diesen Profilen gehören mehrere geerbte Profil und ein einziges funktionierendes Profil.

>[!NOTE]
>
>Ihr arbeitendes Profil (entweder ein DataSet-Profil oder ein rollenspezifisches Profil) ist das Profil, das Sie beim Öffnen der Data Workbench laden.

Die Häkchen (und ihre Farben) geben den bzw. die Profil-Ordner auf dem Data Workbench- und Data Workbench-Server an, auf dem sich die einzelnen Dateien befinden, ob mehrere Exemplare einer  vorhanden sind und ob diese Mehrfachkopien dasselbe Datum und dieselbe Uhrzeit haben. Diese Dateien werden während des Herunterladens des Profils zwischen dem Data Workbench- und dem Data Workbench-Computer synchronisiert.

Im Folgenden finden Sie ein Beispiel [!DNL Profile Manager] für eine HBX Implementierung:

![](assets/client-prof.png)

Im Menü [!DNL Profile Manager] können Sie alle anderen Manager öffnen (z. B. [!DNL Dimensions Manager] oder [!DNL Reports Manager]), die nur bestimmte Teile von [!DNL Profile Manager] anzeigen. Sie können auch neue Profil-Manager erstellen. Siehe [Erstellen neuer Profil-Manager](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

Ein Häkchen neben dem Dateinamen in einer bestimmten Spalte zeigt an, dass sich eine Datei mit diesem Namen in dem in dieser Spalte (Profil) angegebenen Ordner befindet. Wenn Sie nach rechts in [!DNL Profile Manager] wechseln, haben die Dateien Vorrang vor den Dateien links, d. h. jedes geerbte Profil baut auf den Profilen links im [!DNL Profile Manager] auf. Wenn Sie beispielsweise eine Datei mit demselben Namen und demselben Speicherort im Profil [!DNL Base] (Spalte) und im Profil [!DNL User] (Spalte) haben, wird die Datei im Profil [!DNL User] anstelle der Datei im Profil [!DNL Base] verwendet.

## Suchen nach Profilen {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

In Data Workbench 5.5 wurde ein Suchfeld hinzugefügt, um die erforderlichen Profil im [!DNL Profile Manager] zu finden.

![](assets/client-prof2.png)

Die folgenden Arten von Spalten werden im [!DNL Profile Manager] angezeigt:

* Die Spalten *Vererbter Profil* enthalten Häkchen für Dateien, die sich in den einzelnen Profil-Ordnern befinden. Zu den geerbten Profilen zählen interne Profil, die von der Adobe bereitgestellt werden, sowie alle Firmen- oder rollenspezifischen Profil, die Sie erstellen und verwalten. Im obigen Beispiel umfassen die internen Profil Base, Traffic, Value, Marketing usw. Das interne [!DNL Base]-Profil, das die grundlegenden Bausteine und Konfigurationsinformationen enthält, die zum Ausführen der Adobe erforderlich sind, wird bei jeder Implementierung bereitgestellt. Die anderen internen Profil enthalten Elemente (Arbeitsbereiche, Metriken, abgeleitete Dimensionen usw.), die sich auf bestimmte Arten von Informationen beziehen, wie Webverkehr oder Marketing. Adobe bietet nur die Profil, die für die Art der Daten, die Sie analysieren, und für Ihre Branche geeignet sind.

   >[!NOTE]
   >
   >Interne Profil (die durch Adobe bereitgestellt werden) können standardmäßig nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden. Wenn Sie eine neue Anwendung erstellen und ein internes Profil ändern müssen, müssen Sie den Parameter &quot;Interne Profil ändern&quot;in der Datei [!DNL Insight.cfg] ändern. Weitere Informationen finden Sie unter [Insight-Konfigurationsparameter](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b). Wenden Sie sich zuerst an Adobe Consulting Services.

* Die Spalte *Name des funktionierenden Profils*, die immer die letzte Spalte ist, enthält Häkchen für Dateien, die sich im Ordner des aktuellen Profils befinden. Im obigen Beispiel lautet das funktionierende Profil DataSet. Ihr arbeitendes Profil ist entweder ein DataSet-Profil oder ein rollenspezifisches Profil. Die Dateien in diesem Ordner haben Vorrang vor allen Dateien mit denselben Namen in allen geerbten Profilen.
* Die Spalte [!DNL User], bei der es sich immer um die letzte Spalte handelt, enthält Häkchen für Dateien und Ordner, die sich im Ordner &quot;User\*Profil name*&quot;als lokale Dateien befinden. Die Ordnerstruktur des Benutzerordners entspricht der des funktionierenden Profils. Jeder User\*Profil name*-Ordner enthält lokale Kopien der Arbeitsbereiche, Metriken, Dimensionen und Konfigurationsdateien für das jeweilige Profil. Diese lokalen Kopien haben Vorrang vor allen Dateien mit denselben Namen in allen geerbten oder funktionierenden Profilen. Die Dateien in der Spalte [!DNL User] wurden entweder erstellt und nur im Ordner &quot;User\*Profil name*&quot;gespeichert oder befinden sich in einem internen oder funktionierenden Profil sowie im Ordner &quot;User\*Profil*&quot;. Die Dateien in jedem Ordner können identisch sein oder nicht identisch sein und können dasselbe Datum und dieselbe Uhrzeit haben.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Um zu vermeiden, dass der Datensatz nur lokal geändert wird, ignoriert der Data Workbench-Server die lokalen Kopien der [!DNL profile.cfg]-Datei sowie alle Dateien im Dataset- oder Exportordner im Ordner &quot;User\*Profil name*&quot;. Ignorierte Dateien werden durch einen roten Hintergrund in der Spalte [!DNL User] und eine Warnung &quot;Im Benutzerverzeichnis ignoriert&quot; im Kontextmenü identifiziert. Um die Änderungen zu implementieren, die Sie an den lokalen Kopien dieser Dateien vornehmen, müssen Sie sie in Ihrem Profil speichern, damit sie mit dem Data Workbenchs-Server synchronisiert werden können. Eine Anleitung zum Speichern von Dateien in Ihrem Profil finden Sie unter [Veröffentlichen von Dateien in Ihrem Profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
      >    
      >    
   * Ein Bindestrich (-) anstelle eines Häkchens in einer Spalte kennzeichnet eine leere Datei (0-Byte-Datei). Data Workbench behandelt Nullbyte-Dateien als nicht vorhanden, was Ihnen ermöglicht, sie zum Ausblenden von Dateien zu verwenden, die in einem Profil auf der linken Seite enthalten sind. Siehe [Ausblenden von Dateien mit leeren (Null-Byte-)Dateien](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## Bestimmen Sie die Dateiversionen {#section-225d732246b94cbe87acdfa9c881d6af}

Wie im vorherigen Abschnitt erwähnt, sind die Häkchen im [!DNL Profile Manager] farbkodiert, sodass Sie leicht erkennen können, wo sich eine Datei befindet und ob die Mehrfachkopien einer Datei zu unterschiedlichen Zeiten verändert wurden.

Wenn eine Datei oder ein reduzierter Ordner genau mit der Datei oder dem Verzeichnis auf der linken Seite identisch ist, hat sie dasselbe Farbkontrollzeichen wie die Datei oder das Verzeichnis in dieser Spalte (Profil). Wenn es sich von einer Datei oder einem Verzeichnis auf der linken Seite unterscheidet oder die Datei oder das Verzeichnis nur in der Spalte [!DNL User] vorhanden ist, ist das Häkchen weiß.

![](assets/vis_ProfMgr_LocalFiles.png)

Das im obigen Beispiel dargestellte [!DNL Profile Manager]-Zeichen bedeutet Folgendes:

* Ein weißes Häkchen für die Datei [!DNL A New Metric.metric] wird nur in der Spalte [!DNL User] angezeigt. Dies weist darauf hin, dass Sie nur über eine lokale Kopie dieser Datei verfügen. Die Datei wurde nicht veröffentlicht (oder hochgeladen), damit andere Data Workbenchs darauf zugreifen können.

* Häkchen für den Dateinamen [!DNL Average Score.metric] werden in den Spalten &quot;Filme&quot;und [!DNL User] angezeigt. Das Häkchen in der Spalte [!DNL User] ist dieselbe Farbe wie das Häkchen in der Spalte &quot;Filme&quot;. Dies weist darauf hin, dass die lokale Kopie der Datei dasselbe Datum und dieselbe Uhrzeit wie die Datei im Ordner &quot;Filme&quot;hat.

* Häkchen für den Dateinamen [!DNL Average Score Error.metric] werden in den Spalten &quot;Filme&quot;und [!DNL User] angezeigt. Das Häkchen in der Spalte [!DNL User] ist weiß. Dies weist darauf hin, dass die lokale Kopie der Datei ein anderes Datum oder eine andere Uhrzeit hat als die Datei im Ordner &quot;Filme&quot;.

