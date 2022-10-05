---
description: Schritte zum erneuten Senden von Berichten per E-Mail.
title: Erneutes Versenden von Berichten per E-Mail
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Erneutes Versenden von Berichten per E-Mail{#resending-reports-by-email}

{{eol}}

Schritte zum erneuten Senden von Berichten per E-Mail.

Wenn die Variable **[!UICONTROL Allow Report Regeneration]** -Parameter in der [!DNL Report.cfg] -Datei auf [!DNL True], wenn Sie Änderungen an einem [!DNL Report.cfg] und speichern Sie diese Datei wieder auf dem Server. Report Server generiert die Berichte in diesem Satz automatisch neu. Die Berichte werden nicht per E-Mail erneut gesendet.

1. Im [!DNL Reports] wählen Sie den Unterordner (Registerkarte oder Dropdown-Unterverzeichnis) für den Berichtssatz aus, den Sie erneut senden möchten.
1. Klicken Sie auf **[!UICONTROL Report.cfg]**. Die Parameter der [!DNL Report.cfg] für diesen Berichtssatz anzeigen.
1. Ändern Sie die **[!UICONTROL Start Date]** -Parameter auf den zukünftigen Zeitpunkt festlegen, zu dem Berichte erneut gesendet werden sollen.
1. Speichern Sie die Datei durch Rechtsklick **[!UICONTROL Report.cfg (modified)]** oben in den Parametern und klicken Sie auf **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Die Berichte in diesem Satz werden neu generiert und den angegebenen Empfängern per E-Mail erneut gesendet.
