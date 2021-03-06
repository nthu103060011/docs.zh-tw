---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36b2cba14f15cebdcc7f371f53f46b657ab12758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="-netcf"></a>-netcf
設定要以 [!INCLUDE[Compact](~/includes/compact-md.md)] 為目標的編譯器。  
  
## <a name="syntax"></a>語法  
  
```  
-netcf  
```  
  
## <a name="remarks"></a>備註  
 `-netcf`選項會設為目標的 Visual Basic 編譯器[!INCLUDE[Compact](~/includes/compact-md.md)]而不是完整[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。 語言功能只有在完整存在於[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]已停用。  
  
 `-netcf`選項設計來搭配[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)。 停用的語言功能`-netcf`都是相同的目標檔案中沒有的語言功能`-sdkpath`。  
  
> [!NOTE]
>  `-netcf`選項不是從 Visual Studio 開發環境中使用; 其只有在從命令列編譯時。 `-netcf` Visual Basic 裝置專案載入時，設定選項。  
  
 `-netcf`選項會變更具有下列語言功能：  
  
-   [結束\<關鍵字 > 陳述式](../../../visual-basic/language-reference/statements/end-keyword-statement.md)關鍵字，終止程式執行時，會停用。 下列程式會編譯並執行時不會`-netcf`會在編譯階段失敗，但`-netcf`。  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   晚期繫結中所有表單中，已停用。 遇到已辨識的晚期繫結情節時，會產生編譯時期錯誤。 下列程式會編譯並執行時不會`-netcf`會在編譯階段失敗，但`-netcf`。  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   [自動](../../../visual-basic/language-reference/modifiers/auto.md)， [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)，和[Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)修飾詞會停用。 語法[Declare 陳述式](../../../visual-basic/language-reference/statements/declare-statement.md)陳述式也修改成`Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`。 下列程式碼顯示的效果`-netcf`編譯。  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   使用 Visual Basic 中已移除的 Visual Basic 6.0 關鍵字會產生不同的錯誤時`-netcf`用。 這會影響下列關鍵字的錯誤訊息：  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a>範例  
 下列程式碼編譯`Myfile.vb`與[!INCLUDE[Compact](~/includes/compact-md.md)]，使用 mscorlib.dll 和 Microsoft.VisualBasic.dll 的版本中的預設安裝目錄中找到[!INCLUDE[Compact](~/includes/compact-md.md)]C 磁碟機上。 一般而言，您可使用的最新版本[!INCLUDE[Compact](~/includes/compact-md.md)]。  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>另請參閱  
 [Visual Basic 命令列編譯器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [編譯命令列範例](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
