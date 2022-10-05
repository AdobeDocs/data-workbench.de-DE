---
description: Benutzer müssen über ein gültiges Konto verfügen und beim Zugriff auf Report Portal einen Kontonamen und ein Kennwort angeben.
title: Definieren zusätzlicher Konten
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# Definieren zusätzlicher Konten

{{eol}}

Benutzer müssen über ein gültiges Konto verfügen und beim Zugriff auf Report Portal einen Kontonamen und ein Kennwort angeben.

Standardmäßig ist die Benutzerauthentifizierung in [!DNL Report Portal].

Die Liste der gültigen Konten für [!DNL Report Portal] in der Datenbankdatei verwaltet wird, [!DNL portal.mdb]. [!DNL Report Portal] wird mit einem Konto mit Administratorrechten installiert:

* Kontoname: test
* Kennwort: Benutzer

>[!NOTE]
>
>Aus Sicherheitsgründen empfiehlt Adobe, nach der Installation das Kennwort für dieses Konto zu ändern [!DNL Report Portal].

Hinzufügen von Benutzerkonten zu [!DNL Report Portal] oder Informationen bezüglich bestehender Konten ändern, verwenden Sie die [!DNL Admin] auf der Registerkarte [!DNL Report Portal] -Benutzeroberfläche.

Jedes Mal, wenn Sie ein neues Konto hinzufügen oder ein vorhandenes Konto bearbeiten, wird eine Bestätigungs-E-Mail gesendet, wie in der [!DNL email.asp] Datei im Ordner \*PortalName*\PortalASP . Weitere Informationen finden Sie unter [Bearbeiten der Datei &quot;Email.asp&quot;](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

Anweisungen zum Hinzufügen weiterer Benutzer finden Sie unter [Arbeiten mit Konten](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Optional können Sie die Benutzerauthentifizierung deaktivieren und den anonymen Zugriff auf [!DNL Report Portal]. Anweisungen hierzu finden Sie in den Informationen zum Parameter Session(&quot;In&quot;) unter [Bearbeiten der Sitzungskonfigurationsdatei](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
