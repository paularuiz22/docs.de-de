---
title: LINQ und generische Typen (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
ms.openlocfilehash: fe29bb14b85b74c249a5d9b7f8c2802ef991b13d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977811"
---
# <a name="linq-and-generic-types-c"></a>LINQ und generische Typen (C#)
[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen basieren auf generischen Typen, die mit Version 2.0 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] eingeführt wurden. Sie benötigen kein ausführliches Wissen über Generics, um Abfragen schreiben zu können. Dennoch sollten Sie zwei grundlegende Konzepte verstehen:  
  
1.  Wenn Sie eine Instanz einer generischen Auflistungsklasse wie etwa <xref:System.Collections.Generic.List%601> erstellen, ersetzen Sie das „T“ durch den Objekttyp, den die Liste enthalten wird. Eine Liste von Zeichenfolgen wird z.B. als `List<string>` und eine Liste von `Customer`-Objekten als `List<Customer>` ausgedrückt. Eine generische Liste ist stark typisiert und hat gegenüber Auflistungen, die ihre Elemente als <xref:System.Object> speichern, viele Vorzüge. Wenn Sie versuchen einen `Customer` in eine `List<string>` einzufügen, erhalten Sie zur Laufzeit eine Fehlermeldung. Es ist sehr leicht, generische Auflistungen zu verwenden, da Sie keine Laufzeitumwandlung von Typen durchführen müssen.  
  
2.  <xref:System.Collections.Generic.IEnumerable%601> ist die Schnittstelle, die es ermöglicht, dass generische Auflistungsklassen mithilfe der Anweisung `foreach` aufgelistet werden. Generische Auflistungsklassen unterstützen <xref:System.Collections.Generic.IEnumerable%601>, während nicht generische Auflistungsklassen, wie etwa <xref:System.Collections.ArrayList>, <xref:System.Collections.IEnumerable> unterstützen.  
  
 Weitere Informationen zu Generics finden Sie unter [Generics](../../../../csharp/programming-guide/generics/index.md).  
  
## <a name="ienumerablet-variables-in-linq-queries"></a>IEnumerable<T\>-Variablen in LINQ-Abfragen  
 Die Abfragevariablen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] werden als <xref:System.Collections.Generic.IEnumerable%601> typisiert oder als ein abgeleiteter Typ, wie z.B. <xref:System.Linq.IQueryable%601>. Wenn Sie eine Abfragevariable des Typs `IEnumerable<Customer>` sehen, bedeutet dies nur, dass die Abfrage bei der Ausführung eine Folge von null oder mehr `Customer`-Objekten produziert.  
  
 [!code-csharp[csLINQGettingStarted#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#34)]  
  
 Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a>Verarbeiten von generischen Typdeklaration durch den Compiler  
 Falls Sie dies möchten, können Sie generische Syntax umgehen, indem Sie das Schlüsselwort [var](../../../../csharp/language-reference/keywords/var.md) verwenden. Das Schlüsselwort `var` weist den Compiler an, den Typ der Abfragevariablen abzuleiten, indem er sich an der in der `from`-Klausel angegebenen Datenquelle orientiert. Das folgende Beispiel erstellt den gleichen kompilierten Code wie das vorherige Beispiel:  
  
 [!code-csharp[csLINQGettingStarted#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#35)]  
  
 Das Schlüsselwort `var` ist nützlich, wenn der Typ der Variablen offensichtlich ist, oder wenn es nicht so wichtig ist, die geschachtelten generischen Typen explizit festzulegen, wie z.B. diejenigen, die in Gruppenabfragen erstellt werden. Allgemein wird darauf hingewiesen, dass das Verwenden von `var` das Lesen Ihres Codes durch andere erschwert. Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Generics](../../../../csharp/programming-guide/generics/index.md)
