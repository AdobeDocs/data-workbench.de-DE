---
description: Der Zugriff auf und die Berechtigungen in Ihrem Report Portal werden über individuelle Benutzer- und Gruppenkonten gesteuert.
solution: Analytics
title: Datei "Email.asp"bearbeiten
topic: Data workbench
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Datei &quot;Email.asp&quot;bearbeiten{#edit-the-email-asp-file}

Der Zugriff auf und die Berechtigungen in Ihrem Report Portal werden über individuelle Benutzer- und Gruppenkonten gesteuert.

Jedes Mal, wenn Sie ein neues Konto hinzufügen oder ein vorhandenes Konto bearbeiten, kann eine Bestätigungs-E-Mail an die E-Mail-Adresse gesendet werden, die Sie für dieses Konto angeben (siehe [Arbeiten mit Konten](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)), und in die E-Mail-Adressen kopiert werden, die Sie in der [!DNL email.asp] Datei angeben.

>[!NOTE]
>
>Benachrichtigungs-E-Mails werden nur an Kontobenutzer gesendet, wenn Sie eine E-Mail-Adresse für das Konto angegeben und die [!DNL email.asp] Datei ordnungsgemäß konfiguriert haben. Wenn Sie keine Benachrichtigungen-E-Mails für ein Konto senden möchten, lassen Sie das E-Mail-Feld des Kontos leer.

Diese Datei befindet sich im `\*PortalName*\PortalASP` Ordner.

1. Öffnen Sie auf dem Computer, auf dem IIS ausgeführt wird, die [!DNL email.asp] Datei in einem Texteditor wie Notepad.
1. Legen Sie die folgenden Variablen fest:

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Für diese Variable. . . </th> 
   <th colname="col2" class="entry"> Geben Sie diese Informationen ein. . . </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>DNS-Name oder IP-Adresse des SMTP-Servers, über den Nachrichten gesendet werden. </p> <p>Beispiel: <span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> Der Anschluss, an dem der SMTP-Server auf Verbindungen überwacht. Dies ist normalerweise Port 25. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sendusing </td> 
   <td colname="col2"> <p>Gibt an, wie die Nachricht gesendet werden soll. Folgende Werte stehen zur Verfügung: </p> <p>1 - Senden Sie Nachrichten mit dem lokal installierten SMTP-Dienst. Verwenden Sie diesen Wert, wenn der SMTP-Dienst auf dem Computer installiert ist, auf dem das Skript ausgeführt wird. </p> <p>2 - Senden Sie Nachrichten mit dem SMTP-Dienst im Netzwerk. Verwenden Sie diesen Wert, wenn der SMTP-Dienst nicht auf dem Computer installiert ist, auf dem das Skript ausgeführt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectorTimeout </td> 
   <td colname="col2">Die Zeit, die der <span class="wintitle"> Bericht</span> auf eine Antwort vom SMTP-Server warten sollte, bevor die Verbindung beendet wird. </td> 
  </tr> 
 </tbody> 
</table>

1. Legen Sie für die [!DNL NewUserEmail()] Funktionen und [!DNL UpdateUserEmail()] Funktionen die folgenden Variablen fest:

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Für diese Variable. . . </th> 
      <th colname="col2" class="entry"> Geben Sie diese Informationen ein. . . </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Von </td> 
      <td colname="col2">Der Text, der in der Kopfzeile "Von"in den Bestätigungs-E-Mails angezeigt werden soll. Dieser Wert kann mit dem <span class="wintitle"> CC</span> -Wert identisch sein. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>Optional. Die gültige E-Mail-Adresse der Person oder des Alias, die eine Kopie aller Nachrichten über neue und geänderte Benutzerkonten erhalten soll. Sie können mehrere E-Mail-Adressen angeben, indem Sie die Adressen durch Kommas (ohne Leerzeichen) trennen. </p> <p>Beispiel: <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Hinweis:  Die Empfänger erhalten Kopien von E-Mails, die Benutzerpasswörter enthalten. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Betreff </td> 
      <td colname="col2"> Der Text, der in der Kopfzeile des Betreffs in den Bestätigungs-E-Mails angezeigt werden soll. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>Der tatsächliche Pfad zu Ihrem Portal. </p> <p>Beispiel: <span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Text </td> 
      <td colname="col2"> <p>Der Text, der in den automatisch generierten E-Mails enthalten ist. </p> <p>Beispielsweise lautet der Standardtext in den E-Mails, die gesendet werden, um Anmeldeinformationen bereitzustellen: 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">Die Anmeldeinformationen für Ihr Webportal finden Sie unten: </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>UserName: Benutzername </p><p>Neues Kennwort: password </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>Sie können über die folgende URL auf das Portal zugreifen: </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">Nachdem Sie sich beim Portal angemeldet haben, können Sie Ihr Passwort auf der Registerkarte " <span class="wintitle"> Admin</span> "ändern. </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Speichern und schließen Sie die Datei.
