---
title: 巢狀控制結構 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: ec3d4d477290480cdfa0f5b1c88aa82c81040d11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="nested-control-structures-visual-basic"></a>巢狀控制結構 (Visual Basic)
您可以將放控制陳述式內部的其他控制陳述式，例如`If...Then...Else`區塊內`For...Next`迴圈。 放在另一個控制陳述式內的控制陳述式即為*巢狀*。  
  
## <a name="nesting-levels"></a>巢狀層級  
 在 Visual Basic 中的控制結構可以是巢狀的層級您的需要。 它是常見的作法是藉由縮排每一個主體，讓巢狀的結構更容易閱讀。 整合式的開發環境 (IDE) 編輯器會自動執行此。  
  
 在下列範例中，此程序`sumRows`一起正值會將元素加入每個資料列的矩陣。  
  
```  
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 在上述範例中，第一個`Next`陳述式會關閉內部`For`迴圈和最後一個`Next`陳述式會關閉外部`For`迴圈。  
  
 同樣地，在巢狀`If`陳述式，`End If`陳述式會自動套用至最接近之前`If`陳述式。 巢狀`Do`適用於類似的方式，最內層的迴圈`Loop`陳述式比對最內層`Do`陳述式。  
  
> [!NOTE]
>  許多控制項結構，當您按一下關鍵字，所有的結構中的關鍵字會反白顯示。 比方說，當您按一下`If`中`If...Then...Else`建構的所有執行個體`If`， `Then`， `ElseIf`， `Else`，和`End If`建構中會反白顯示。 若要移至下一頁或上一頁反白顯示關鍵字，請按 CTRL + SHIFT + 向下鍵或 CTRL + SHIFT + 向上鍵。  
  
## <a name="nesting-different-kinds-of-control-structures"></a>巢狀方式置於不同種類的控制結構  
 您可以巢狀控制結構中其他類型的一種。 下列範例會使用`With`封鎖內`For Each`迴圈及巢狀`If`封鎖內`With`區塊。  
  
```  
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a>重疊的控制結構  
 您不能重疊控制結構。 這表示任何巢狀的結構必須完全包含在下一個最內層結構內。 例如，下列的排列方式不正確因為`For`迴圈終止之前內部`With`區塊會結束。  
  
 ![無效巢狀處理示意圖](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")  
無效的巢狀結構和結構  
  
 Visual Basic 編譯器會偵測這類重疊的控制結構，並發出編譯時期錯誤。  
  
## <a name="see-also"></a>另請參閱  
 [控制流程](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [決策結構](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [迴圈結構](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [其他控制結構](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
