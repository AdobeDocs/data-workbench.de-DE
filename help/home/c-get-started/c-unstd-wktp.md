---
description: Auf der Arbeitsfläche können Sie alle Arbeitsbereiche und Berichte organisieren und darauf zugreifen.
title: Arbeitsflächen
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
exl-id: e714ca25-5e94-408a-9d4e-6e1c13e2a3ef
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Arbeitsflächen{#worktops}

Auf der Arbeitsfläche können Sie alle Arbeitsbereiche und Berichte organisieren und darauf zugreifen.

In den meisten Fällen wird [!DNL Worktop] sofort nach dem Öffnen der Data Workbench angezeigt. Die Funktionen von [!DNL Worktop] umfassen die Seitenleiste und die Benutzeroberfläche mit Registerkarten. Darüber hinaus können Sie mit der Seitenleiste Visualisierungen hinzufügen und auf regelmäßig verwendete Funktionen zugreifen.

**Arbeitsfläche**

![](assets/client-wktp.png)

Mit dem [!DNL Worktop] können Sie außerdem neue und aktualisierte Arbeitsbereiche und Berichte erstellen und speichern sowie Arbeitsbereiche und Berichte veröffentlichen und auf den Data Workbench-Server übertragen, damit andere darauf zugreifen können.

Die nachstehende Elementtabelle [!DNL Worktop] beschreibt jedes Element von [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Seitenleiste </td> 
   <td colname="col2"> <p>Die Seitenleiste bietet Kontext- und Steuerungsmöglichkeiten für Arbeitsbereiche sowie Bewusstsein für den aktuellen Zustand eines Arbeitsbereichs und Zugang zu regelmäßig verwendeten Funktionen. Die folgenden Funktionen sind in der Seitenleiste verfügbar: </p> <p> <b>Verbindung: </b> Eine Statusanzeige, die den Online-Status anzeigt. Klicken Sie auf den Verbindungsstatus, um <span class="wintitle"> Online arbeiten</span> zu aktivieren oder zu deaktivieren. Siehe <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Offline und Online arbeiten</a>. </p> <p> <b>Profil:</b> Ein Indikator für das aktuell verwendete Profil. </p> <p> <b>Ab:  </b>Eine Statusanzeige, die anzeigt, wie aktuell die Daten im Datensatz des Profils sind. Diese Daten werden vom DPU-Server heruntergeladen und verarbeitet. Dies kann nur vorkommen, wenn Sie online arbeiten. </p> <p> <b>Abfragen-/Beispielsicherheit: </b> Ein Indikator für den Abschluss der Abfrage. Wenn der Status auf 100 Prozent Abfrage wird, wurden alle Daten abgefragt. </p> <p> <b>hinzufügen:</b> Hiermit können Sie der Seitenleiste Visualisierungen wie Bedienfelder, Legenden und Tabellen hinzufügen. Siehe <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> Hinzufügen von Visualisierungen zur Seitenleiste</a>. </p> <p> <b>Optionen: </b> Hiermit können Sie zu einer früheren Randleisteneinstellung zurückkehren und die Seitenleiste automatisch ausblenden. </p> <p>Die Einstellungen der Seitenleiste werden in der Datei <span class="filepath"> sidebar.vw</span> gespeichert, wenn Sie die Data Workbench schließen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registerkarten- und Unterregisterkarten- oder Dropdown-Unterordner (nicht angezeigt) </p> </td> 
   <td colname="col2"> <p>Jede Registerkarte, die auf der Registerkarte <span class="wintitle"> Worktop</span> angezeigt wird, entspricht dem Ordner <i>Arbeitsname</i>\Workspaces\<i>tab name</i> im Installationsordner der Data Workbench und stellt einen bestimmten Informationstyp dar, z. B. Dashboard, Aktivität, Akquise, Besucher usw. Die Unterordner im Ordner mit Registerkartennamen werden standardmäßig als Unterregisterkarten angezeigt, können aber auch als Unterordner angezeigt werden. Siehe <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> Anpassen der Arbeitsflächen</a>. </p> <p> <p>Hinweis:  Jedes Data Workbench-Profil wird mit einem Standardsatz von Registerkarten geliefert. Da Ihre Implementierung vollständig angepasst werden kann, unterscheiden sich die angezeigten Arbeitsbereiche (und damit die angezeigten Registerkarten) möglicherweise von den in diesem Handbuch beschriebenen Elementen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profil-Status </td> 
   <td colname="col2"> Stellt den Verbindungsstatus zum Data Workbench-Server und den Namen des aktuell geladenen Profils bereit. Das Ausführungsdatum und die Uhrzeit für die Daten im Datensatz des Profils werden unter dem Online-Indikator angezeigt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minimieren, Maximieren, Schließen </td> 
   <td colname="col2"> Windows-Standardfunktionen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniaturansichten </td> 
   <td colname="col2"> <p>Eine Miniaturansicht ist ein Schnappschuss eines Arbeitsbereichs, der auf der <span class="wintitle">-Arbeitsfläche</span> angezeigt wird. Jedes Mal, wenn Sie den Arbeitsbereich speichern, wird ein neuer Schnappschuss erstellt. Mithilfe von Miniaturen können Sie eine bestimmte Arbeitsfläche auf der <span class="wintitle"> Arbeitsfläche</span> schnell identifizieren. </p> <p>Um einen Arbeitsbereich zu öffnen, klicken Sie auf die Miniaturansicht. </p> <p> <p>Hinweis:  Jedes Data Workbench-Profil wird mit einem Standardsatz von Arbeitsbereichen geliefert. Da Ihre Implementierung vollständig angepasst werden kann, unterscheiden sich die angezeigten Arbeitsbereiche (und damit auch die Miniaturansichten) möglicherweise von den in diesem Handbuch beschriebenen Elementen. </p> </p> <p>Weitere Informationen zu Arbeitsbereichen finden Sie unter <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> Konfigurieren der Seitenleiste</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fehlermeldungen </td> 
   <td colname="col2"> <p>Fehlermeldungen werden in roter Farbe unter dem Status angezeigt. Statuscode-Beschreibungen finden Sie unter <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>Beispiel: 403_Verboten. </p> </td> 
  </tr> 
 </tbody> 
</table>
