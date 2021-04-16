---
description: Benutzer müssen über ein gültiges Konto verfügen und beim Zugriff auf das Report Portal einen Kontonamen und ein Kennwort angeben.
title: Definieren zusätzlicher Konten
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# Definieren zusätzlicher Konten

Benutzer müssen über ein gültiges Konto verfügen und beim Zugriff auf das Report Portal einen Kontonamen und ein Kennwort angeben.

Standardmäßig ist die Benutzerauthentifizierung in [!DNL Report Portal] aktiviert.

Die Liste der gültigen Konten für [!DNL Report Portal] wird in der Datenbankdatei [!DNL portal.mdb] beibehalten. [!DNL Report Portal] mit einem Konto mit Administratorrechten installiert ist:

* Kontoname: test
* Kennwort: user

>[!NOTE]
>
>Aus Sicherheitsgründen empfiehlt Adobe, nach der Installation von [!DNL Report Portal] das Kennwort für dieses Konto zu ändern.

Um Benutzerkonten zu [!DNL Report Portal] hinzuzufügen oder Informationen zu bestehenden Konten zu ändern, verwenden Sie die Registerkarte [!DNL Admin] der [!DNL Report Portal]-Benutzeroberfläche.

Jedes Mal, wenn Sie ein neues Konto hinzufügen oder ein vorhandenes Konto bearbeiten, wird eine Bestätigungs-E-Mail gesendet, wie in der Datei [!DNL email.asp] im Ordner \*PortalName*\PortalASP angegeben. Weitere Informationen finden Sie unter [Datei &quot;Email.asp&quot;bearbeiten](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

Anweisungen zum Hinzufügen weiterer Benutzer finden Sie unter [Arbeiten mit Konten](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Optional können Sie die Benutzerauthentifizierung deaktivieren und den anonymen Zugriff auf [!DNL Report Portal] zulassen. Anweisungen dazu finden Sie in den Informationen zum Parameter Session(&quot;In&quot;) unter [Bearbeiten der Sitzungskonfigurationsdatei](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
