---
title: "例外狀況：try...finally 運算式 (F#)"
description: "深入了解如何 F # ' try finally' 運算式可讓您執行清除程式碼，即使一段程式碼擲回例外狀況。"
keywords: "Visual F#, F#, 函式程式設計"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: af06b20c-8d87-4496-a0aa-6fdfe8b3a786
ms.openlocfilehash: 2e2445c42bf8129ea81beef56cb725ac0e37d202
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="ce29b-104">例外狀況：try...finally 運算式</span><span class="sxs-lookup"><span data-stu-id="ce29b-104">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="ce29b-105">`try...finally`運算式可讓您執行清除程式碼，即使一段程式碼擲回例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ce29b-105">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="ce29b-106">語法</span><span class="sxs-lookup"><span data-stu-id="ce29b-106">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="ce29b-107">備註</span><span class="sxs-lookup"><span data-stu-id="ce29b-107">Remarks</span></span>
<span data-ttu-id="ce29b-108">`try...finally`運算式可用來執行中的程式碼*expression2*中先前的語法，不論是否在執行期間會產生例外狀況*expression1*。</span><span class="sxs-lookup"><span data-stu-id="ce29b-108">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="ce29b-109">型別*expression2*並沒有提供完整的運算式; 的值時不會發生例外狀況傳回的類型是中的最後一個值*expression1*。</span><span class="sxs-lookup"><span data-stu-id="ce29b-109">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="ce29b-110">例外狀況發生時，會傳回任何值，並控制流程將轉移至下一個相符例外狀況處理常式的呼叫堆疊。</span><span class="sxs-lookup"><span data-stu-id="ce29b-110">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="ce29b-111">如果不找到任何例外狀況處理常式，在程式終止。</span><span class="sxs-lookup"><span data-stu-id="ce29b-111">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="ce29b-112">相符的處理常式中的程式碼會執行，或在程式終止中的程式碼之前`finally`分支執行。</span><span class="sxs-lookup"><span data-stu-id="ce29b-112">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="ce29b-113">下列程式碼會示範如何使用`try...finally`運算式。</span><span class="sxs-lookup"><span data-stu-id="ce29b-113">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="ce29b-114">以下是輸出到主控台。</span><span class="sxs-lookup"><span data-stu-id="ce29b-114">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="ce29b-115">您可以從輸出中看到之前已處理外部例外狀況，, 關閉資料流和檔案`test.txt`包含文字`test1`，指出已排清緩衝區，並寫入磁碟，即使例外狀況傳送控制外部例外狀況處理常式。</span><span class="sxs-lookup"><span data-stu-id="ce29b-115">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="ce29b-116">請注意，`try...with`建構是從個別建構`try...finally`建構。</span><span class="sxs-lookup"><span data-stu-id="ce29b-116">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="ce29b-117">因此，如果您的程式碼需要`with`區塊和`finally`區塊中，您必須將巢狀化的兩個建構，如下列程式碼範例所示。</span><span class="sxs-lookup"><span data-stu-id="ce29b-117">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="ce29b-118">在計算運算式的內容，包括 循序項運算式及非同步工作流程， **try … 最後**運算式可能會有自訂的實作。</span><span class="sxs-lookup"><span data-stu-id="ce29b-118">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="ce29b-119">如需詳細資訊，請參閱[計算運算式](../computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="ce29b-119">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="ce29b-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce29b-120">See Also</span></span>
[<span data-ttu-id="ce29b-121">例外狀況處理</span><span class="sxs-lookup"><span data-stu-id="ce29b-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="ce29b-122">例外狀況：`try...with` 運算式</span><span class="sxs-lookup"><span data-stu-id="ce29b-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)