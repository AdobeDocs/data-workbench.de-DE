---
description: Schritte zum erneuten Senden von Berichten per E-Mail.
solution: Analytics
title: Berichte per E-Mail zurücksenden
topic: Data workbench
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Berichte per E-Mail zurücksenden{#resending-reports-by-email}

Schritte zum erneuten Senden von Berichten per E-Mail.

Wenn der **[!UICONTROL Allow Report Regeneration]** Parameter in der [!DNL Report.cfg] Datei auf [!DNL True]festgelegt ist und Sie Änderungen an einer [!DNL Report.cfg] Datei vornehmen und diese Datei auf dem Server speichern, generiert Report Server die Berichte in diesem Satz automatisch neu. Die Berichte werden nicht per E-Mail erneut gesendet.

1. Wählen Sie auf der [!DNL Reports] Registerkarte den Unterordner (Registerkarte oder Dropdown-Unterordner) für den Berichtsatz aus, den Sie erneut senden möchten.
1. Klicken Sie auf **[!UICONTROL Report.cfg]**. Die Parameter des [!DNL Report.cfg] Berichts werden angezeigt.
1. Ändern Sie den **[!UICONTROL Start Date]** Parameter in den zukünftigen Zeitpunkt, zu dem Berichte erneut gesendet werden sollen.
1. Speichern Sie die Datei, indem Sie mit der rechten Maustaste **[!UICONTROL Report.cfg (modified)]** oben auf die Parameter klicken und auf **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*klicken.
Die Berichte in diesem Satz werden neu generiert und per E-Mail an die angegebenen Empfänger gesendet.
