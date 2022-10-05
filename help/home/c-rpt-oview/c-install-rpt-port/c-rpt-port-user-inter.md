---
description: Berichtssätze müssen auf bestimmte Weise konfiguriert werden, um Berichte zu erstellen, die über Report Portal korrekt angezeigt werden.
title: Anpassen der Benutzeroberfläche von Report Portal
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Anpassen der Benutzeroberfläche von Report Portal{#customize-the-report-portal-user-interface}

{{eol}}

Berichtssätze müssen auf bestimmte Weise konfiguriert werden, um Berichte zu erstellen, die über Report Portal korrekt angezeigt werden.

Die Benutzeroberfläche für [!DNL Report Portal] ist so konzipiert, dass für jeden Berichtsset-Ordner, der im Ausgabeverzeichnis angezeigt wird und im [!DNL profiles.xml] sowie der integrierten [!DNL Admin] -Tab, der zum [!DNL TopNavigation.xml] -Datei anzuzeigen. Weitere Informationen zum Anzeigen der integrierten [!DNL Admin] Registerkarte, siehe [Verknüpfen eines Ausgabeordners mit einer Registerkarte im Benutzer ...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Sicherstellung der Kompatibilität Ihrer Berichtssätze mit Report Portal..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Verknüpfen eines Ausgabeordners mit einer Registerkarte im Benutzer ...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Sicherstellen, dass Ihre Berichtssätze mit Report Portal kompatibel sind {#section-2b141e5d198a4bbea455699126c24706}

Ein Berichtssatz definiert einen geplanten Auftrag für [!DNL Report]. Sie besteht aus zwei Elementen:

* Ein Ordner, der die gewünschte Sammlung von Arbeitsbereichen definiert [!DNL Report] als Berichte zu generieren.
* Eine Konfigurationsdatei ( [!DNL Report.cfg]).

Unter anderem wird die [!DNL Report.cfg] file [!DNL Report] wann die Berichte zu erstellen sind und wo die Ausgabedateien gespeichert werden sollen. Berichtssätze befinden sich im Ordner Berichte auf dem Data Workbench-Server. Ein Profil kann eine beliebige Anzahl von Berichtssätzen anzeigen.

So stellen Sie die Kompatibilität mit [!DNL Report Portal]müssen Ihre Berichtssätze die folgenden Anforderungen erfüllen:

* Das Ausgabeverzeichnis für Ihre Berichtssätze muss eine konfigurierte [!DNL profiles.xml] -Datei.
* Jeder Berichtssatz muss einen Bericht der obersten Ebene mit dem Namen *ReportSetName* Zusammenfassung: *ReportSetName* entspricht dem Namen des Berichtssatzes. Beispiel: [!DNL Profile Manager] zeigt zwei Berichtssätze an: &quot;Startseite&quot;und &quot;Traffic&quot;. Beachten Sie, dass jeder Berichtssatz einen Zusammenfassungsbericht definiert ( [!DNL Home Summary.vw] und [!DNL Traffic Summary.vw], bzw. ).

![](assets/rptPort_scrn_RptSets.png)

In [!DNL Report Portal], wird der Zusammenfassungsbericht auf der Registerkarte des Berichtssatzes angezeigt. Der Zusammenfassungsbericht kann einen beliebigen Arbeitsbereich, ein beliebiges Fenster oder eine beliebige Visualisierung enthalten.

* Der Zusammenfassungsbericht muss der einzige Bericht im Ordner der obersten Ebene für einen Berichtssatz sein. Alle anderen Berichte müssen in Unterordnern platziert werden. Wenn Sie andere Berichte in den Ordner der obersten Ebene einfügen, können Sie sie nicht über das Portal anzeigen.

## Verknüpfen eines Ausgabeordners mit einer Registerkarte in der Benutzeroberfläche {#section-3f6bc47d37ed448e871f4f685f46acee}

So legen Sie die gewünschten Registerkarten fest [!DNL Report Portal] zur Anzeige müssen Sie eine [!DNL TopNavigation.xml] -Datei für jedes Profil. Diese Datei bestimmt, welche Berichtssätze in der Benutzeroberfläche für ein bestimmtes Profil als Registerkarten angezeigt werden, sowie die Reihenfolge dieser Registerkarten. Die [!DNL TopNavigation.xml] -Datei im Ordner &quot;PortalName*\PortalFiles\Core\TopNav\*profileName*&quot;gespeichert.

**Bearbeiten der Datei &quot;TopNavigation.xml&quot;**

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, den [!DNL TopNavigation.xml] in einem Texteditor wie Notepad.
1. Liste der `<TopNav>` -Elemente, sodass sie die Namen und Reihenfolge der Berichtssätze definieren, deren Ausgabe Sie wünschen [!DNL Report Portal] , um wie im folgenden Beispiel anzuzeigen:

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
   >Die [!DNL Admin] ist eine integrierte Registerkarte, die zusätzliche Funktionen bietet. Wenn Sie ihn nicht in die [!DNL TopNavigation.xml] -Datei, wird dieser Tab nicht angezeigt und seine Funktionalität ist nicht verfügbar.

1. Erstellen Sie im Ordner \*PortalName*\PortalFiles\Core\TopNav\ folder einen Ordner für Ihr nächstes Profil.
1. Kopieren Sie die [!DNL TopNavigation.xml] aus dem ersten Profilordner und fügen Sie ihn in den neuen Ordner ein.
1. Bearbeiten Sie die [!DNL TopNavigation.xml] speichern Sie die Datei nach Bedarf.
1. Wiederholen Sie die Schritte 3 bis 5 für alle anderen in Ihrem Portal verfügbaren Profile.
