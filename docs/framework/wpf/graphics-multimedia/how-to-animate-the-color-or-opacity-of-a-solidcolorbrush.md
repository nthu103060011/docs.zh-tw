---
title: 操作說明：建立 SolidColorBrush 色彩或不透明效果的動畫
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 2457bdb794d81e7c482f735cad4ade34564328e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>操作說明：建立 SolidColorBrush 色彩或不透明效果的動畫
此範例示範如何以動畫方式顯示<xref:System.Windows.Media.SolidColorBrush.Color%2A>和<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.SolidColorBrush>。  
  
## <a name="example"></a>範例  
 下列範例會使用三個動畫以動畫方式顯示<xref:System.Windows.Media.SolidColorBrush.Color%2A>和<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.SolidColorBrush>。  
  
-   第一次的動畫， <xref:System.Windows.Media.Animation.ColorAnimation>，筆刷的色彩變更為<xref:System.Windows.Media.Colors.Gray%2A>當滑鼠進入矩形。  
  
-   下一步的動畫，另一個<xref:System.Windows.Media.Animation.ColorAnimation>，筆刷的色彩變更為<xref:System.Windows.Media.Colors.Orange%2A>當滑鼠離開矩形。  
  
-   最終的動畫， <xref:System.Windows.Media.Animation.DoubleAnimation>，筆刷的不透明度變更為 0.0，當按下滑鼠左鍵時。  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 如需更完整的範例，示範如何建立不同類型的筆刷的動畫，請參閱[筆刷範例](http://go.microsoft.com/fwlink/?LinkID=159973)。 如需動畫的詳細資訊，請參閱[動畫概觀](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  
  
 此範例的程式碼版本使用的其他動畫範例的一致性，<xref:System.Windows.Media.Animation.Storyboard>將其動畫套用的物件。 不過，當套用程式碼中的單一動畫，它會更容易使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法，而不要使用<xref:System.Windows.Media.Animation.Storyboard>。 如需範例，請參閱[不使用分鏡腳本而建立屬性的動畫](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>另請參閱  
 [動畫概觀](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [分鏡腳本概觀](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [筆刷範例](http://go.microsoft.com/fwlink/?LinkID=159973)
