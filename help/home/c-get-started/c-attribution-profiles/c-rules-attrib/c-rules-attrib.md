---
description: Mithilfe des neuen regelbasierten Attributions-Profils in der Data Workbench können Sie schnell Zuordnungs-Ereignis analysieren und Verantwortung zuweisen, die zu einer von Ihnen definierten erfolgreichen Umrechnung führt. Das Attribution-Profil enthält alle Informationen, die erforderlich sind, damit Ihr Datenerfasser seine Funktionen einrichten und erweitern kann. Außerdem enthält es vordefinierte Arbeitsbereiche, in denen Ihr Analyst direkt einsteigen und Beginn analysieren kann.
title: Attributionsprofil
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
exl-id: 29946f22-1d39-44ca-9474-13dbe228751c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# Attributionsprofil{#attribution-profile}

Mithilfe des neuen regelbasierten Attributions-Profils in der Data Workbench können Sie schnell Zuordnungs-Ereignis analysieren und Verantwortung zuweisen, die zu einer von Ihnen definierten erfolgreichen Umrechnung führt. Das Attribution-Profil enthält alle Informationen, die erforderlich sind, damit Ihr Datenerfasser seine Funktionen einrichten und erweitern kann. Außerdem enthält es vordefinierte Arbeitsbereiche, in denen Ihr Analyst direkt einsteigen und Beginn analysieren kann.

Mit dem Attribution-Profil können Sie eine neue Perspektive hinsichtlich der Beziehungen zwischen Ihren Marketingbemühungen und einer erfolgreichen KundenInteressentenanwerbung oder -umrechnung gewinnen. Das Attribution-Profil hilft Ihnen, Interaktionen zu qualifizieren, die eine Gutschrift für den erzielten Umsatz oder die nachgelagerte Teilnahme an der Journey erhalten sollten. Sie hilft Ihnen dabei, die Auswirkungen Ihrer Marketingbemühungen und -kosten zu identifizieren, indem Sie schnell die Zuordnungs-Ereignis analysieren und dann die Verantwortung für Erst- oder Letztkontakt oder andere Ereignis zuweisen, die zu einem erfolgreichen Verkauf führen.

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>Das Attribution-Profil ist für die sofortige Verwendung durch Benutzer konfiguriert, die das Adobe SC-Profil implementiert haben, das den Analytics-(SC/Insight-)Datenfeed verwendet. Standardmäßig werden die Ereignis Marketing und Konversion als Standardtypen von Interaktionen verwendet, die in den bereitgestellten regelbasierten Modellen ausgewertet werden.

Weitere Informationen finden Sie unter [Bereitstellen des Attribution-Profils](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) und [Attribution-Modelle](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d).

## Architektur- und Analyst-Arbeitsbereiche {#section-27c6aff70ba147cca6e11451e127afb4}

Im Attribution-Profil sind auf separaten Registerkarten in der Workbench Architektur- und Analyst-Arbeitsbereiche definiert.

![](assets/attribution_profile_tabs.png)

**Architektur-Arbeitsbereiche**

Klicken Sie auf der Registerkarte **Zuordnung** auf die Registerkarte **[!UICONTROL Architect Workspace]**, um Arbeitsbereiche zu öffnen, die speziell für die Einrichtung Ihrer Konfigurationsdateien für das grundlegende Zuordnungsmodell entwickelt wurden.

![](assets/attribution_profile_arch.png)

Auf der Registerkarte &quot;Architektur&quot;finden Sie Arbeitsbereiche, in denen Sie die einzelnen Konfigurationsdateien im Profil-Dataset-Ordner durchlaufen können. Beispielsweise können Sie mit **[!UICONTROL Attribution Configuration - Step 1]** die Zuordnungswerte im Abschnitt &quot;Transformation&quot;der Datei [!DNL profile.cfg] identifizieren.

![](assets/attribution_profile_arch_step1.png)

**Analyst** WorkspacesKlicken Sie auf die  **[!UICONTROL Analyst]** **[!UICONTROL Workspaces]** Registerkarte, um die vordefinierte Analyse der Arbeitsbereiche zu öffnen, die die im Profil Zuordnung bereitgestellten Dimensionen und Metriken verwendet.

Diese Arbeitsbereiche sind in vier Kategorien unterteilt:

1. **Grundlegende** Berichte stellen ein einzelnes Modell in einer Arbeitsfläche dar.
1. **Vergleichende** Berichte erweiterte die Analysen, indem sie mehrere Modelle in einer einzigen Ansicht präsentierten.
1. **Die** Analyseberichte erweitern die Vorlagen der Berichte, um die Zuordnungsmodelle in verschiedenen Formaten darzustellen. In diesem Abschnitt werden auch die Positionsgewichte eingeführt und offen gelegt.
1. **Pfadberichte** bieten einen Einblick in die Marketing-Journey des Kunden mit mehreren Pfadvisualisierungen, um die Prozessflüsse und Interaktions-Pfade vollständig zu untersuchen und darzustellen.

![](assets/attribution_profile_analyst.png)

Die Registerkarte &quot;Analyst&quot;enthält Arbeitsbereiche, die mit Berichten vorkonfiguriert sind. Beispielsweise können Sie **[!UICONTROL First Attribution]** in der Tabelle **[!UICONTROL Campaign]** auswählen, um die **[!UICONTROL Revenue]**-Zuordnung basierend auf **[!UICONTROL Time]** anzuzeigen.

![](assets/attribution_profile_analyst_step1.png)
