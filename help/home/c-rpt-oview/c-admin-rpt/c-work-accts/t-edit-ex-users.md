---
description: Schritte zum Bearbeiten vorhandener Benutzerkonten.
title: Bearbeiten bestehender Benutzer
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
exl-id: cfbc54d8-16b4-4629-b556-a2aa4ee0c606
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 3%

---

# Bearbeiten bestehender Benutzer{#editing-existing-users}

Schritte zum Bearbeiten vorhandener Benutzerkonten.

1. Klicken Sie in [!DNL Report Portal] auf die Registerkarte **[!UICONTROL Admin]** . Die Seite [!DNL Admin] wird angezeigt.

   ![](assets/report_admintag2.png)

1. Klicken Sie auf den Brief, der den ersten Buchstaben des Kontonamens darstellt, den Sie bearbeiten möchten. Wenn Sie beispielsweise das Konto &quot;Marketing&quot;bearbeiten möchten, klicken Sie auf den Buchstaben &quot;M&quot;.

   Eine Liste der Kontonamen, die mit diesem Brief beginnen, wird angezeigt.

1. Wählen Sie den Kontonamen aus, den Sie bearbeiten möchten, und klicken Sie dann auf die Schaltfläche **[!UICONTROL select]** . Die Seite [!DNL Edit Account Info] wird angezeigt.

   ![Schritt-Info](assets/rptPort_scrn_AdminTab_editUser.png)

1. Ändern Sie nur die zu aktualisierenden Felder auf dieser Seite. Die folgende Tabelle enthält Beschreibungen der einzelnen Felder:

   | In diesem Feld . . . | Legen Sie . . . |
   |---|---|
   | email | Die E-Mail-Adresse des Benutzers. |
   | altes Kennwort | Das aktuelle Kennwort, das erforderlich ist, um beim Bearbeiten eines Administratorkontos oder beim Zurücksetzen des Kennworts für ein Konto ohne Administratorrechte fortzufahren. |
   | neues Kennwort | Das neue Kennwort, das der Benutzer beim Anmelden bei [!DNL Report Portal] angeben muss. |
   | Passwort bestätigen | Das neue Kennwort, das der Benutzer beim Anmelden bei [!DNL Report Portal] angeben muss. |
   | Profilzugriff | Die Profile, auf die dieser Benutzer zugreifen darf (z. B. ProductSales). Um den Zugriff auf mehrere Profile zu ermöglichen, trennen Sie die Namen durch Kommas. Wenn der Benutzer auf alle Profile zugreifen darf, die mit [!DNL Report Portal] verknüpft sind, geben Sie &quot;ALL&quot;ein. |
   | Registerkartenzugriff | Die Registerkarten, auf die dieser Benutzer zugreifen darf (z. B. [!DNL Admin]). Um den Zugriff auf mehrere Registerkarten zu ermöglichen, trennen Sie die Namen durch Kommas. Wenn der Benutzer auf alle Registerkarten im [!DNL Report Portal] zugreifen darf, geben Sie &quot;ALL&quot;ein. Dieses Feld ist zusammen mit dem Feld &quot;Kontotyp&quot;sehr nützlich für die Definition von Gruppenzugriffsrechten. |
   | Kontotyp | Ob dieses Konto für eine Einzelperson oder eine Gruppe bestimmt ist. Einzelne Konten ermöglichen es Benutzern, ihre Kennwörter zurückzusetzen, Gruppen dagegen nicht. Ein Administrator ist die einzige Person, die das Kennwort für ein Gruppenkonto zurücksetzen kann. |
   | status | Ob dieses Konto aktiv oder inaktiv ist. Der Standardwert ist aktiv. Um ein Benutzerkonto zu deaktivieren, wählen Sie **[!UICONTROL inactive]** aus. |
   | admin | Gibt an, ob dieser Benutzer Benutzerkonten erstellen, aktualisieren und löschen sowie mit jedem Bericht verknüpfte Notizen bearbeiten kann. Die Standardeinstellung ist &quot;false&quot;. Um dies zu einem Administrator zu machen, wählen Sie &quot;true&quot;aus. |
   | Ablaufdatum | Das Datum im Format MM/TT/JJJJ, bis zu dem dieser Benutzer [!DNL Report Portal] verwenden darf. |

1. Klicken Sie auf **[!UICONTROL update]**.
