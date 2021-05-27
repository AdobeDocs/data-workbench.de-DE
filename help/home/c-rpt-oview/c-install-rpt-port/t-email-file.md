---
description: Der Zugriff auf und die Berechtigungen in Ihrem Report Portal werden über individuelle Benutzer- und Gruppenkonten gesteuert.
title: Bearbeiten der Datei „Email.asp“
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
exl-id: e984f12f-362a-4dee-9af3-6d7a38a178a4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 2%

---

# Bearbeiten der Datei „Email.asp“{#edit-the-email-asp-file}

Der Zugriff auf und die Berechtigungen in Ihrem Report Portal werden über individuelle Benutzer- und Gruppenkonten gesteuert.

Jedes Mal, wenn Sie ein neues Konto hinzufügen oder ein vorhandenes Konto bearbeiten, kann eine Bestätigungs-E-Mail an die E-Mail-Adresse gesendet werden, die Sie für dieses Konto angeben (siehe [Arbeiten mit Konten](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)), und sie kann an die E-Mail-Adressen kopiert werden, die Sie in der Datei [!DNL email.asp] angegeben haben.

>[!NOTE]
>
>Benachrichtigungs-E-Mails werden nur an Benutzer gesendet, die eine E-Mail-Adresse für das Konto angegeben und die Datei [!DNL email.asp] ordnungsgemäß konfiguriert haben. Wenn Sie keine Benachrichtigungs-E-Mails für ein Konto senden möchten, lassen Sie das E-Mail-Feld des Kontos leer.

Diese Datei befindet sich im Ordner `\*PortalName*\PortalASP` .

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die Datei [!DNL email.asp] in einem Texteditor wie Notepad.
1. Legen Sie die folgenden Variablen fest:

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diese Variable . . . </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen an. . . </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>DNS-Name oder IP-Adresse des SMTP-Servers, über den Nachrichten gesendet werden. </p> <p>Beispiel: <span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> Der Anschluss, an dem der SMTP-Server auf Verbindungen wartet. Dies ist normalerweise Port 25. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sendusing </td> 
   <td colname="col2"> <p>Gibt an, wie die Nachricht gesendet werden soll. Folgende Werte stehen zur Verfügung: </p> <p>1 - Nachrichten mit dem lokal installierten SMTP-Dienst senden. Verwenden Sie diesen Wert, wenn der SMTP-Dienst auf dem Computer installiert ist, auf dem das Skript ausgeführt wird. </p> <p>2 - Senden Sie Nachrichten mit dem SMTP-Dienst im Netzwerk. Verwenden Sie diesen Wert, wenn der SMTP-Dienst nicht auf dem Computer installiert ist, auf dem das Skript ausgeführt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2">Die Zeit, die <span class="wintitle"> Report</span> auf eine Antwort vom SMTP-Server warten soll, bevor die Verbindung unterbrochen wird. </td> 
  </tr> 
 </tbody> 
</table>

1. Legen Sie für die Funktionen [!DNL NewUserEmail()] und [!DNL UpdateUserEmail()] die folgenden Variablen fest:

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Für diese Variable . . . </th> 
      <th colname="col2" class="entry"> Geben Sie diese Informationen an. . . </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Von </td> 
      <td colname="col2">Der Text, der in der Kopfzeile von Von in Ihren Bestätigungs-E-Mails angezeigt werden soll. Dieser Wert kann mit dem Wert <span class="wintitle"> CC</span> übereinstimmen. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>Optional. Die gültige E-Mail-Adresse der Person oder des Alias, die eine Kopie aller Nachrichten bezüglich neuer und geänderter Benutzerkonten erhalten soll. Sie können mehrere E-Mail-Adressen angeben, indem Sie die Adressen durch Kommas (ohne Leerzeichen) trennen. </p> <p>Beispiel: <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Hinweis:  Die Empfänger erhalten Kopien von E-Mails, die Benutzerkennwörter enthalten. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Betreff </td> 
      <td colname="col2"> Der Text, der in der Kopfzeile des Betreffs in Ihren Bestätigungs-E-Mails angezeigt werden soll. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>Der tatsächliche Pfad zu Ihrem Portal. </p> <p>Beispiel: <span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Text </td> 
      <td colname="col2"> <p>Der in den automatisch generierten E-Mails enthaltene Text. </p> <p>Folgendes ist beispielsweise der Standardtext, der in den gesendeten E-Mails enthalten ist, um Anmeldeinformationen bereitzustellen: 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">Die Anmeldeinformationen für Ihr Webportal finden Sie unten: </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>UserName: Benutzername </p><p>Neues Kennwort: password </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>Sie können über die folgende URL auf das Portal zugreifen: </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">Nachdem Sie sich beim Portal angemeldet haben, können Sie Ihr Kennwort auf dem Tab <span class="wintitle"> Admin</span> ändern. </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Speichern und schließen Sie die Datei.
