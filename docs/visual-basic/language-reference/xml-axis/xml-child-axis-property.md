---
title: Untergeordnete XML-Achseneigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
ms.openlocfilehash: 8f8283e7ed09e657a20addab0b203b3d99420d3a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838811"
---
# <a name="xml-child-axis-property-visual-basic"></a>Untergeordnete XML-Achseneigenschaft (Visual Basic)
Bietet Zugriff auf die untergeordneten Elemente eines <xref:System.Xml.Linq.XElement>-Objekts, eines <xref:System.Xml.Linq.XDocument>-Objekts, einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten oder einer Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.  
  
## <a name="syntax"></a>Syntax  
  
```  
object.<child>  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`object`|Erforderlich. Ein <xref:System.Xml.Linq.XElement>Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.|  
|.<|Erforderlich. Gibt den Anfang einer untergeordneten Achseneigenschaft an.|  
|`child`|Erforderlich. Name der untergeordneten Knoten des Formulars den Zugriff auf [`prefix:]name`.<br /><br /> -   `Prefix` – Optional.  XML-Namespacepräfix für den untergeordneten Knoten. Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.<br />-   `Name` – Erforderlich. Lokaler Name des untergeordneten Knotens. Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
|>|Erforderlich. Gibt das Ende einer untergeordneten Achseneigenschaft an.|  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine untergeordnete XML-Achseneigenschaft verwenden, um auf untergeordnete Knoten eines <xref:System.Xml.Linq.XElement>-Objekts oder eines <xref:System.Xml.Linq.XDocument>-Objekts bzw. einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten oder <xref:System.Xml.Linq.XDocument>-Objekten über den Namen zuzugreifen. Verwenden Sie die XML-`Value`-Eigenschaft, um auf den Wert des ersten untergeordneten Knotens in der zurückgegebenen Auflistung zuzugreifen. Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 Visual Basic-Compiler konvertiert die untergeordneten Achseneigenschaften in Aufrufe an die <xref:System.Xml.Linq.XContainer.Elements%2A> Methode.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Für den Namen in einer untergeordneten Achseneigenschaft können nur XML-Namespacepräfixe verwendet werden, die mit der `Imports`-Anweisung global deklariert wurden. Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden. Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie auf die untergeordneten Knoten mit dem Namen `phone` aus dem `contact`-Objekt zugegriffen werden kann.  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dargestellt, wie auf die untergeordneten Knoten mit dem Namen `phone` aus der Auflistung zugegriffen werden kann, die von der untergeordneten `contact`-Achseneigenschaft des `contacts`-Objekts zurückgegeben wurde.  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix. Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 Durch diesen Code wird folgender Text angezeigt:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
