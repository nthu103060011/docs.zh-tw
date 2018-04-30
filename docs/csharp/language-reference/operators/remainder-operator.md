---
title: '% 運算子 (C# 參考)'
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1bcbc-102">% 運算子 (C# 參考)</span><span class="sxs-lookup"><span data-stu-id="1bcbc-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="1bcbc-103">remainder 運算子 (`%`) 會計算其第一個運算元除以第二個運算元之後的餘數。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="1bcbc-104">所有數值類型都有預先定義的餘數運算子。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="1bcbc-105">備註</span><span class="sxs-lookup"><span data-stu-id="1bcbc-105">Remarks</span></span>  
 <span data-ttu-id="1bcbc-106">公式 `a % b` 一律會傳回範圍 `(-b, b)` 中的值、不含上下界值 (它永遠不會傳回 `b` 或 `-b`)，並保留被除數的正負號。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="1bcbc-107">針對整數除法，餘數運算子會滿足規則 `a % b = a - (a / b) * b`。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="1bcbc-108">這不能與標準模數混淆，標準模數符合類似的規則，但是使用浮點除法並傳回範圍 `[0, b)` 中的值。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="1bcbc-109">C# 沒有標準模數的運算子。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="1bcbc-110">不過，正值被除數的行為是一樣的。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="1bcbc-111">使用者定義型別可以多載 `%` 運算子 (請參閱 [operator](../../../csharp/language-reference/keywords/operator.md))。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="1bcbc-112">二元運算子多載時，對應的指派運算子 (若有) 也會隱含地多載。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bcbc-113">範例</span><span class="sxs-lookup"><span data-stu-id="1bcbc-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="1bcbc-114">註解</span><span class="sxs-lookup"><span data-stu-id="1bcbc-114">Comments</span></span>  
 <span data-ttu-id="1bcbc-115">請注意與 double 類型建立關聯的四捨五入錯誤。</span><span class="sxs-lookup"><span data-stu-id="1bcbc-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bcbc-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="1bcbc-116">See Also</span></span>  
 [<span data-ttu-id="1bcbc-117">C# 參考</span><span class="sxs-lookup"><span data-stu-id="1bcbc-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1bcbc-118">C# 程式設計指南</span><span class="sxs-lookup"><span data-stu-id="1bcbc-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1bcbc-119">C# 運算子</span><span class="sxs-lookup"><span data-stu-id="1bcbc-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)