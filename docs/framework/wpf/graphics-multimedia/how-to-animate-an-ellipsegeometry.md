---
title: 'Vorgehensweise: Animieren einer EllipseGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], EllipseGeometry objects [WPF]
- EllipseGeometry objects [WPF], animating
- graphics [WPF], animation
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
ms.openlocfilehash: 0f8174a2144435c9ad65904ee587355e8b38e935
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126008"
---
# <a name="how-to-animate-an-ellipsegeometry"></a>Vorgehensweise: Animieren einer EllipseGeometry
In diesem Beispiel wird gezeigt, wie zum Animieren einer <xref:System.Windows.Media.Geometry> innerhalb einer <xref:System.Windows.Shapes.Path> Element. Im folgenden Beispiel eine <xref:System.Windows.Media.Animation.PointAnimation> wird verwendet, um das Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> von einer <xref:System.Windows.Media.EllipseGeometry>.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[animatepath_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](~/samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über die Geometrie](geometry-overview.md)
