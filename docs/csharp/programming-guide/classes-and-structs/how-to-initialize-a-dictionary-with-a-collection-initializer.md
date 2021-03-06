---
title: Initialisieren eines Wörterbuchs mit einem Auflistungsinitialisierer – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: acd426b7652705ff395df9a81cde8ef549af0e31
ms.sourcegitcommit: d09c77414e9e4fc72c79b04deee7a756a120674e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2019
ms.locfileid: "54084692"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Initialisieren eines Wörterbuchs mit einem Auflistungsinitialisierer (C#-Programmierhandbuch)

Eine <xref:System.Collections.Generic.Dictionary%602> enthält eine Sammlung von Schlüssel-Wert-Paaren. Die <xref:System.Collections.Generic.Dictionary%602.Add*>-Methode nimmt zwei Parameter an, einen für den Schlüssel und einen für den Wert. Eine Möglichkeit, um eine <xref:System.Collections.Generic.Dictionary%602>-Klasse oder eine beliebige Sammlung zu initialisieren, deren `Add`-Methode mehrere Parameter annimmt, ist es, jedes Parameterpaar in Klammern einzuschließen, so wie im folgenden Beispiel dargestellt. Eine andere Möglichkeit besteht darin, einen Index-Initialisierer zu verwenden, wie im nächsten Beispiel gezeigt wird.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird <xref:System.Collections.Generic.Dictionary%602> mit Instanzen vom Typ `StudentName` initialisiert.  Die erste Initialisierung verwendet die `Add`-Methode mit zwei Argumenten. Der Compiler führt für `Add` einen Aufruf für jedes der Paare von `int`-Schlüsseln und `StudentName`-Werten durch. Bei der zweiten Initialisierung wird eine öffentliche Indexermethode der `Dictionary`-Klasse für Lese- und Schreibvorgänge verwendet:

[!code-csharp-interactive[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

Beachten Sie die zwei Paare geschweifter Klammern in jedem Element der Collection in der ersten Deklaration. Die inneren Klammern umschließen den Objektinitialisierer für `StudentName`, und die äußeren Klammern umschließen den Initialisierer für das Schlüssel-Wert-Paar, das `students` <xref:System.Collections.Generic.Dictionary%602> hinzugefügt wird. Schließlich wird der ganze Auflistungsinitialisierer für das Wörterbuch in geschweifte Klammern eingeschlossen. Bei der zweiten Initialisierung ist die linke Seite des Arbeitsauftrags der Schlüssel und die rechte Seite ist der Wert. Für `StudentName` wird ein Objektinitialisierer verwendet.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Objekt- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
