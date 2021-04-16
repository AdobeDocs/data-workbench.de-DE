---
description: Schritte zum erneuten Senden von Berichten per E-Mail.
title: 'Erneutes Versenden von Berichten per E-Mail '
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Erneutes Versenden von Berichten per E-Mail {#resending-reports-by-email}

Schritte zum erneuten Senden von Berichten per E-Mail.

Wenn der Parameter **[!UICONTROL Allow Report Regeneration]** in der Datei [!DNL Report.cfg] auf [!DNL True] eingestellt ist und Sie Änderungen an einer [!DNL Report.cfg]-Datei vornehmen und diese Datei wieder auf dem Server speichern, generiert Report Server die Berichte in diesem Satz automatisch neu. Die Berichte werden nicht per E-Mail erneut gesendet.

1. Wählen Sie auf der Registerkarte [!DNL Reports] den Unterordner (Registerkarte oder Dropdown-Unterordner) für den Berichtsatz aus, den Sie erneut senden möchten.
1. Klicken Sie auf **[!UICONTROL Report.cfg]**. Die Parameter von [!DNL Report.cfg] für diesen Berichtssatz werden angezeigt.
1. Ändern Sie den Parameter **[!UICONTROL Start Date]** in den zukünftigen Zeitpunkt, zu dem Berichte erneut gesendet werden sollen.
1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste auf **[!UICONTROL Report.cfg (modified)]** oben in den Parametern klicken und auf **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]***klicken.
Die Berichte in diesem Satz werden neu generiert und per E-Mail an die angegebenen Empfänger weitergeleitet.
