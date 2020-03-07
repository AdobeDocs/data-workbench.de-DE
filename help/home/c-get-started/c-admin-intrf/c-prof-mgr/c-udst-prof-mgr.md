---
description: Die Ordner- und Dateinamen, die in Ihrer Implementierung enthalten sind, werden auf der linken Seite des Profilmanagers angezeigt.
solution: Analytics
title: Profilmanager
topic: Data workbench
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profilmanager{#profile-manager}

Die Ordner- und Dateinamen, die in Ihrer Implementierung enthalten sind, werden auf der linken Seite des Profilmanagers angezeigt.

Die Profile, aus denen Ihre Anwendung besteht, werden als einzelne Spalten im [!DNL Profile Manager]Diagramm angezeigt. Zu diesen Profilen gehören mehrere geerbte Profile und ein einziges Arbeitsprofil.

>[!NOTE]
>
>Ihr Arbeitsprofil (entweder ein DataSet-Profil oder ein rollenspezifisches Profil) ist das Profil, das Sie beim Öffnen von Data Workbench laden.

Die Häkchen (und ihre Farben) geben den/die Profilordner auf dem Data Workbench-Server und den Data Workbench-Computern an, auf denen sich jede Datei befindet, ob mehrere Kopien einer Datei vorhanden sind und ob diese Mehrfachkopien dasselbe Datum und dieselbe Uhrzeit haben. Diese Dateien werden während des Profildownloads zwischen dem Data Workbench-Server und den Data Workbench-Computern synchronisiert.

Im Folgenden finden Sie ein Beispiel [!DNL Profile Manager] für eine HBX-Implementierung:

![](assets/client-prof.png)

Über das [!DNL Profile Manager] Menü können Sie alle anderen Manager (z. B. die [!DNL Dimensions Manager] oder [!DNL Reports Manager]) öffnen, die nur bestimmte Teile anzeigen [!DNL Profile Manager]. Sie können auch neue Profilmanager erstellen. Siehe [Erstellen neuer Profilmanager](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

Ein Häkchen neben einem Dateinamen in einer bestimmten Spalte zeigt an, dass sich eine Datei mit diesem Namen in dem in dieser Spalte (Profil) genannten Ordner befindet. Wenn Sie nach rechts in der [!DNL Profile Manager]Datei wechseln, haben die Dateien Vorrang vor den Dateien links, d. h. jedes geerbte Profil baut auf den Profilen links im [!DNL Profile Manager]. Wenn Sie beispielsweise eine Datei mit demselben Namen und an demselben Speicherort im Profil (Spalte) und im Profil (Spalte) haben, wird die Datei im Profil anstelle der Datei im [!DNL Base] Profil [!DNL User] (Spalte) verwendet. Die Datei im [!DNL User] Profil wird dann anstelle der Datei im [!DNL Base] Profil verwendet.

## Profile suchen {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

Mit Data Workbench 5.5 wurde ein Suchfeld hinzugefügt, um die erforderlichen Profile in der [!DNL Profile Manager]zu finden.

![](assets/client-prof2.png)

Die folgenden Arten von Spalten werden in der [!DNL Profile Manager]angezeigt:

* Die *Spalten für den geerbten Profilnamen* enthalten Häkchen für Dateien, die sich in den einzelnen Profilordnern befinden. Zu den geerbten Profilen gehören interne Profile von Adobe sowie unternehmensspezifische oder rollenspezifische Profile, die Sie erstellen und verwalten. Im obigen Beispiel umfassen die internen Profile Base, Traffic, Value, Marketing usw. Das interne [!DNL Base] Profil, das die grundlegenden Bausteine und Konfigurationsinformationen enthält, die zum Ausführen der Adobe-Anwendung erforderlich sind, wird bei jeder Implementierung bereitgestellt. Die anderen internen Profile enthalten Elemente (Arbeitsbereiche, Metriken, abgeleitete Dimensionen usw.), die sich auf bestimmte Arten von Informationen beziehen, wie z. B. Web-Traffic oder Marketing. Adobe stellt nur die Profile bereit, die für den Datentyp, den Sie analysieren, und für Ihre Branche geeignet sind.

   >[!NOTE]
   >
   >Standardmäßig können interne Profile (die von Adobe bereitgestellt werden) nicht geändert werden. Alle Anpassungen müssen in Ihrem Datensatz, in Ihren rollenspezifischen Profilen oder in anderen Profilen, die Sie erstellen, vorgenommen werden. Wenn Sie eine neue Anwendung erstellen und ein internes Profil ändern müssen, müssen Sie den Parameter &quot;Interne Profile ändern&quot;in der [!DNL Insight.cfg] Datei ändern. Weitere Informationen finden Sie unter [Insight-Konfigurationsparameter](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) . Wenden Sie sich zuvor an Adobe Consulting Services.

* Die Spalte mit dem *Arbeitsprofilnamen* , die immer die letzte Spalte darstellt, enthält Häkchen für Dateien, die sich im Ordner des aktuellen Arbeitsprofils befinden. Im obigen Beispiel ist das Arbeitsprofil DataSet. Ihr Arbeitsprofil ist entweder ein DataSet-Profil oder ein rollenspezifisches Profil. Die Dateien in diesem Ordner haben Vorrang vor allen Dateien mit denselben Namen in einem geerbten Profilordner.
* Die [!DNL User] Spalte, bei der es sich immer um die letzte Spalte handelt, enthält Häkchen für Dateien und Ordner, die als lokale Dateien im Ordner &quot;Benutzer\*Profilname*&quot;gespeichert sind. Die Ordnerstruktur des Benutzerordners entspricht der des Arbeitsprofils. Jeder User\*Profilname*-Ordner enthält lokale Kopien der Arbeitsbereiche, Metriken, Dimensionen und Konfigurationsdateien für dieses Profil. Diese lokalen Kopien haben Vorrang vor allen Dateien mit denselben Namen in einem geerbten oder funktionierenden Profilordner. Die Dateien in der [!DNL User] Spalte wurden entweder erstellt und im Ordner &quot;Benutzer\*Profilname*&quot;gespeichert oder befinden sich in einem internen oder einem Arbeitsprofil sowie im Ordner &quot;Benutzer\*Profilname*&quot;. Die Dateien in jedem Ordner können identisch sein oder nicht identisch sein und können dasselbe Datum und dieselbe Uhrzeit haben.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Um zu vermeiden, dass der Datensatz nur lokal geändert wird, ignoriert der Data Workbench-Server die lokalen Kopien der [!DNL profile.cfg] Datei sowie alle Dateien im Ordner &quot;Dataset&quot;oder &quot;Export&quot;im Ordner &quot;User\*profile name*&quot;. Ignorierte Dateien werden durch einen roten Hintergrund in der [!DNL User] Spalte und eine Warnung &quot;Im Benutzerverzeichnis ignoriert&quot;im Kontextmenü identifiziert. Um die Änderungen zu implementieren, die Sie in Ihren lokalen Kopien dieser Dateien vornehmen, müssen Sie sie in Ihrem Arbeitsprofil speichern, damit sie mit dem Data Workbench-Server synchronisiert werden können. Anweisungen zum Speichern von Dateien in Ihrem Arbeitsprofil finden Sie unter [Veröffentlichen von Dateien in Ihrem Arbeitsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
      >    
      >    
   * Ein Bindestrich (-) anstelle eines Häkchens in einer Spalte kennzeichnet eine leere Datei (0-Byte-Datei). Data Workbench behandelt Nullbyte-Dateien als nicht vorhanden, was Ihnen ermöglicht, sie zum Ausblenden von Dateien zu verwenden, die in einem Profil auf der linken Seite enthalten sind. Siehe [Ausblenden von Dateien mit leeren (Null-Byte-)Dateien](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## Dateiversionen bestimmen {#section-225d732246b94cbe87acdfa9c881d6af}

Wie im vorherigen Abschnitt erwähnt, [!DNL Profile Manager] sind die Häkchen im Abschnitt farblich codiert, sodass Sie leicht erkennen können, wo sich eine Datei befindet und ob die Mehrfachkopien einer Datei zu unterschiedlichen Zeiten verändert wurden.

Wenn eine Datei oder ein minimierter Ordner genau mit der Datei oder dem Verzeichnis auf der linken Seite identisch ist, hat sie dasselbe Farbkontrollzeichen wie die Datei oder das Verzeichnis in dieser Spalte (Profil). Wenn es sich von einer Datei oder einem Verzeichnis auf der linken Seite unterscheidet oder die Datei bzw. das Verzeichnis nur in der [!DNL User] Spalte vorhanden ist, ist das Häkchen weiß.

![](assets/vis_ProfMgr_LocalFiles.png)

Das oben stehende Beispiel [!DNL Profile Manager] zeigt Folgendes an:

* Ein weißes Häkchen für die [!DNL A New Metric.metric] Datei wird nur in der [!DNL User] Spalte angezeigt. Dies bedeutet, dass Sie nur über eine lokale Kopie dieser Datei verfügen. Diese Datei wurde nicht auf den Data Workbench-Server hochgeladen, damit andere Data Workbench-Benutzer darauf zugreifen können.

* Häkchen für den [!DNL Average Score.metric] Dateinamen werden in den Spalten &quot;Filme&quot;und &quot; [!DNL User] Filme&quot;angezeigt. Das Häkchen in der [!DNL User] Spalte ist dieselbe Farbe wie das Häkchen in der Spalte &quot;Filme&quot;. Dies bedeutet, dass die lokale Kopie der Datei dasselbe Datum und dieselbe Uhrzeit hat wie die Datei im Ordner &quot;Filme&quot;.

* Häkchen für den [!DNL Average Score Error.metric] Dateinamen werden in den Spalten &quot;Filme&quot;und &quot; [!DNL User] Filme&quot;angezeigt. Das Häkchen in der [!DNL User] Spalte ist weiß, was bedeutet, dass die lokale Kopie der Datei ein anderes Datum oder eine andere Uhrzeit hat als die Datei im Ordner &quot;Filme&quot;.

