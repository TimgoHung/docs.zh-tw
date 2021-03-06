---
title: 如何：繪製線條
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: bee343676175098493df347823a3bdbdf17b205f
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2018
ms.locfileid: "45963766"
---
# <a name="how-to-draw-a-line"></a>如何：繪製線條
此範例將示範如何藉由繪製線條<xref:System.Windows.Shapes.Line>項目。  
  
 若要繪製一條線，請建立<xref:System.Windows.Shapes.Line>項目。 使用其<xref:System.Windows.Shapes.Line.X1%2A>並<xref:System.Windows.Shapes.Line.Y1%2A>屬性來設定它的起點，並使用其<xref:System.Windows.Shapes.Line.X2%2A>和<xref:System.Windows.Shapes.Line.Y2%2A>屬性來設定其端點。 最後，設定其<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>因為沒有筆觸線條是不可見。  
  
 設定<xref:System.Windows.Shapes.Shape.Fill%2A>一行的項目會有任何作用，由於線條沒有任何內部。  
  
 下列範例會繪製內的三行<xref:System.Windows.Controls.Canvas>項目。  
  
## <a name="example"></a>範例  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 這個範例屬於較大型的範例;如需完整的範例，請參閱[圖形元素範例](https://go.microsoft.com/fwlink/?LinkID=160037)。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Shapes.Line>  
 [圖形元素範例](https://go.microsoft.com/fwlink/?LinkID=160037)
