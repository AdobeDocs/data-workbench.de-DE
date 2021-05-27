---
description: Um Report Portal zu konfigurieren, müssen Sie die Anwendungsdateien virtuellen Verzeichnissen zuordnen.
title: Zuordnen von Report Portal-Seiten zu virtuellen Verzeichnissen
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 18%

---

# Zuordnen von Report Portal-Seiten zu virtuellen Verzeichnissen{#map-the-report-portal-pages-to-virtual-directories}

Um Report Portal zu konfigurieren, müssen Sie die Anwendungsdateien virtuellen Verzeichnissen zuordnen.

Ein virtuelles Verzeichnis definiert die Adresse, die Browser-Clients zum Suchen einer physischen Ressource auf dem IIS-Anwendungsserver verwenden. Um auf [!DNL Report Portal] zuzugreifen, verweisen Clients ihre Browser auf das virtuelle Verzeichnis, das Sie dem Portal zuweisen.

Der Name des virtuellen Verzeichnisses, das Sie [!DNL Report Portal] zuweisen, muss mit dem Namen übereinstimmen, den Sie in Schritt 3 des vorherigen Abschnitts für den Ordner VSVirtualPortalName verwendet haben. Wenn Sie beispielsweise &quot;Portal&quot;als Namen Ihres [!DNL Report Portal] verwenden möchten, müssen Sie die Dateien des Portals einem virtuellen Verzeichnis mit dem Namen &quot;Portal&quot;zuordnen. Das folgende Beispiel zeigt den URI, den Clients verwenden würden, um auf einen [!DNL Report Portal] zuzugreifen, der dem virtuellen Verzeichnis [!DNL VisualReportPortal] auf einem Server namens myWebServer zugewiesen ist:

[!DNL http://myWebServer/VisualReportPortal]

Die folgenden Verfahren beschreiben, wie Sie [!DNL Report Portal] einem virtuellen Verzeichnis auf IIS 5.0, 6.0 und 7.0 oder höher zuordnen.

Befolgen Sie die Vorgehensweisen für die Version von IIS, die Sie verwenden:

* [Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 7.0 oder höher)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Zuordnen von Report Portal zu einem virtuellen Verzeichnis (IIS 5.0 oder höher)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [Bearbeiten der Datei für die Sitzungskonfiguration](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
