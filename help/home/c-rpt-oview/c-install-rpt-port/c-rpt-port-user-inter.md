---
description: Berichtssätze müssen auf eine bestimmte Weise konfiguriert werden, um Berichte zu erstellen, die über Report Portal korrekt angezeigt werden.
solution: Analytics
title: Anpassen der Benutzeroberfläche von Report Portal
topic: Data workbench
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Anpassen der Benutzeroberfläche von Report Portal{#customize-the-report-portal-user-interface}

Berichtssätze müssen auf eine bestimmte Weise konfiguriert werden, um Berichte zu erstellen, die über Report Portal korrekt angezeigt werden.

Die Benutzeroberfläche für [!DNL Report Portal] zeigt eine Registerkarte für jeden Berichtsatzordner an, der im Ausgabeverzeichnis angezeigt wird und in der [!DNL profiles.xml] -Datei aufgeführt ist, sowie die integrierte [!DNL Admin] Registerkarte, die der anzuzeigenden [!DNL TopNavigation.xml] Datei hinzugefügt werden muss. Weitere Informationen zum Anzeigen der integrierten [!DNL Admin] Registerkarte finden Sie unter [Verknüpfen eines Ausgabeordners mit einer Registerkarte im Benutzer...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Sicherstellen, dass Ihre Berichtsätze mit Report Portal kompatibel sind...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Verknüpfen eines Ausgabeordners mit einer Registerkarte im Benutzer...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Sicherstellen, dass Ihre ReportSets mit ReportPortal kompatibel sind {#section-2b141e5d198a4bbea455699126c24706}

Ein Berichtsatz definiert einen geplanten Auftrag für [!DNL Report]. Es besteht aus zwei Elementen:

* Ein Ordner, der die Sammlung von Arbeitsbereichen definiert, die Sie als Berichte [!DNL Report] erstellen möchten.
* Eine Konfigurationsdatei ( [!DNL Report.cfg]).

Unter anderem wird in der [!DNL Report.cfg] Datei angegeben, [!DNL Report] wann die Berichte erstellt werden und wo die Ausgabedateien gespeichert werden sollen. Berichtssätze befinden sich im Ordner Berichte auf dem Data Workbench-Server. Ein Profil kann beliebig viele Berichtssätze anzeigen.

Um die Kompatibilität mit [!DNL Report Portal]sicherzustellen, müssen Ihre Berichtssätze die folgenden Anforderungen erfüllen:

* Der Ausgabeverzeichnis für Ihre Berichtssätze muss eine konfigurierte [!DNL profiles.xml] Datei enthalten.
* Jeder Berichtssatz muss einen Bericht der obersten Ebene mit dem Namen &quot;*ReportSetName* Summary&quot;enthalten, wobei *ReportSetName* mit dem Namen des Berichtssatzes übereinstimmt. Im Folgenden werden beispielsweise zwei Berichtssätze [!DNL Profile Manager] gezeigt: &quot;Home&quot;und &quot;Traffic&quot;. Beachten Sie, dass jeder Berichtssatz einen Zusammenfassungsbericht definiert ( [!DNL Home Summary.vw] bzw. [!DNL Traffic Summary.vw]).

![](assets/rptPort_scrn_RptSets.png)

Der Zusammenfassungsbericht wird [!DNL Report Portal]auf der Registerkarte des Berichtssatzes angezeigt. Der Zusammenfassungsbericht kann jede beliebige Arbeitsfläche, jedes Fenster oder jede von Ihnen ausgewählte Visualisierung enthalten.

* Der Zusammenfassungsbericht muss der einzige Bericht im Ordner auf der obersten Ebene für einen Berichtssatz sein. Alle anderen Berichte müssen in Unterordnern platziert werden. Wenn Sie andere Berichte in den Ordner auf der obersten Navigationsebene platzieren, können Sie sie nicht über das Portal anzeigen.

## Verknüpfen eines Ausgabeordners mit einer Registerkarte in der Benutzeroberfläche {#section-3f6bc47d37ed448e871f4f685f46acee}

Um die anzuzeigenden Registerkarten [!DNL Report Portal] anzugeben, müssen Sie für jedes Profil eine [!DNL TopNavigation.xml] Datei konfigurieren. Diese Datei legt fest, welche Berichtssätze in der Benutzeroberfläche für ein bestimmtes Profil als Registerkarten angezeigt werden, sowie die Reihenfolge dieser Registerkarten. Die [!DNL TopNavigation.xml] Datei befindet sich im Ordner \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**So bearbeiten Sie die Datei &quot;TopNavigation.xml&quot;**

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die [!DNL TopNavigation.xml] Datei in einem Texteditor wie Notepad.
1. Bearbeiten Sie die Liste der `<TopNav>` Elemente so, dass sie die Namen und Reihenfolge der Berichtssätze definiert, deren Ausgabe Sie anzeigen [!DNL Report Portal] möchten, wie im folgenden Beispiel:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <TOPNAV_ELEMENTS>
   <TOPNAV>
       <NAME>Monthly Web</NAME>
     </TOPNAV>
     <TOPNAV>
       <NAME>Weekly Web</NAME>
     </TOPNAV>
   <TOPNAV> 
         <NAME>Admin</NAME> 
     </TOPNAV>
   </TOPNAV_ELEMENTS>
   ```

   >[!NOTE]
   >
   >Die [!DNL Admin] Registerkarte ist eine integrierte Registerkarte, die zusätzliche Funktionen bietet. Wenn Sie sie nicht in die [!DNL TopNavigation.xml] Datei einschließen, wird diese Registerkarte nicht angezeigt und ihre Funktionalität ist nicht verfügbar.

1. Erstellen Sie im Ordner \*PortalName*\PortalFiles\Core\TopNav\ folder einen Ordner für Ihr nächstes Profil.
1. Kopieren Sie die [!DNL TopNavigation.xml] Datei aus dem ersten Profilordner und fügen Sie sie in den neuen Ordner ein.
1. Bearbeiten Sie die Datei [!DNL TopNavigation.xml] nach Bedarf und speichern Sie sie.
1. Wiederholen Sie die Schritte 3-5 für alle anderen Profile, die in Ihrem Portal verfügbar sind.

