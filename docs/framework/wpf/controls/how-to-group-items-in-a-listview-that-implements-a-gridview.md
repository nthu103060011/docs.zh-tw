---
title: 如何：實作 GridView 的 ListView 中的群組項目
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: 76074449d4ea1454689c51ecad54d7c495f00872
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>如何：實作 GridView 的 ListView 中的群組項目
這個範例示範如何顯示群組中的項目<xref:System.Windows.Controls.GridView>檢視模式<xref:System.Windows.Controls.ListView>控制項。  
  
## <a name="example"></a>範例  
 若要顯示群組中的項目<xref:System.Windows.Controls.ListView>，定義<xref:System.Windows.Data.CollectionViewSource>。 下列範例所示<xref:System.Windows.Data.CollectionViewSource>，群組資料項目的值根據`Catalog`資料欄位。  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 下列範例會設定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>如<xref:System.Windows.Controls.ListView>至<xref:System.Windows.Data.CollectionViewSource>前一個範例定義。 此範例也會定義<xref:System.Windows.Controls.ItemsControl.GroupStyle%2A>實作<xref:System.Windows.Controls.Expander>控制項。  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [HOW-TO 主題](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 概觀](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 概觀](../../../../docs/framework/wpf/controls/gridview-overview.md)
