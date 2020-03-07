---
description: Mithilfe der Abfragezeichenfolgengruppierung können Sie eine große Anzahl von Feldern zusammenfassen.
title: Gruppierung von Abfragezeichenfolgen
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gruppierung von Abfragezeichenfolgen{#query-string-grouping}

Mithilfe der Abfragezeichenfolgengruppierung können Sie eine große Anzahl von Feldern zusammenfassen.

Die Gruppierung von Abfragezeichenfolgen ist für jedes Profil spezifisch, funktioniert aber bei Transformationen wie im folgenden Beispiel gut:

1. Erstellen Sie die Paare, die Sie bündeln möchten, indem Sie eine benutzerdefinierte Konfigurationsdatei ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]) hinzufügen und dann den Transformationstyp *BuildNameValuePair* als Parameter hinzufügen.

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

1. Erstellen Sie eine neue Datei zum Extrahieren der kondensierten Daten in die Felder, die Sie verwenden möchten, indem Sie eine benutzerdefinierte Konfigurationsdatei hinzufügen ( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]) und dann den Transformation-Typ *ExtractNameValuePairs* als Parameter hinzufügen.

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

## Andere Verwendungszwecke {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

Wenn Sie viele Felder mit benutzerdefinierten eVars, Props und Variablen haben, können Sie während der Protokollverarbeitung ein Namenswertpaar erstellen, um Felder in einem Bericht zu kombinieren. Sie können beispielsweise benannte Wertpaare in kombinierte Felder erstellen, um die [!DNL tempDB] Dateigröße zu reduzieren.

![](assets/query_string_grouping.png)
