---
description: Zum Konfigurieren von Report Portal müssen Sie die Anwendungsdateien den virtuellen Verzeichnissen zuordnen.
solution: Analytics
title: Zuordnen von Report Portal-Seiten zu virtuellen Verzeichnissen
topic: Data workbench
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Zuordnen von Report Portal-Seiten zu virtuellen Verzeichnissen{#map-the-report-portal-pages-to-virtual-directories}

Zum Konfigurieren von Report Portal müssen Sie die Anwendungsdateien den virtuellen Verzeichnissen zuordnen.

Ein virtueller Ordner definiert die Adresse, die Browser-Clients zum Suchen einer physischen Ressource auf dem IIS-Anwendungsserver verwenden. Um Zugriff zu erhalten, verweisen Clients [!DNL Report Portal]ihre Browser auf den virtuellen Ordner, den Sie dem Portal zuweisen.

Der Name des virtuellen Ordners, dem Sie zuweisen, [!DNL Report Portal] muss mit dem Namen übereinstimmen, den Sie in Schritt 3 des vorherigen Abschnitts für den Ordner &quot;VSVirtualPortalName&quot;verwendet haben. Wenn Sie z. B. &quot;Portal&quot;als Namen verwenden möchten, [!DNL Report Portal]müssen Sie die Portaldateien einem virtuellen Verzeichnis mit dem Namen &quot;Portal&quot;zuordnen. Das folgende Beispiel zeigt den URI, den Clients verwenden würden, um auf einen [!DNL Report Portal] virtuellen Ordner auf einem Server mit dem Namen myWebServer zuzugreifen [!DNL VisualReportPortal] :

[!DNL http://myWebServer/VisualReportPortal]

Die folgenden Verfahren beschreiben, wie Sie einem virtuellen Verzeichnis unter IIS 5.0, 6.0 und 7.0 oder höher [!DNL Report Portal] zuordnen.

Befolgen Sie die Vorgehensweise für die Version von IIS, die Sie verwenden:

* [Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ Sitzungskonfigurationsdatei [bearbeiten](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)

