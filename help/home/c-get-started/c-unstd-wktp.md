---
description: Auf der Arbeitsfläche können Sie alle Arbeitsbereiche und Berichte organisieren und darauf zugreifen.
title: Arbeitsflächen
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
exl-id: e714ca25-5e94-408a-9d4e-6e1c13e2a3ef
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Arbeitsflächen{#worktops}

{{eol}}

Auf der Arbeitsfläche können Sie alle Arbeitsbereiche und Berichte organisieren und darauf zugreifen.

In den meisten Fällen wird die [!DNL Worktop] wird unmittelbar nach dem Öffnen der Data Workbench angezeigt. Die Funktionen der [!DNL Worktop] die Seitenleiste und die Benutzeroberfläche mit Registerkarten einschließen. Darüber hinaus können Sie über die Seitenleiste Visualisierungen hinzufügen und auf regelmäßig verwendete Funktionen zugreifen.

**Arbeitsfläche**

![](assets/client-wktp.png)

Die [!DNL Worktop] Sie können auch neue und aktualisierte Arbeitsbereiche und Berichte erstellen und speichern sowie Arbeitsbereiche und Berichte auf dem Data Workbench-Server veröffentlichen, damit andere darauf zugreifen können.

Die [!DNL Worktop] Die nachstehende Tabelle mit den Elementen beschreibt jedes Element der [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689">
 <tbody>
  <tr>
   <td colname="col1"> Seitenleiste </td>
   <td colname="col2"> <p>Die Seitenleiste bietet Kontext und Kontrolle für Arbeitsbereiche, informiert über den aktuellen Status eines Arbeitsbereichs und bietet Zugriff auf regelmäßig verwendete Funktionen. Die folgenden Funktionen sind in der Seitenleiste verfügbar: </p> <p> <b>Verbindung:</b> Eine Statusanzeige, die den Online-Status anzeigt. Klicken Sie auf den Verbindungsstatus, um ihn zu aktivieren oder zu deaktivieren. <span class="wintitle"> Online arbeiten</span>. Siehe <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Offline und online arbeiten</a>. </p> <p> <b>Profil:</b> Ein Indikator für das aktuell verwendete Profil. </p> <p> <b>Ausführungsdatum: </b>Ein Statusindikator, der anzeigt, wie aktuell die Daten im Datensatz des Profils sind. Diese Daten werden vom DPU-Server heruntergeladen und verarbeitet, was nur bei Online-Workflows auftreten kann. </p> <p> <b>Abfrage-/Beispielkonfidenz:</b> Ein Indikator für den Abschluss der Abfrage. Wenn der Status zu 100 Prozent abgerufen wird, wurden alle Daten abgefragt. </p> <p> <b>Hinzufügen:</b> Hiermit können Sie der Seitenleiste Visualisierungen wie Bedienfelder, Legenden und Tabellen hinzufügen. Siehe <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> Hinzufügen von Visualisierungen zur Seitenleiste</a>. </p> <p> <b>Optionen:</b> Hiermit können Sie zu einer vorherigen Seitenleisteneinstellung zurückkehren und die Seitenleiste automatisch ausblenden. </p> <p>Die Einstellungen der Seitenleiste werden im <span class="filepath"> sidebar.vw</span> -Datei, wenn Sie die Data Workbench schließen. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Registerkarten- und Unterregisterkarten- oder Dropdown-Unterverzeichnisse (nicht angezeigt) </p> </td>
   <td colname="col2"> <p>Jede Registerkarte, die auf der <span class="wintitle"> Arbeitsfläche</span> entspricht dem <i>Name des Arbeitsprofils</i>\Workspaces\<i>tab name</i> -Ordner im Installationsordner der Data Workbench und stellt einen bestimmten Informationstyp dar, z. B. Dashboards, Aktivitäten, Akquise, Besucher usw. Die Unterordner im Ordner mit dem Registerkartennamen werden standardmäßig als Unterregisterkarten angezeigt, können aber auch als Unterordner angezeigt werden. Siehe <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> Anpassen von Registerkarten der Arbeitsfläche</a>. </p> <p> <p>Hinweis: Jedes Data Workbench-Profil wird mit einem Standardsatz von Tabs bereitgestellt. Da Ihre Implementierung vollständig angepasst werden kann, können sich die angezeigten Arbeitsbereiche (und daher die Registerkarten) von den in diesem Handbuch beschriebenen unterscheiden. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Profilstatus </td>
   <td colname="col2"> Stellt den Verbindungsstatus zum Data Workbench-Server und den Namen des derzeit geladenen Profils bereit. Das Ausführungsdatum und die Ausführungszeit für die Daten im Datensatz des Profils werden unter dem Online-Indikator angezeigt. </td>
  </tr>
  <tr>
   <td colname="col1"> Minimieren, Maximieren, Schließen </td>
   <td colname="col2"> Windows-Standardfunktionen. </td>
  </tr>
  <tr>
   <td colname="col1"> Miniaturen </td>
   <td colname="col2"> <p>Eine Miniaturansicht ist ein Schnappschuss eines Arbeitsbereichs, der auf der <span class="wintitle"> Arbeitsfläche</span>. Jedes Mal, wenn Sie den Arbeitsbereich speichern, wird ein neuer Schnappschuss erstellt. Mithilfe von Miniaturansichten können Sie einen bestimmten Arbeitsbereich auf der <span class="wintitle"> Arbeitsfläche</span>. </p> <p>Um einen Arbeitsbereich zu öffnen, klicken Sie auf die Miniaturansicht. </p> <p> <p>Hinweis: Jedes Data Workbench-Profil wird mit einem Standardsatz von Arbeitsbereichen bereitgestellt. Da Ihre Implementierung vollständig angepasst werden kann, können sich die angezeigten Arbeitsbereiche (und somit die Miniaturansichten) von den in diesem Handbuch beschriebenen unterscheiden. </p> </p> <p>Weitere Informationen zu Arbeitsbereichen finden Sie unter <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> Konfigurieren der Seitenleiste</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Fehlermeldungen </td>
   <td colname="col2"> <p>Fehlermeldungen werden rot unter dem Status angezeigt. Statuscode-Beschreibungen finden Sie unter <a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>Beispiel: 403_Verboten. </p> </td>
  </tr>
 </tbody>
</table>
