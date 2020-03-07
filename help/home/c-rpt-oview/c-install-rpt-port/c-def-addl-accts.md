---
description: Benutzer müssen über ein gültiges Konto verfügen und beim Zugriff auf das Report Portal einen Kontonamen und ein Kennwort angeben.
solution: Analytics
title: Zusätzliche Konten definieren
topic: Data workbench
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zusätzliche Konten definieren{#define-additional-accounts}

Benutzer müssen über ein gültiges Konto verfügen und beim Zugriff auf das Report Portal einen Kontonamen und ein Kennwort angeben.

Standardmäßig ist die Benutzerauthentifizierung in aktiviert [!DNL Report Portal].

Die Liste der gültigen Konten für [!DNL Report Portal] wird in der Datenbankdatei beibehalten, [!DNL portal.mdb]. [!DNL Report Portal] mit einem Konto mit Administratorrechten installiert ist:

* Kontoname: test
* Kennwort: user

>[!NOTE]
>
>Aus Sicherheitsgründen empfiehlt Adobe, das Kennwort für dieses Konto nach der Installation zu ändern [!DNL Report Portal].

Um Benutzerkonten zu bestehenden Konten hinzuzufügen [!DNL Report Portal] oder Informationen zu ändern, verwenden Sie die [!DNL Admin] Registerkarte auf der [!DNL Report Portal] Benutzeroberfläche.

Jedes Mal, wenn Sie ein neues Konto hinzufügen oder ein vorhandenes Konto bearbeiten, wird eine Bestätigungs-E-Mail wie in der [!DNL email.asp] Datei im Ordner \*PortalName*\PortalASP angegeben gesendet. Weitere Informationen finden Sie unter [Bearbeiten der Datei](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)&quot;Email.asp&quot;.

Anweisungen zum Hinzufügen weiterer Benutzer finden Sie unter [Arbeiten mit Konten](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Optional können Sie die Benutzerauthentifizierung deaktivieren und den anonymen Zugriff darauf zulassen [!DNL Report Portal]. Anweisungen dazu finden Sie in den Informationen zum Parameter Session(&quot;In&quot;) unter [Bearbeiten der Sitzungskonfigurationsdatei](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).

