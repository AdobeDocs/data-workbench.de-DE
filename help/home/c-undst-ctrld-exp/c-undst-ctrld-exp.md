---
description: Kontrollierte Experimente sind Tests, mit denen Sie die Ergebnisse einer experimentellen Stichprobengruppe mit denen einer Standard-Kontrollgruppe vergleichen können.
solution: Analytics,Analytics
title: Data Workbench-gesteuerte Experimente
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Von Data Workbenchs gesteuerte Experimente{#data-workbench-controlled-experiments}

Kontrollierte Experimente sind Tests, mit denen Sie die Ergebnisse einer experimentellen Stichprobengruppe mit denen einer Standard-Kontrollgruppe vergleichen können.

Mit Site können Sie kontrollierte Experimente und deren Ergebnisse implementieren, messen und analysieren, da sie sich auf verschiedene Aspekte Ihrer Website beziehen. Auf diese Weise können Sie Hypothesen zur Verbesserung der Website-Performance testen, bevor Sie erhebliche Zeit oder Geld für die vollständige Umsetzung der vorgeschlagenen Änderungen aufwenden.

>[!NOTE]
>
>Site-Experimente können nur in Datasets analysiert werden, bei denen die einzige verwendete Methode zur Identifizierung des Besuchers die Methode [!DNL Sensor] zum Festlegen eines persistenten Cookies ist. Sensoren, die auf J2EE-Servern (JBoss, Tomcat, WebLogic und WebSphere) ausgeführt werden, unterstützen keine kontrollierte Experimentierung. Weitere Informationen finden Sie im folgenden Abschnitt.

Mithilfe der Site können Sie A/B-, A/B/A- und Multivarianz-gesteuerte Experimente implementieren, um genügend Testdaten zu sammeln, um statistisch genaue Daten für eine detaillierte Auswertung Ihrer Hypothese bereitzustellen, ohne die aktuelle Website-Performance zu beeinträchtigen.
