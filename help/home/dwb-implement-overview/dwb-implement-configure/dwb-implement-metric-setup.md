---
description: In diesem Abschnitt wird beschrieben, wie Sie Metriken in Data Workbench erstellen.
title: Einrichten von Metriken
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
exl-id: a60c08d3-f708-43be-a14f-8b7f129f3ee5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 3%

---

# Einrichten von Metriken{#metrics-setup}

{{eol}}

In diesem Abschnitt wird beschrieben, wie Sie Metriken in Data Workbench erstellen.

## Grundlagen zu Metriken {#section-f0412e851fcb4ac9886dca4003d42cec}

Metriken sind quantitative Informationen über Kundenaktivitäten wie Ansichten, Bestellungen, Anzahl der getätigten Aufrufe und Umsatz. Metriken bilden die Grundlage für Berichte und helfen Ihnen, Datenbeziehungen anzuzeigen und zu verstehen.

Mit der Dimension von Metriken können Sie Metrikzählungen nach einer bestimmten Ebene gruppieren. Sie können damit auch Metrikzählungen nach einer bestimmten Ebene gruppieren.

## Erstellen neuer Metriken {#section-60a413899d1b4707965e06fb5ef7fc4e}

Gehen Sie wie folgt vor, um eine neue Metrik zu erstellen:

1. Klicken **Tool** > **Metrik-Editor**.

1. Geben Sie im Metriken-Editor den neuen Metriknamen und die neue Formel ein. ![](assets/dwb_impl_metrics1.png)

1. Speichern Sie sie im Ordner Metriken . ![](assets/dwb_impl_metrics2.png)

## Erstellen und Bearbeiten abgeleiteter Metriken {#section-ebdcd3ec652f485e90e001d694eab6d0}

Verwenden Sie einen Metrik-Editor, um eine neue Metrik nach Name, Formel und Format zu definieren, die im [!DNL User\profile_name\Metrics] Ordner zur späteren Verwendung.

1. Öffnen Sie den neuen Metrik-Editor mit dem **Admin > Profil** oder indem Sie mit der rechten Maustaste auf die Spalte Benutzer für den Ordner klicken, in dem Sie die Metrik erstellen möchten, und auf **Erstellen > Neue Metrik**. Ein Metrik-Editor wird angezeigt.

1. Im *Name* -Parameter, geben Sie einen Namen für die neue Metrik ein.

   >[!NOTE]
   >
   >Beachten Sie, dass Leerzeichen ( ) zulässig sind, Unterstriche (_) dagegen nicht. Außerdem können Sie die folgenden Symbole nicht verwenden: + - &#42; /

   ![](assets/dwb_impl_metrics3.png)

1. Im *Formel* -Parameter, geben Sie einen Ausdruck für die neue Metrik ein.

   >[!NOTE]
   >
   >Filter müssen in Klammern definiert werden [ ] im Ausdruck. Weitere Syntax-Regeln für Metriken-Ausdrücke finden Sie unter [Syntax für Metrikausdrücke.](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   Diese Tabelle enthält Beispielausdrücke für erweiterte Metriken. ![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   >
   >Wenn ein entsprechender Ausdruck eingegeben wird, zeigt die Vorschauzeile den Wert der neuen Metrik an. Wenn der Ausdruck einen Fehler enthält, zeigt die Vorschauzeile eine Fehlermeldung an.

1. Klicken Sie mit der rechten Maustaste und wählen Sie **Speichern**. Wenn Sie die Metrik speichern, wird eine Datei, die die neue Metrik darstellt, auf Ihrem Computer im DWB erstellt *Installationsordner \Benutzer\Profilname\Metriken* Ordner.

## Bearbeiten vorhandener abgeleiteter Metriken {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. Klicken Sie im Profil-Manager oder Metriken-Manager in der Spalte mit dem Profilnamen mit der rechten Maustaste auf das Häkchen für die Metrikdatei, die Sie bearbeiten möchten, und klicken Sie auf **Lokal machen**.
1. Klicken Sie mit der rechten Maustaste auf das Häkchen für die Metrikdatei in der Spalte Benutzer und klicken Sie auf **Öffnen** aus der Workbench.

   >[!NOTE]
   >
   >Sie können auch einen Metrik-Editor öffnen, indem Sie mit der rechten Maustaste auf einen beliebigen metrikbezogenen Bereich innerhalb einer Visualisierung klicken, um das Metrikmenü anzuzeigen.

1. Im **Metrik-Editor**, bearbeiten und speichern Sie die Metrikdefinition bei Bedarf mithilfe der Schritte 2 bis 4 unter *Erstellen neuer abgeleiteter Metriken*.

   Wenn Sie möchten, dass alle Benutzer des Profils die bearbeitete Metrik verwenden, müssen Sie sie mithilfe des Profil-Managers in dem Arbeitsprofil veröffentlichen.

Weitere Informationen finden Sie in der Dokumentation .

[Syntax für Metrikausdrücke](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[Erstellen und Bearbeiten abgeleiteter Metriken](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
