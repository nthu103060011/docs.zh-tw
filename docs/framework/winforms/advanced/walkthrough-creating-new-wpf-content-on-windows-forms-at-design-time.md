---
title: 逐步解說：在設計階段建立 Windows Form 的新 WPF 內容
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 1ea0160530fea0f35c6d4746dc4bbca9439bc462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a>逐步解說：在設計階段建立 Windows Form 的新 WPF 內容
本主題示範如何建立 Windows Presentation Foundation (WPF) 控制項，以便在 Windows Form 應用程式中使用。  
  
 在這個逐步解說中，您將執行下列工作：  
  
-   建立專案。  
  
-   建立新的 WPF 控制項。  
  
-   將新的 WPF 控制項加入 Windows Form。 WPF 控制項裝載於 <xref:System.Windows.Forms.Integration.ElementHost> 控制項中。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱 [在 Visual Studio 中自訂開發設定](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)  
  
## <a name="prerequisites"></a>必要條件  
 您需要下列元件才能完成此逐步解說：  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>建立專案  
 第一個步驟是建立 Windows Form 專案。  
  
> [!NOTE]
>  裝載 WPF 內容時，只支援 C# 和 Visual Basic 專案。  
  
#### <a name="to-create-the-project"></a>若要建立專案  
  
-   建立新的 Windows Forms 應用程式專案在 Visual Basic 或 Visual C# 中名為`HostingWpf`。  
  
## <a name="creating-a-new-wpf-control"></a>建立新的 WPF 控制項  
 建立新的 WPF 控制項並將其加入專案中，就像是將其他任何項目加入專案中一樣容易。 Windows Form 設計工具搭配特定種類的控制項，名為*複合控制項*，或*使用者控制項*。 如需 WPF 使用者控制項的詳細資訊，請參閱 <xref:System.Windows.Controls.UserControl>。  
  
> [!NOTE]
>  WPF 的 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 類型不同於 Windows Form 所提供的使用者控制項類型 (又稱為 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>)。  
  
#### <a name="to-create-a-new-wpf-control"></a>建立新的 WPF 控制項  
  
1.  在**方案總管 中**，加入新**WPF 使用者控制項程式庫**專案加入方案。 使用控制項程式庫的預設名稱 `WpfControlLibrary1`。 預設控制項名稱為 `UserControl1.xaml`。  
  
     加入新的控制項具有下列效果。  
  
    -   會加入 UserControl1.xaml 檔案。  
  
    -   會加入 UserControl1.xaml.cs 或 UserControl1.xaml.vb 檔案。 這個檔案包含事件處理常式和其他實作的程式碼後置。  
  
    -   會加入 WPF 組件的參考。  
  
    -   UserControl1.xaml 檔案會在 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] 中開啟。  
  
2.  在 [設計] 檢視中，確定已選取 `UserControl1`。 如需詳細資訊，請參閱[如何： 選取並在設計介面上的 移動項目](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)。  
  
3.  在**屬性**視窗中，設定的值<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>屬性`200`。  
  
4.  從**工具箱**，拖曳<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>控制項拖曳至設計介面。  
  
5.  在**屬性**視窗中，設定的值<xref:System.Windows.Controls.TextBox.Text%2A>屬性**裝載內容**。  
  
    > [!NOTE]
    >  一般而言，您應該裝載更複雜的 WPF 內容。 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控制項在此僅供說明用途使用。  
  
6.  建置專案。  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a>將 WPF 控制項加入 Windows Form  
 您的新 WPF 控制項已經準備好在表單上使用。 Windows Form 會使用 <xref:System.Windows.Forms.Integration.ElementHost> 控制項裝載 WPF 內容。  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a>將 WPF 控制項加入 Windows Form  
  
1.  在 Windows Form 設計工具中開啟 `Form1`。  
  
2.  在**工具箱**，尋找 索引標籤**WPFUserControlLibrary WPF 使用者控制項**。  
  
3.  將 `UserControl1` 的執行個體拖曳到表單上。  
  
    -   <xref:System.Windows.Forms.Integration.ElementHost> 控制項會在表單上自動建立，以裝載 WPF 控制項。  
  
    -   <xref:System.Windows.Forms.Integration.ElementHost>控制項名為`elementHost1`和**屬性**視窗中，您可以看到其<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>屬性設定為**UserControl1**。  
  
    -   WPF 組件的參考會加入專案中。  
  
    -   `elementHost1` 控制項具有智慧標籤面板，這個面板會顯示可用的裝載選項。  
  
4.  在**ElementHost 工作**智慧標籤面板中，選取**停駐於父容器**。  
  
5.  按 F5 鍵建置並執行應用程式。  
  
## <a name="next-steps"></a>後續步驟  
 Windows Form 和 WPF 是不同的技術，不過可以藉由設計密切地相互操作。 若要在應用程式中提供更豐富的外觀和行為，請嘗試下列方法。  
  
-   將 Windows Form 控制項裝載到 WPF 頁面中。 如需詳細資訊，請參閱[逐步解說： 在 WPF 中將 Windows Form 控制項裝載](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)。  
  
-   將 Windows Form 視覺化樣式套用至 WPF 內容。 如需詳細資訊，請參閱[如何：在混合應用程式中啟用視覺化樣式](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)。  
  
-   變更 WPF 內容的樣式。 如需詳細資訊，請參閱[逐步解說： 設定樣式的 WPF 內容](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [移轉和互通性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [使用 WPF 控制項](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF 設計工具](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
