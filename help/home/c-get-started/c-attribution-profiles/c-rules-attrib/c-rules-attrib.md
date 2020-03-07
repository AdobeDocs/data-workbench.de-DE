---
description: Mithilfe des neuen regelbasierten Zuordnungsprofils in Data Workbench können Sie Zuordnungsereignisse schnell analysieren und Verantwortlichkeiten zuweisen, die zu einer von Ihnen definierten erfolgreichen Konvertierung führen. Das Zuordnungsprofil enthält alle Informationen, die erforderlich sind, damit Ihr Datenerfasser seine Funktionen einrichten und erweitern kann. Außerdem enthält es vordefinierte Arbeitsbereiche, in denen Ihr Analyst direkt einsteigen und mit der Analyse beginnen kann.
solution: Analytics
title: Zuordnungsprofil
topic: Data workbench
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Attribution Profile{#attribution-profile}

Mithilfe des neuen regelbasierten Zuordnungsprofils in Data Workbench können Sie Zuordnungsereignisse schnell analysieren und Verantwortlichkeiten zuweisen, die zu einer von Ihnen definierten erfolgreichen Konvertierung führen. Das Zuordnungsprofil enthält alle Informationen, die erforderlich sind, damit Ihr Datenerfasser seine Funktionen einrichten und erweitern kann. Außerdem enthält es vordefinierte Arbeitsbereiche, in denen Ihr Analyst direkt einsteigen und mit der Analyse beginnen kann.

Das Zuordnungsprofil ermöglicht es Ihnen, eine neue Perspektive hinsichtlich der Beziehungen zwischen Ihren Marketingbemühungen und einer erfolgreichen Interessentenanwerbung oder -umrechnung von Kunden zu gewinnen. Das Zuordnungsprofil hilft Ihnen dabei, Interaktionen zu qualifizieren, denen eine Gutschrift für den erzielten Umsatz oder die nachgelagerte Teilnahme auf der Customer Journey zugeschrieben werden sollte. Sie hilft Ihnen dabei, die Auswirkungen Ihrer Marketingbemühungen und -kosten zu identifizieren, indem Sie schnell Zuordnungsereignisse analysieren und dann die Verantwortung für Erst- oder Letztkontakt oder andere Ereignisse, die zu einem erfolgreichen Verkauf führen, zuweisen.

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>Das Zuordnungsprofil wird für die sofortige Verwendung durch Benutzer konfiguriert, die das Adobe SC-Profil implementiert haben, das den Analytics-(SC/Insight-)Datenfeed verwendet. Standardmäßig werden die Marketing- und Umrechnungsereignisse als Standardtypen von Interaktionen verwendet, die in den bereitgestellten regelbasierten Modellen ausgewertet werden.

Weitere Informationen finden Sie unter [Bereitstellen des Zuordnungsprofils](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) und der [Zuordnungsmodelle](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d) .

## Architektur- und Analyst-Arbeitsbereiche {#section-27c6aff70ba147cca6e11451e127afb4}

Im Zuordnungsprofil sind auf separaten Registerkarten in der Workbench Architektur- und Analyst-Arbeitsbereiche definiert.

![](assets/attribution_profile_tabs.png)

**Architektur-Arbeitsbereiche**

Klicken Sie auf der Registerkarte &quot; **Zuordnung** &quot;auf die **[!UICONTROL Architect Workspace]** Registerkarte, um Arbeitsbereiche zu öffnen, die speziell für die Einrichtung Ihrer Konfigurationsdateien für das grundlegende Zuordnungsmodell entwickelt wurden.

![](assets/attribution_profile_arch.png)

Die Registerkarte &quot;Architektur&quot;enthält Arbeitsbereiche, in denen die einzelnen Konfigurationsdateien im Ordner &quot;Profildataset&quot;durchlaufen werden. Beispielsweise **[!UICONTROL Attribution Configuration - Step 1]** können Sie die Zuordnungswerte im Abschnitt &quot;Transformation&quot;der [!DNL profile.cfg] Datei identifizieren.

![](assets/attribution_profile_arch_step1.png)

**Analyst Workspaces** Klicken Sie auf die **[!UICONTROL Analyst]****[!UICONTROL Workspaces]** Registerkarte, um eine vordefinierte Analyse der Arbeitsbereiche zu öffnen, die die im Zuordnungsprofil bereitgestellten Dimensionen und Metriken verwendet.

Diese Arbeitsbereiche sind in vier Kategorien unterteilt:

1. **Grundlegende Berichte** stellen ein einziges Modell in einer Arbeitsfläche dar.
1. **Vergleichende Berichte** erweiterte die Analysen, indem sie mehrere Modelle in einer einzigen Ansicht präsentierten.
1. **Untersuchungsberichte** erweitern die Berichtsvorlagen, um die Zuordnungsmodelle in verschiedenen Formaten darzustellen. In diesem Abschnitt werden auch die Positionsgewichte eingeführt und offen gelegt.
1. **Pfadberichte** bieten einen Einblick in die Marketingwege des Kunden mit mehreren Pfadvisualisierungen, um die Prozessflüsse und Interaktionspfade vollständig zu untersuchen und darzustellen.

![](assets/attribution_profile_analyst.png)

Die Registerkarte &quot;Analyst&quot;enthält Arbeitsbereiche, die mit Berichten vorkonfiguriert sind. Sie **[!UICONTROL First Attribution]** können beispielsweise aus der **[!UICONTROL Campaign]** Tabelle auswählen, um die **[!UICONTROL Revenue]** Zuordnung basierend auf anzuzeigen **[!UICONTROL Time]**.

![](assets/attribution_profile_analyst_step1.png)

