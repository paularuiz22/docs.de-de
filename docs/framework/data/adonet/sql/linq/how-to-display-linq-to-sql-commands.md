---
title: 'Vorgehensweise: Anzeigen von LINQ to SQL-Befehlen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1decb05e-37ad-4ed6-ab2f-071eb4c4f628
ms.openlocfilehash: d71eaf834ebf36d462f8581f0074b2f6a90bae17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211607"
---
# <a name="how-to-display-linq-to-sql-commands"></a>Vorgehensweise: Anzeigen von LINQ to SQL-Befehlen
Verwenden Sie <xref:System.Data.Linq.DataContext.GetCommand%2A> zur Anzeige von SQL-Befehlen und anderen Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel zeigt das Konsolenfenster die Ausgabe der Abfrage, gefolgt von den erzeugten SQL-Befehlen, den Befehlstypen und den Verbindungstypen an.  
  
 [!code-csharp[DLinqDebuggingSupport#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#3)]
 [!code-vb[DLinqDebuggingSupport#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#3)]  
  
 Die Ausgabe erscheint wie folgt:  
  
```  
Customers from London:  
    Thomas Hardy  
    Victoria Ashworth  
    Elizabeth Brown  
    Ann Devon  
    Simon Crowther  
    Marie Bertrand  
    Hari Kumar  
    Dominique Perrier  
```  
  
```  
Command Text:  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
  
Command Type: Text  
  
Connection: System.Data.SqlClient.SqlConnection  
```  
  
## <a name="see-also"></a>Siehe auch

- [Debugunterstützung](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
