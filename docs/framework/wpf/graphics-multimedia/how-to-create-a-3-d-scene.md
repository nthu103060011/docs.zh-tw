---
title: 如何：建立立體場景
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: e3c2ea803961ca57606f8ea8bec21d50a38dbe1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-3-d-scene"></a>如何：建立立體場景
這個範例示範如何建立 3d 物件會像一般的工作表的已旋轉的紙張。 A<xref:System.Windows.Controls.Viewport3D>以及下列元件用來建立這個簡單的 3d 場景：  
  
-   使用建立相機<xref:System.Windows.Media.Media3D.PerspectiveCamera>。 相機指定可檢視的 3d 場景哪個部分。  
  
-   網狀結構是用來指定 3d 物件 （單張紙） 使用的圖形<xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>屬性<xref:System.Windows.Media.Media3D.GeometryModel3D>。  
  
-   材質指定物件 （在此範例中的線性漸層） 使用的介面上顯示<xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>屬性<xref:System.Windows.Media.Media3D.GeometryModel3D>。  
  
-   物件使用平台建立光線<xref:System.Windows.Media.Media3D.DirectionalLight>。  
  
## <a name="example"></a>範例  
 下列程式碼會示範如何在 XAML 中建立的 3d 場景。  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>範例  
 下列程式碼會示範如何在程序程式碼中建立相同的 3d 場景。  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>另請參閱  
 [立體圖形概觀](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
