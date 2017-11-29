---
title: "轉型和轉換 (F#)"
description: "了解如何 F # 程式語言提供的轉換運算子的各種基本型別之間的算術轉換。"
keywords: "Visual F#, F#, 函式程式設計"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: f17d3919c59c5881213d28a59cea7ae184493949
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="85a40-104">轉型和轉換 (F#)</span><span class="sxs-lookup"><span data-stu-id="85a40-104">Casting and Conversions (F#)</span></span>

<span data-ttu-id="85a40-105">本主題描述支援 F # 中的型別轉換。</span><span class="sxs-lookup"><span data-stu-id="85a40-105">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="85a40-106">算術類型</span><span class="sxs-lookup"><span data-stu-id="85a40-106">Arithmetic Types</span></span>
<span data-ttu-id="85a40-107">F # 提供的轉換運算子算術轉換之間各種基本型別，例如整數和浮點類型之間。</span><span class="sxs-lookup"><span data-stu-id="85a40-107">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="85a40-108">整數類資料類型和 char 的轉換運算子有核取及取消核取的表單。浮點運算子和`enum`轉換運算子不這麼做。</span><span class="sxs-lookup"><span data-stu-id="85a40-108">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="85a40-109">若未選取的表單中定義`Microsoft.FSharp.Core.Operators`且已檢查的表單定義於`Microsoft.FSharp.Core.Operators.Checked`。</span><span class="sxs-lookup"><span data-stu-id="85a40-109">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="85a40-110">選取的表單溢位檢查，並產生執行階段例外狀況，如果產生的值超過限制的目標類型。</span><span class="sxs-lookup"><span data-stu-id="85a40-110">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="85a40-111">每個這些運算子有相同名稱做為目的地類型的名稱。</span><span class="sxs-lookup"><span data-stu-id="85a40-111">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="85a40-112">例如，在下列程式碼中的類型必須明確標註，`byte`與兩個不同的意義會出現。</span><span class="sxs-lookup"><span data-stu-id="85a40-112">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="85a40-113">第一個型別，而第二個轉換運算子。</span><span class="sxs-lookup"><span data-stu-id="85a40-113">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="85a40-114">下表顯示 F # 中定義的轉換運算子。</span><span class="sxs-lookup"><span data-stu-id="85a40-114">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="85a40-115">運算子</span><span class="sxs-lookup"><span data-stu-id="85a40-115">Operator</span></span>|<span data-ttu-id="85a40-116">說明</span><span class="sxs-lookup"><span data-stu-id="85a40-116">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="85a40-117">將轉換成 byte、 8 位元不帶正負號類型。</span><span class="sxs-lookup"><span data-stu-id="85a40-117">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="85a40-118">將轉換成帶正負號的位元組。</span><span class="sxs-lookup"><span data-stu-id="85a40-118">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="85a40-119">將轉換成 16 位元帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="85a40-119">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="85a40-120">將轉換成 16 位元不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="85a40-120">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="85a40-121">將轉換為 32 位元帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="85a40-121">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="85a40-122">將轉換為 32 位元不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="85a40-122">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="85a40-123">將轉換為 64 位元帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="85a40-123">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="85a40-124">將轉換為 64 位元不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="85a40-124">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="85a40-125">將轉換成原生的整數。</span><span class="sxs-lookup"><span data-stu-id="85a40-125">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="85a40-126">將轉換成原生不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="85a40-126">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="85a40-127">將轉換為 64 位元雙精度 IEEE 浮點數。</span><span class="sxs-lookup"><span data-stu-id="85a40-127">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="85a40-128">將轉換為 32 位元單精確度 IEEE 浮點數。</span><span class="sxs-lookup"><span data-stu-id="85a40-128">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="85a40-129">將轉換成`System.Decimal`。</span><span class="sxs-lookup"><span data-stu-id="85a40-129">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="85a40-130">將轉換成`System.Char`，Unicode 字元。</span><span class="sxs-lookup"><span data-stu-id="85a40-130">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="85a40-131">轉換為列舉類型。</span><span class="sxs-lookup"><span data-stu-id="85a40-131">Convert to an enumerated type.</span></span>|
<span data-ttu-id="85a40-132">除了內建基本類型，您可以使用這些運算子實作的型別與`op_Explicit`或`op_Implicit`具有適當簽章的方法。</span><span class="sxs-lookup"><span data-stu-id="85a40-132">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="85a40-133">例如，`int`轉換運算子搭配任何類型，提供靜態方法`op_Explicit`採用做為參數的型別，並傳回`int`。</span><span class="sxs-lookup"><span data-stu-id="85a40-133">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="85a40-134">為一般的規則不傳回型別多載方法的特殊例外狀況，您可以`op_Explicit`和`op_Implicit`。</span><span class="sxs-lookup"><span data-stu-id="85a40-134">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="85a40-135">列舉的類型</span><span class="sxs-lookup"><span data-stu-id="85a40-135">Enumerated Types</span></span>
<span data-ttu-id="85a40-136">`enum`運算子是採用一個代表類型的型別參數的泛型運算子`enum`轉換。</span><span class="sxs-lookup"><span data-stu-id="85a40-136">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="85a40-137">當轉換為列舉類型時，類型推斷嘗試判斷型別`enum`您想要轉換成。</span><span class="sxs-lookup"><span data-stu-id="85a40-137">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="85a40-138">在下列範例中，變數`col1`沒有明確標註，但其類型會推斷從更新版本的等號比較測試。</span><span class="sxs-lookup"><span data-stu-id="85a40-138">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="85a40-139">因此，編譯器可以減少您轉換成`Color`列舉型別。</span><span class="sxs-lookup"><span data-stu-id="85a40-139">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="85a40-140">或者，您可以提供類型註釋，如同`col2`在下列範例中。</span><span class="sxs-lookup"><span data-stu-id="85a40-140">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
<span data-ttu-id="85a40-141">您也可以明確指定的目標列舉型別與型別參數，如下列程式碼所示：</span><span class="sxs-lookup"><span data-stu-id="85a40-141">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="85a40-142">請注意，列舉型別會轉換為工作只有在列舉的基礎類型是轉換的類型相容。</span><span class="sxs-lookup"><span data-stu-id="85a40-142">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="85a40-143">下列程式碼，則轉換會失敗編譯因為之間不相符`int32`和`uint32`。</span><span class="sxs-lookup"><span data-stu-id="85a40-143">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="85a40-144">如需詳細資訊，請參閱[列舉](enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="85a40-144">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="85a40-145">轉型物件類型</span><span class="sxs-lookup"><span data-stu-id="85a40-145">Casting Object Types</span></span>
<span data-ttu-id="85a40-146">物件階層中的類型之間的轉換是對物件導向程式設計基礎。</span><span class="sxs-lookup"><span data-stu-id="85a40-146">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="85a40-147">有兩個基本類型的轉換: （向上轉型） 向上轉型及向下 （向下轉型） 轉型。</span><span class="sxs-lookup"><span data-stu-id="85a40-147">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="85a40-148">階層架構中向上轉型表示從衍生的物件參考的基底物件參考的轉型。</span><span class="sxs-lookup"><span data-stu-id="85a40-148">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="85a40-149">這類轉換保證可以運作，只要基底類別是在衍生類別的繼承階層架構中。</span><span class="sxs-lookup"><span data-stu-id="85a40-149">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="85a40-150">從衍生的物件參考的基底物件參考的階層中向轉型成功只有物件實際上是正確的目的地 （衍生） 型別或目的型別衍生之類型的執行個體。</span><span class="sxs-lookup"><span data-stu-id="85a40-150">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="85a40-151">F # 提供這些類型之轉換的運算子。</span><span class="sxs-lookup"><span data-stu-id="85a40-151">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="85a40-152">`:>`運算子會轉換為階層中往上和`:?>`運算子會轉換為階層中向下。</span><span class="sxs-lookup"><span data-stu-id="85a40-152">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="85a40-153">向上轉型</span><span class="sxs-lookup"><span data-stu-id="85a40-153">Upcasting</span></span>
<span data-ttu-id="85a40-154">在許多物件導向語言中，向上轉型是隱含的;F # 中的規則有些許不同。</span><span class="sxs-lookup"><span data-stu-id="85a40-154">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="85a40-155">將引數傳遞給方法的物件類型時，會自動套用向上轉型。</span><span class="sxs-lookup"><span data-stu-id="85a40-155">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="85a40-156">不過，對於在模組中的 let 繫結函式，向上轉型不是自動，除非參數型別宣告為有彈性的類型。</span><span class="sxs-lookup"><span data-stu-id="85a40-156">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="85a40-157">如需詳細資訊，請參閱[彈性類型](flexible-Types.md)。</span><span class="sxs-lookup"><span data-stu-id="85a40-157">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="85a40-158">`:>`運算子會執行轉換，這表示成功的轉型由決定在編譯時期靜態。</span><span class="sxs-lookup"><span data-stu-id="85a40-158">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="85a40-159">如果使用 cast`:>`會編譯成功，它是有效的轉換，在執行階段有未故障的時候。</span><span class="sxs-lookup"><span data-stu-id="85a40-159">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="85a40-160">您也可以使用`upcast`運算子來執行這類轉換。</span><span class="sxs-lookup"><span data-stu-id="85a40-160">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="85a40-161">下列運算式會指定在階層中向上轉換：</span><span class="sxs-lookup"><span data-stu-id="85a40-161">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="85a40-162">當您使用 upcast 運算子時，編譯器會嘗試推斷您從內容轉換成的型別。</span><span class="sxs-lookup"><span data-stu-id="85a40-162">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="85a40-163">如果編譯器無法判斷目標類型，編譯器會報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="85a40-163">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="85a40-164">向下轉型</span><span class="sxs-lookup"><span data-stu-id="85a40-164">Downcasting</span></span>
<span data-ttu-id="85a40-165">`:?>`運算子會執行轉換，這表示成功的轉型會在執行階段決定的動態。</span><span class="sxs-lookup"><span data-stu-id="85a40-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="85a40-166">使用 cast`:?>`運算子不會檢查在編譯時期; 但在執行階段，嘗試轉型為指定的型別。</span><span class="sxs-lookup"><span data-stu-id="85a40-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="85a40-167">如果物件是相容的目標類型，轉換就會成功。</span><span class="sxs-lookup"><span data-stu-id="85a40-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="85a40-168">如果物件不相容於目標型別，就會引發執行階段`InvalidCastException`。</span><span class="sxs-lookup"><span data-stu-id="85a40-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="85a40-169">您也可以使用`downcast`運算子來執行動態類型轉換。</span><span class="sxs-lookup"><span data-stu-id="85a40-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="85a40-170">下列運算式會指定從程式內容推斷的型別階層中向下轉換：</span><span class="sxs-lookup"><span data-stu-id="85a40-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="85a40-171">與`upcast`運算子，如果編譯器無法推斷特定目標類型從內容，則會回報錯誤。</span><span class="sxs-lookup"><span data-stu-id="85a40-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="85a40-172">下列程式碼說明如何使用`:>`和`:?>`運算子。</span><span class="sxs-lookup"><span data-stu-id="85a40-172">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="85a40-173">程式碼會說明`:?>`運算子最適合在您知道轉換成功，因為它會擲回`InvalidCastException`如果轉換失敗。</span><span class="sxs-lookup"><span data-stu-id="85a40-173">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="85a40-174">如果您不知道，轉換會成功，會使用的型別測試`match`運算式是更好，因為它可避免產生例外狀況的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="85a40-174">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="85a40-175">因為泛型運算子`downcast`和`upcast`依賴類型推斷來判斷引數和傳回型別，上述程式碼中的，您可以取代</span><span class="sxs-lookup"><span data-stu-id="85a40-175">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="85a40-176">取代為</span><span class="sxs-lookup"><span data-stu-id="85a40-176">with</span></span>

```fsharp
base1 = upcast d1
```

<span data-ttu-id="85a40-177">在先前的程式碼中，引數類型和傳回型別是`Derived1`和`Base1`分別。</span><span class="sxs-lookup"><span data-stu-id="85a40-177">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="85a40-178">如需類型測試的詳細資訊，請參閱[比對運算式](match-Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="85a40-178">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="85a40-179">另請參閱</span><span class="sxs-lookup"><span data-stu-id="85a40-179">See Also</span></span>
[<span data-ttu-id="85a40-180">F# 語言參考</span><span class="sxs-lookup"><span data-stu-id="85a40-180">F# Language Reference</span></span>](index.md)