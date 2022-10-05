---
description: Die Gruppierung von Abfragezeichenfolgen ermöglicht die Integration einer großen Anzahl von Feldern.
title: Gruppierung von Abfragezeichenfolgen
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
exl-id: 4052cf7e-abdf-4e16-9f42-521c4e719786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# Gruppierung von Abfragezeichenfolgen{#query-string-grouping}

{{eol}}

Die Gruppierung von Abfragezeichenfolgen ermöglicht die Integration einer großen Anzahl von Feldern.

Die Gruppierung von Abfragezeichenfolgen ist für jedes Profil spezifisch, funktioniert aber bei Transformationen wie im folgenden Beispiel gut:

1. Erstellen Sie die Paare, die Sie bündeln möchten, indem Sie eine benutzerdefinierte Konfigurationsdatei hinzufügen ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]) und fügen Sie dann den Umwandlungstyp hinzu *BuildNameValuePair* als Parameter.

   ```
   2 = BuildNameValuePair:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to build)
             Name = string: Custom Events 
             Output = string: x-event-list       
   ```

1. Erstellen Sie eine neue Datei zum Extrahieren der gekürzten Daten in die Felder, die Sie verwenden möchten, indem Sie eine benutzerdefinierte Konfigurationsdatei hinzufügen ( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]) und fügen Sie dann den Umwandlungstyp hinzu *ExtractNameValuePairs* als Parameter.

   ```
   2 = ExtractNameValuePairs:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Field = string: x-event-list 
         Name = string: Custom Events 
         Output Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to extract) 
             Name = string: Custom Events 
             Output = string: x-event-list   
   ```

## Sonstige Verwendungen {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

Wenn Sie viele Felder mit benutzerdefinierten eVars, Props und Variablen haben, können Sie während der Protokollverarbeitung ein Namenswertpaar erstellen, um Felder in einem Bericht zu kombinieren. Sie können beispielsweise Namens-Wert-Paare in kombinierte Felder erstellen, um die [!DNL tempDB] Dateigröße.

![](assets/query_string_grouping.png)
