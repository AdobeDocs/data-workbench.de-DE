---
description: Um Report Portal zu konfigurieren, müssen Sie die Anwendungsdateien virtuellen Verzeichnissen zuordnen.
title: Zuordnen von Report Portal-Seiten zu virtuellen Verzeichnissen
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 18%

---

# Zuordnen von Report Portal-Seiten zu virtuellen Verzeichnissen{#map-the-report-portal-pages-to-virtual-directories}

{{eol}}

Um Report Portal zu konfigurieren, müssen Sie die Anwendungsdateien virtuellen Verzeichnissen zuordnen.

Ein virtuelles Verzeichnis definiert die Adresse, die Browser-Clients zum Suchen einer physischen Ressource auf dem IIS-Anwendungsserver verwenden. So greifen Sie auf [!DNL Report Portal], verweisen die Clients ihre Browser auf das virtuelle Verzeichnis, das Sie dem Portal zuweisen.

Der Name des virtuellen Verzeichnisses, das Sie zuweisen [!DNL Report Portal] muss mit dem Namen übereinstimmen, den Sie in Schritt 3 des vorherigen Abschnitts für den Ordner VSVirtualPortalName verwendet haben. Wenn Sie beispielsweise &quot;Portal&quot;als Namen für [!DNL Report Portal]müssen Sie die Dateien des Portals einem virtuellen Verzeichnis mit dem Namen &quot;Portal&quot;zuordnen. Das folgende Beispiel zeigt den URI, mit dem Clients auf eine [!DNL Report Portal] dem virtuellen Verzeichnis zugewiesen ist [!DNL VisualReportPortal] auf einem Server namens myWebServer:

[!DNL https://myWebServer/VisualReportPortal]

In den folgenden Verfahren wird beschrieben, wie Sie eine Zuordnung vornehmen [!DNL Report Portal] in ein virtuelles Verzeichnis auf IIS 5.0, 6.0 und 7.0 oder höher.

Befolgen Sie die Vorgehensweisen für die Version von IIS, die Sie verwenden:

* [Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 7.0 oder höher)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 5.0 oder höher)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [Bearbeiten der Datei für die Sitzungskonfiguration](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
