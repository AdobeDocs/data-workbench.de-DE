---
description: Die Ordner- und Dateinamen, die in Ihrer Implementierung enthalten sind, werden links im Profil-Manager angezeigt.
title: Profil-Manager
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# Profil-Manager{#profile-manager}

Die Ordner- und Dateinamen, die in Ihrer Implementierung enthalten sind, werden links im Profil-Manager angezeigt.

Die Profile, aus denen Ihre Anwendung besteht, werden als einzelne Spalten im [!DNL Profile Manager] angezeigt. Diese Profile umfassen mehrere vererbte Profile und ein einziges Arbeitsprofil.

>[!NOTE]
>
>Ihr Arbeitsprofil (entweder ein Datensatzprofil oder ein rollenspezifisches Profil) ist das Profil, das Sie beim Öffnen der Data Workbench laden.

Die Häkchen (und ihre Farben) geben an, in welchen Profilordnern sich der Data Workbench-Server und die Dateicomputer befinden, auf denen sich die Data Workbench befindet, ob mehrere Exemplare einer Datei vorhanden sind und ob diese Mehrfachkopien dasselbe Änderungsdatum und dieselbe Änderungszeit aufweisen. Diese Dateien werden während des Profildownloads zwischen dem Data Workbench-Server und den Data Workbench-Computern synchronisiert.

Im Folgenden finden Sie ein Beispiel [!DNL Profile Manager] für eine HBX Implementierung:

![](assets/client-prof.png)

