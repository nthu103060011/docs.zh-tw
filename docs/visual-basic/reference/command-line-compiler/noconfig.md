---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: bce2d98a8915e80cdecd7b67029b0c872cf70140
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="-noconfig"></a>-noconfig
指定的編譯器不應該自動參考常用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]組件或匯入`System`和`Microsoft.VisualBasic`命名空間。  
  
## <a name="syntax"></a>語法  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>備註  
 `-noconfig`選項會指示編譯器不要使用 Vbc.rsp 檔案，位於與 Vbc.exe 檔案相同的目錄中進行編譯。 Vbc.rsp 檔案進行參考常用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]組件和匯入`System`和`Microsoft.VisualBasic`命名空間。 編譯器隱含參考之 System.dll 組件，除非`-nostdlib`指定選項。 `-nostdlib`選項會告知編譯器不要使用 vbc.rsp 進行編譯，或自動參考之 System.dll 組件。  
  
> [!NOTE]
>  一律會參考 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的組件。  
  
 您可以修改 Vbc.rsp 檔案，以指定應包含在每個 Vbc.exe 編譯的其他編譯器選項 (指定時，除非`-noconfig`選項)。 如需詳細資訊，請參閱 [@ (指定回應檔)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)。  
  
 編譯器會先處理傳遞至選項`vbc`最後一個命令。 因此，在命令列上的任何選項會覆寫中 Vbc.rsp 檔案進行的相同選項的設定。  
  
> [!NOTE]
>  `-noconfig`選項不是從 Visual Studio 開發環境中使用; 其只有在從命令列編譯時。  
  
## <a name="see-also"></a>另請參閱  
 [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [Visual Basic 命令列編譯器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [@ (指定回應檔)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [-參考 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
