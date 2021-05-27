---
description: Berichtssätze müssen auf bestimmte Weise konfiguriert werden, um Berichte zu erstellen, die über Report Portal korrekt angezeigt werden.
title: Anpassen der Benutzeroberfläche von Report Portal
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Anpassen der Benutzeroberfläche von Report Portal{#customize-the-report-portal-user-interface}

Berichtssätze müssen auf bestimmte Weise konfiguriert werden, um Berichte zu erstellen, die über Report Portal korrekt angezeigt werden.

Die Benutzeroberfläche von [!DNL Report Portal] wurde entwickelt, um für jeden Berichtssatzordner, der im Ausgabeverzeichnis angezeigt wird und in der Datei [!DNL profiles.xml] aufgeführt ist, eine Registerkarte anzuzeigen. Außerdem enthält sie die integrierte Registerkarte [!DNL Admin], die der anzuzeigenden Datei [!DNL TopNavigation.xml] hinzugefügt werden muss. Weitere Informationen zum Anzeigen der integrierten Registerkarte [!DNL Admin] finden Sie unter [Verknüpfen eines Ausgabeordners mit einer Registerkarte im Benutzer ...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Sicherstellung der Kompatibilität Ihrer Berichtssätze mit Report Portal..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Verknüpfen eines Ausgabeordners mit einer Registerkarte im Benutzer ...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Sicherstellen, dass Ihre Berichtssätze mit Report Portal kompatibel sind {#section-2b141e5d198a4bbea455699126c24706}

Ein Berichtssatz definiert einen geplanten Auftrag für [!DNL Report]. Sie besteht aus zwei Elementen:

* Ein Ordner, der die Sammlung von Arbeitsbereichen definiert, die [!DNL Report] als Berichte generieren soll.
* Eine Konfigurationsdatei ( [!DNL Report.cfg]).

Die [!DNL Report.cfg]-Datei teilt [!DNL Report] unter anderem mit, wann die Berichte generiert werden und wo die Ausgabedateien gespeichert werden sollen. Berichtssätze befinden sich im Ordner Berichte auf dem Data Workbench-Server. Ein Profil kann eine beliebige Anzahl von Berichtssätzen anzeigen.

Um die Kompatibilität mit [!DNL Report Portal] sicherzustellen, müssen Ihre Berichtssätze die folgenden Anforderungen erfüllen:

* Das Ausgabeverzeichnis für Ihre Berichtssätze muss eine konfigurierte Datei [!DNL profiles.xml] enthalten.
* Jeder Berichtssatz muss einen Bericht der obersten Ebene mit dem Namen &quot;*ReportSetName* Zusammenfassung&quot;enthalten, wobei *ReportSetName* mit dem Namen des Berichtssatzes übereinstimmt. Im folgenden [!DNL Profile Manager] werden beispielsweise zwei Berichtssätze angezeigt: &quot;Home&quot;und &quot;Traffic&quot;. Beachten Sie, dass jeder Berichtssatz einen Zusammenfassungsbericht definiert ( [!DNL Home Summary.vw] bzw. [!DNL Traffic Summary.vw]).

![](assets/rptPort_scrn_RptSets.png)

In [!DNL Report Portal] wird der Zusammenfassungsbericht auf der Registerkarte des Berichtssatzes angezeigt. Der Zusammenfassungsbericht kann einen beliebigen Arbeitsbereich, ein beliebiges Fenster oder eine beliebige Visualisierung enthalten.

* Der Zusammenfassungsbericht muss der einzige Bericht im Ordner der obersten Ebene für einen Berichtssatz sein. Alle anderen Berichte müssen in Unterordnern platziert werden. Wenn Sie andere Berichte in den Ordner der obersten Ebene einfügen, können Sie sie nicht über das Portal anzeigen.

## Verknüpfen eines Ausgabeordners mit einer Registerkarte in der Benutzeroberfläche {#section-3f6bc47d37ed448e871f4f685f46acee}

Um die Registerkarten anzugeben, die [!DNL Report Portal] angezeigt werden sollen, müssen Sie für jedes Profil eine [!DNL TopNavigation.xml]-Datei konfigurieren. Diese Datei bestimmt, welche Berichtssätze in der Benutzeroberfläche für ein bestimmtes Profil als Registerkarten angezeigt werden, sowie die Reihenfolge dieser Registerkarten. Die Datei [!DNL TopNavigation.xml] befindet sich im Ordner \*PortalName*\PortalFiles\Core\TopNav\*profileName* .

**Bearbeiten der Datei &quot;TopNavigation.xml&quot;**

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die Datei [!DNL TopNavigation.xml] in einem Texteditor wie Notepad.
1. Bearbeiten Sie die Liste der `<TopNav>` -Elemente so, dass sie die Namen und Reihenfolge der Berichtssätze definiert, deren Ausgabe [!DNL Report Portal] angezeigt werden soll, wie im folgenden Beispiel gezeigt:

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
   >Die Registerkarte [!DNL Admin] ist eine integrierte Registerkarte mit zusätzlichen Funktionen. Wenn Sie ihn nicht in die Datei [!DNL TopNavigation.xml] aufnehmen, wird dieser Tab nicht angezeigt und seine Funktionalität ist nicht verfügbar.

1. Erstellen Sie im Ordner \*PortalName*\PortalFiles\Core\TopNav\ folder einen Ordner für Ihr nächstes Profil.
1. Kopieren Sie die Datei [!DNL TopNavigation.xml] aus dem ersten Profilordner und fügen Sie sie in den neuen Ordner ein.
1. Bearbeiten Sie den [!DNL TopNavigation.xml] nach Bedarf und speichern Sie dann die Datei.
1. Wiederholen Sie die Schritte 3 bis 5 für alle anderen in Ihrem Portal verfügbaren Profile.