Über das Menü [!DNL Profile Manager] können Sie alle anderen Manager öffnen (z. B. [!DNL Dimensions Manager] oder [!DNL Reports Manager]), die nur bestimmte Bereiche von [!DNL Profile Manager] anzeigen. Sie können auch neue Profil-Manager erstellen. Siehe [Erstellen neuer Profil-Manager](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

Ein Häkchen neben einem Dateinamen in einer bestimmten Spalte zeigt an, dass sich eine Datei mit diesem Namen in dem Ordner befindet, der in dieser Spalte (Profil) heißt. Wenn Sie nach rechts in [!DNL Profile Manager] wechseln, haben die Dateien Vorrang vor den Dateien links, d. h. jedes geerbte Profil basiert auf den Profilen, die links im [!DNL Profile Manager] stehen. Wenn Sie beispielsweise eine Datei mit demselben Namen und demselben Speicherort im Profil [!DNL Base] (Spalte) und im Profil [!DNL User] (Spalte) haben, wird die Datei im Profil [!DNL User] anstelle der Datei im Profil [!DNL Base] verwendet.

## Suchen nach Profilen {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

In Data Workbench 5.5 wurde ein Suchfeld hinzugefügt, um die erforderlichen Profile in der [!DNL Profile Manager] zu finden.

![](assets/client-prof2.png)

Die folgenden Spaltentypen werden im [!DNL Profile Manager] angezeigt:

* Die Spalten *Vererbter Profilname* enthalten Häkchen für Dateien, die sich in jedem Profilordner befinden. Zu den geerbten Profilen gehören von Adobe bereitgestellte interne Profile sowie firmenspezifische oder rollenspezifische Profile, die Sie erstellen und verwalten. Im obigen Beispiel umfassen die internen Profile Base, Traffic, Value, Marketing usw. Das interne [!DNL Base]-Profil, das die grundlegenden Bausteine und Konfigurationsinformationen enthält, die zum Ausführen Ihrer Adobe App erforderlich sind, wird bei jeder Implementierung bereitgestellt. Die anderen internen Profile enthalten Elemente (Arbeitsbereiche, Metriken, abgeleitete Dimensionen usw.), die sich auf bestimmte Arten von Informationen beziehen, wie z. B. Web-Traffic oder Marketing. Adobe stellt nur die Profile bereit, die für den Datentyp, den Sie analysieren, und für Ihre Branche geeignet sind.

   >[!NOTE]
   >
   >Interne Profile (die von Adobe bereitgestellt werden) können standardmäßig nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz oder in rollenspezifischen Profilen oder anderen von Ihnen erstellten Profilen vorgenommen werden. Wenn Sie eine neue Anwendung erstellen und ein internes Profil ändern müssen, müssen Sie den Parameter &quot;Modify Internal Profiles&quot;in der Datei [!DNL Insight.cfg] ändern. Weitere Informationen finden Sie unter [Insight-Konfigurationsparameter](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) . Wenden Sie sich zunächst an Adobe Consulting Services.

* Die Spalte *Name des Arbeitsprofils*, die immer die letzte Spalte ist, enthält Häkchen für Dateien, die sich im Ordner des aktuellen Arbeitsprofils befinden. Im obigen Beispiel lautet das Arbeitsprofil Datensatz. Ihr Arbeitsprofil ist entweder ein Datensatzprofil oder ein rollenspezifisches Profil. Die Dateien in diesem Ordner haben Vorrang vor allen Dateien mit denselben Namen in einem geerbten Profilordner.
* Die Spalte [!DNL User], die immer die letzte Spalte ist, enthält Häkchen für Dateien und Ordner, die sich im Ordner &quot;User\*Profilname*&quot;als lokale Dateien befinden. Die Verzeichnisstruktur des Benutzerordners entspricht der des Arbeitsprofils. Jeder Ordner &quot;User\*profile name*&quot;enthält lokale Kopien der Arbeitsbereiche, Metriken, Dimensionen und Konfigurationsdateien für dieses bestimmte Profil. Diese lokalen Kopien haben Vorrang vor allen Dateien mit denselben Namen in einem geerbten oder funktionierenden Profilordner. Die Dateien in der Spalte [!DNL User] wurden entweder erstellt und im Ordner &quot;User\*profile name*&quot;gespeichert oder befinden sich in einem internen Profil oder einem Arbeitsprofil sowie im Ordner &quot;User\*profile name*&quot;. Die Dateien in den einzelnen Ordnern können identisch sein oder nicht und dürfen nicht dasselbe Änderungsdatum und dieselbe Änderungszeit haben.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Um zu vermeiden, dass Sie den Datensatz nur lokal ändern, ignoriert der Data Workbench-Server die lokalen Kopien der [!DNL profile.cfg]-Datei sowie alle Dateien im Datensatz- oder Exportordner im Ordner &quot;User\*Profilname*&quot;. Ignorierte Dateien werden in der Spalte [!DNL User] durch einen roten Hintergrund und im Kontextmenü durch die Warnung &quot;Ignoriert im Benutzerverzeichnis&quot; gekennzeichnet. Um die Änderungen zu implementieren, die Sie an Ihren lokalen Kopien dieser Dateien vornehmen, müssen Sie sie in Ihrem Arbeitsprofil speichern, damit sie mit dem Data Workbench-Server synchronisiert werden können. Anweisungen zum Speichern von Dateien in Ihrem Arbeitsprofil finden Sie unter [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
      >    
      >    
   * Ein Bindestrich (-) anstelle eines Kontrollkästchens in einer Spalte gibt eine leere (0-Byte-)Datei an. Data Workbench behandelt Nullbyte-Dateien als nicht vorhanden, was es Ihnen ermöglicht, sie zum Ausblenden von in einem Profil auf der linken Seite enthaltenen Dateien zu verwenden. Siehe [Ausblenden von Dateien mit leeren (Null-Byte-)Dateien](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## Dateiversionen bestimmen {#section-225d732246b94cbe87acdfa9c881d6af}

Wie im vorherigen Abschnitt erwähnt, sind die Häkchen im [!DNL Profile Manager] farbcodiert, sodass Sie leicht erkennen können, wo sich eine Datei befindet und ob die verschiedenen Kopien einer Datei zu unterschiedlichen Zeitpunkten geändert wurden.

Wenn eine Datei oder ein reduziertes Verzeichnis genau mit der Datei oder dem Verzeichnis auf der linken Seite übereinstimmt, hat sie dasselbe Farbkontrollzeichen wie die Datei oder das Verzeichnis in dieser Spalte (Profil). Wenn es sich von einer Datei oder einem Verzeichnis auf der linken Seite unterscheidet oder die Datei bzw. das Verzeichnis nur in der Spalte [!DNL User] vorhanden ist, ist das Häkchen weiß.

![](assets/vis_ProfMgr_LocalFiles.png)

Das im obigen Beispiel gezeigte [!DNL Profile Manager]-Zeichen weist auf Folgendes hin:

* Ein weißes Häkchen für die Datei [!DNL A New Metric.metric] wird nur in der Spalte [!DNL User] angezeigt. Dies bedeutet, dass Sie nur über eine lokale Kopie dieser Datei verfügen. Sie wurde nicht veröffentlicht (oder auf den Data Workbench-Server hochgeladen), damit andere Data Workbench-Benutzer darauf zugreifen können.

* Markierungen für den Dateinamen [!DNL Average Score.metric] werden in den Spalten Filme und [!DNL User] angezeigt. Das Häkchen in der Spalte [!DNL User] ist dieselbe Farbe wie das Häkchen in der Spalte &quot;Filme&quot;. Dies bedeutet, dass die lokale Kopie der Datei dasselbe Änderungsdatum und dieselbe Änderungszeit hat wie die Datei im Ordner &quot;Filme&quot;.

* Markierungen für den Dateinamen [!DNL Average Score Error.metric] werden in den Spalten Filme und [!DNL User] angezeigt. Das Häkchen in der Spalte [!DNL User] ist weiß, was bedeutet, dass die lokale Kopie der Datei ein anderes Änderungsdatum oder eine andere Uhrzeit hat als die Datei im Ordner Filme .

