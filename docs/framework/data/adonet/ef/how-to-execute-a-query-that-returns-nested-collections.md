---
title: 'Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
ms.openlocfilehash: b3319d3b833ab50ec426c8059bccf818b1407a60
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115296"
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a>Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt
Dieses Beispiel zeigt die Ausführung eines Befehls für ein konzeptionelles Modell mit einem <xref:System.Data.EntityClient.EntityCommand>-Objekt und das Abrufen der Ergebnisse der geschachtelten Auflistung mithilfe eines <xref:System.Data.EntityClient.EntityDataReader>.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1.  Hinzufügen der [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt und Konfigurieren Ihres Projekts zur Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Beispiel  
 Ein *geschachtelte Auflistung* ist eine Sammlung, die innerhalb einer anderen Auflistung. Der folgende Code ruft eine Auflistung von `Contacts` und die geschachtelten Auflistungen von `SalesOrderHeaders` für jeden `Contact` auf.  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a>Siehe auch

- [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
