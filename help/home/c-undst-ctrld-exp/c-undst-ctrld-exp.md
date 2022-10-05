---
description: Kontrollierte Experimente sind Tests, mit denen Sie die Ergebnisse einer experimentellen Stichprobengruppe mit denen einer Standardkontrollgruppe vergleichen können.
solution: Analytics
title: Data Workbench gesteuerte Experimente
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Data Workbench gesteuerte Experimente{#data-workbench-controlled-experiments}

{{eol}}

Kontrollierte Experimente sind Tests, mit denen Sie die Ergebnisse einer experimentellen Stichprobengruppe mit denen einer Standardkontrollgruppe vergleichen können.

Mit Site können Sie kontrollierte Experimente und deren Ergebnisse implementieren, messen und analysieren, da sie sich auf verschiedene Aspekte Ihrer Website beziehen. Auf diese Weise können Sie Hypothesen hinsichtlich der Verbesserung der Website-Performance testen, bevor Sie erhebliche Zeit oder Geld für die vollständige Umsetzung der vorgeschlagenen Änderungen aufwenden.

>[!NOTE]
>
>Site-Experimente können nur in Datensätzen analysiert werden, in denen die einzige verwendete Methode zur Besucheridentifizierung die [!DNL Sensor] persistente Cookie-Methode festlegen. Sensoren, die auf J2EE-Servern (JBoss, Tomcat, WebLogic und WebSphere) ausgeführt werden, unterstützen keine kontrollierte Experimentierung. Weitere Informationen finden Sie im folgenden Abschnitt.

Mithilfe von Site können Sie A/B-, A/B/A- und multivariate kontrollierte Experimente implementieren, um ausreichend Testdaten zu sammeln, um statistisch präzise Daten für eine detaillierte Auswertung Ihrer Hypothese bereitzustellen, ohne die aktuelle Website-Leistung zu beeinträchtigen.
