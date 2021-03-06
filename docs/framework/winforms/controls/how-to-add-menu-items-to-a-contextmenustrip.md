---
title: 如何：將功能表項目加入至 ContextMenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: d044cf92cf7ce6db3425aacf397d6c7b4f111324
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a>如何：將功能表項目加入至 ContextMenuStrip
您可以一次新增一個功能表項目或數個項目<xref:System.Windows.Forms.ContextMenuStrip>。  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a>若要將單一功能表項目加入 ContextMenuStrip  
  
-   使用<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>方法，將一個功能表項目<xref:System.Windows.Forms.ContextMenuStrip>。  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a>若要將數個功能表項目加入 ContextMenuStrip  
  
-   使用<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>方法，以將數個功能表項目加入<xref:System.Windows.Forms.ContextMenuStrip>。  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a>另請參閱  
 [ContextMenuStrip 控制項](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
