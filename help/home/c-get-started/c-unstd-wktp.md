---
description: Auf der Arbeitsfläche können Sie alle Arbeitsbereiche und Berichte organisieren und darauf zugreifen.
solution: Analytics
title: Arbeitsflächen
topic: Data workbench
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arbeitsflächen{#worktops}

Auf der Arbeitsfläche können Sie alle Arbeitsbereiche und Berichte organisieren und darauf zugreifen.

In den meisten Fällen [!DNL Worktop] wird der Bericht sofort nach dem Öffnen von Data Workbench angezeigt. Zu den Funktionen der [!DNL Worktop] gehören die Seitenleiste und die Benutzeroberfläche mit Registerkarten. Darüber hinaus können Sie mit der Seitenleiste Visualisierungen hinzufügen und auf regelmäßig verwendete Funktionen zugreifen.

**Arbeitsfläche**

![](assets/client-wktp.png)

Mit [!DNL Worktop] dem können Sie außerdem neue und aktualisierte Arbeitsbereiche und Berichte erstellen und speichern sowie Arbeitsbereiche und Berichte auf dem Data Workbench-Server veröffentlichen, damit andere darauf zugreifen können.

In der Tabelle [!DNL Worktop] &quot;Elemente&quot;werden die einzelnen Elemente der [!DNL Worktop]Variablen beschrieben.

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Seitenleiste </td> 
   <td colname="col2"> <p>Die Seitenleiste bietet Kontext- und Steuerungsmöglichkeiten für Arbeitsbereiche sowie Bewusstsein für den aktuellen Zustand eines Arbeitsbereichs und Zugang zu regelmäßig verwendeten Funktionen. Die folgenden Funktionen sind in der Seitenleiste verfügbar: </p> <p> <b>Verbindung:</b> Eine Statusanzeige, die den Online-Status anzeigt. Klicken Sie auf den Verbindungsstatus, um <span class="wintitle"> Work Online</span>zu aktivieren oder zu deaktivieren. Siehe <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Offline- und Online-Arbeit</a>. </p> <p> <b>Profil:</b> Ein Indikator für das aktuell verwendete Profil. </p> <p> <b>Ab: </b>Eine Statusanzeige, die anzeigt, wie aktuell die Daten im Profildatensatz sind. Diese Daten werden vom DPU-Server heruntergeladen und verarbeitet. Dies kann nur vorkommen, wenn Sie online arbeiten. </p> <p> <b>Abfrage-/Beispielsicherheit:</b> Ein Indikator für den Abschluss der Abfrage. Wenn der Status zu 100 Prozent abfragt, wurden alle Daten abgefragt. </p> <p> <b>Hinzufügen:</b> Hiermit können Sie der Seitenleiste Visualisierungen wie Bedienfelder, Legenden und Tabellen hinzufügen. Siehe <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> Hinzufügen von Visualisierungen zur Seitenleiste</a>. </p> <p> <b>Optionen:</b> Damit können Sie zu einer vorherigen Randleisteneinstellung zurückkehren und die Seitenleiste automatisch ausblenden. </p> <p>Die Einstellungen der Seitenleiste werden in der Datei " <span class="filepath"> sidebar.vw</span> "gespeichert, wenn Sie Data Workbench schließen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registerkarten- und Unterregisterkarten- oder Dropdown-Unterordner (nicht angezeigt) </p> </td> 
   <td colname="col2"> <p>Jede Registerkarte, die auf der <span class="wintitle"> Arbeitsfläche</span> angezeigt wird, entspricht dem <i>Profilnamen</i>\Workspaces\<i>registernamen</i> im Installationsordner von Data Workbench und stellt einen bestimmten Informationstyp dar, z. B. Dashboards, Aktivität, Akquise, Besucher usw. Die Unterordner im Ordner mit Registerkartennamen werden standardmäßig als Unterregisterkarten angezeigt, können aber auch als Unterordner angezeigt werden. Siehe <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> Anpassen von Registerkarten</a>am Arbeitsplatz. </p> <p> <p>Hinweis:  Jedes Data Workbench-Profil wird mit einem Standardsatz von Registerkarten bereitgestellt. Da Ihre Implementierung vollständig angepasst werden kann, unterscheiden sich die angezeigten Arbeitsbereiche (und damit die angezeigten Registerkarten) möglicherweise von den in diesem Handbuch beschriebenen Elementen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profilstatus </td> 
   <td colname="col2"> Stellt den Verbindungsstatus zum Data Workbench-Server und den Namen des aktuell geladenen Profils bereit. Das Ausführungsdatum und die Uhrzeit für die Daten im Datensatz des Profils werden unter dem Online-Indikator angezeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minimieren, Maximieren, Schließen </td> 
   <td colname="col2"> Windows-Standardfunktionen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniaturansichten </td> 
   <td colname="col2"> <p>Eine Miniaturansicht ist ein Schnappschuss eines Arbeitsbereichs, der auf der <span class="wintitle"> Arbeitsfläche</span>angezeigt wird. Jedes Mal, wenn Sie den Arbeitsbereich speichern, wird ein neuer Schnappschuss erstellt. Mithilfe von Miniaturansichten können Sie einen bestimmten Arbeitsbereich auf der <span class="wintitle"> Arbeitsfläche</span>schnell identifizieren. </p> <p>Um einen Arbeitsbereich zu öffnen, klicken Sie auf die Miniaturansicht. </p> <p> <p>Hinweis:  Jedes Data Workbench-Profil wird mit einem Standardsatz von Arbeitsbereichen bereitgestellt. Da Ihre Implementierung vollständig angepasst werden kann, unterscheiden sich die angezeigten Arbeitsbereiche (und somit auch die angezeigten Miniaturansichten) möglicherweise von den in diesem Handbuch beschriebenen Elementen. </p> </p> <p>Weitere Informationen zu Arbeitsbereichen finden Sie unter <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> Konfigurieren der Seitenleiste</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fehlermeldungen </td> 
   <td colname="col2"> <p>Fehlermeldungen werden in roter Farbe unter dem Status angezeigt. Statuscode-Beschreibungen finden Sie unter <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>Beispiel: 403_Verboten. </p> </td> 
  </tr> 
 </tbody> 
</table>

