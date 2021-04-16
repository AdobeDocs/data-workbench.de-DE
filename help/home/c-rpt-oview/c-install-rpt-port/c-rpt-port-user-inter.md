---
description: Berichtssätze müssen auf eine bestimmte Weise konfiguriert werden, um Berichte zu erstellen, die über Report Portal korrekt angezeigt werden.
title: Anpassen der Benutzeroberfläche von Report Portal
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Anpassen der Benutzeroberfläche von Report Portal{#customize-the-report-portal-user-interface}

Berichtssätze müssen auf eine bestimmte Weise konfiguriert werden, um Berichte zu erstellen, die über Report Portal korrekt angezeigt werden.

Die Benutzeroberfläche für [!DNL Report Portal] zeigt eine Registerkarte für jeden Berichtsatzordner an, der im Ausgabeverzeichnis angezeigt wird und in der [!DNL profiles.xml]-Datei aufgeführt ist, sowie die integrierte Registerkarte [!DNL Admin], die der anzuzeigenden [!DNL TopNavigation.xml]-Datei hinzugefügt werden muss. Weitere Informationen zum Anzeigen der integrierten Registerkarte [!DNL Admin] finden Sie unter [Verknüpfen eines Ausgabeordners mit einer Registerkarte im Benutzer...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Sicherstellen, dass Ihre Berichtsätze mit Report Portal kompatibel sind...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Verknüpfen eines Ausgabeordners mit einer Registerkarte im Benutzer...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Sicherstellen, dass Ihre ReportSets mit ReportPortal kompatibel sind {#section-2b141e5d198a4bbea455699126c24706}

Ein Berichtsatz definiert einen geplanten Auftrag für [!DNL Report]. Es besteht aus zwei Elementen:

* Ein Ordner, der die Sammlung von Arbeitsbereichen definiert, die [!DNL Report] als Berichte generiert werden sollen.
* Eine Konfigurationsdatei ( [!DNL Report.cfg]).

Die Datei [!DNL Report.cfg] teilt [!DNL Report] unter anderem mit, wann die Berichte generiert werden und wo die Ausgabedateien gespeichert werden sollen. Berichtssätze befinden sich im Ordner Berichte auf dem Data Workbench-Server. Ein Profil kann beliebig viele Berichtssätze anzeigen.

Um die Kompatibilität mit [!DNL Report Portal] sicherzustellen, müssen Ihre Berichtssätze die folgenden Anforderungen erfüllen:

* Der Ausgabeverzeichnis für Ihre Berichtsätze muss eine konfigurierte [!DNL profiles.xml]-Datei enthalten.
* Jeder Berichtssatz muss einen Bericht der obersten Ebene mit dem Namen &quot;*ReportSetName* Zusammenfassung&quot;enthalten, wobei *ReportSetName* mit dem Namen des Berichtssatzes übereinstimmt. Im folgenden [!DNL Profile Manager] werden beispielsweise zwei Berichtssätze angezeigt: &quot;Home&quot;und &quot;Traffic&quot;. Beachten Sie, dass jeder Berichtssatz einen Zusammenfassungsbericht definiert ( [!DNL Home Summary.vw] bzw. [!DNL Traffic Summary.vw]).

![](assets/rptPort_scrn_RptSets.png)

In [!DNL Report Portal] wird der Zusammenfassungsbericht auf der Registerkarte des Berichtssatzes angezeigt. Der Zusammenfassungsbericht kann jede beliebige Arbeitsfläche, jedes Fenster oder jede von Ihnen ausgewählte Visualisierung enthalten.

* Der Zusammenfassungsbericht muss der einzige Bericht im Ordner auf der obersten Ebene für einen Berichtssatz sein. Alle anderen Berichte müssen in Unterordnern platziert werden. Wenn Sie andere Berichte in den Ordner auf der obersten Navigationsebene einfügen, können Sie sie nicht über das Portal Ansicht werden.

## Verknüpfen eines Ausgabeordners mit einer Registerkarte in der Benutzeroberfläche {#section-3f6bc47d37ed448e871f4f685f46acee}

Um die Registerkarten anzugeben, die [!DNL Report Portal] angezeigt werden sollen, müssen Sie für jedes Profil eine [!DNL TopNavigation.xml]-Datei konfigurieren. Diese Datei legt fest, welche Berichtssätze in der Benutzeroberfläche für ein bestimmtes Profil als Registerkarten angezeigt werden, sowie die Reihenfolge dieser Registerkarten. Die Datei [!DNL TopNavigation.xml] befindet sich im Ordner \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**So bearbeiten Sie die Datei &quot;TopNavigation.xml&quot;**

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die Datei [!DNL TopNavigation.xml] in einem Texteditor wie Notepad.
1. Bearbeiten Sie die Liste der `<TopNav>`-Elemente so, dass sie die Namen und Reihenfolge der Berichtssätze definiert, deren Ausgabe [!DNL Report Portal] angezeigt werden soll, wie im folgenden Beispiel:

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
   >Die Registerkarte [!DNL Admin] ist eine integrierte Registerkarte mit zusätzlichen Funktionen. Wenn Sie sie nicht in die Datei [!DNL TopNavigation.xml] einschließen, wird diese Registerkarte nicht angezeigt und ihre Funktionalität ist nicht verfügbar.

1. Erstellen Sie im Ordner \*PortalName*\PortalFiles\Core\TopNav\ folder einen Ordner für das nächste Profil.
1. Kopieren Sie die Datei [!DNL TopNavigation.xml] aus dem ersten Profil-Ordner und fügen Sie sie in den neuen Ordner ein.
1. Bearbeiten Sie die Datei nach Bedarf und speichern Sie sie.[!DNL TopNavigation.xml]
1. Wiederholen Sie die Schritte 3-5 für alle anderen Profil, die in Ihrem Portal verfügbar sind.
