---
title: '&amp; 運算子 (C# 參考)'
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 59813b4bc5781776c9f9741c3e49e660c684bff9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="amp-operator-c-reference"></a>&amp; 運算子 (C# 參考)
`&` 運算子可以作為一元或二元運算子。  
  
## <a name="remarks"></a>備註  
 一元 `&` 運算子會傳回運算元的位址 (需要 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 內容)。  
  
 整數型別和 `bool` 會預先定義二元 `&` 運算子。 對於整數型別，& 會計算其運算元的邏輯位元 AND。 對於 `bool` 運算元，& 會計算其運算元的邏輯 AND；亦即，如果且唯有當其兩個運算元都是 `true` 時，結果會是 `true`。  
  
 二元 `&` 運算子不同於[條件式 AND 運算子](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`，它會評估兩個運算子，而不論第一個運算子的值為何。 例如:   
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 使用者定義型別可以多載二進位 `&` 運算子 (請參閱 [operator](../../../csharp/language-reference/keywords/operator.md))。 整數類資料類型上的作業通常允許用於列舉型別。 二元運算子多載時，對應的指派運算子 (若有) 也會隱含地多載。  
  
## <a name="example"></a>範例  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a>請參閱  
 [C# 參考](../../../csharp/language-reference/index.md)  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [C# 運算子](../../../csharp/language-reference/operators/index.md)
