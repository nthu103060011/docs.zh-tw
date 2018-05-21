---
title: 'F # 程式碼格式化方針'
description: '了解 F # 程式碼格式化方針。'
ms.date: 05/14/2018
ms.openlocfilehash: 1433b6891a6a0ddcdc082c141365ae54fa40c27b
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2018
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="b307f-103">F # 程式碼格式化方針</span><span class="sxs-lookup"><span data-stu-id="b307f-103">F# code formatting guidelines</span></span>

<span data-ttu-id="b307f-104">這篇文章提供如何格式化您的程式碼，讓 F # 程式碼的指導方針：</span><span class="sxs-lookup"><span data-stu-id="b307f-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="b307f-105">通常以更易於閱讀檢視</span><span class="sxs-lookup"><span data-stu-id="b307f-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="b307f-106">會根據套用的 Visual Studio 中的工具和其他編輯器格式設定慣例</span><span class="sxs-lookup"><span data-stu-id="b307f-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="b307f-107">類似於線上的其他程式碼</span><span class="sxs-lookup"><span data-stu-id="b307f-107">Similar to other code online</span></span>

<span data-ttu-id="b307f-108">這些方針根據[F # 格式設定慣例的完整指南](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)由[Anh 盜賊藩](https://github.com/dungpa)。</span><span class="sxs-lookup"><span data-stu-id="b307f-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="b307f-109">縮排的一般規則</span><span class="sxs-lookup"><span data-stu-id="b307f-109">General rules for indentation</span></span>

<span data-ttu-id="b307f-110">F # 預設會使用空白字元。</span><span class="sxs-lookup"><span data-stu-id="b307f-110">F# uses significant whitespace by default.</span></span> <span data-ttu-id="b307f-111">下列指導方針均提供指導方針來選擇龐大這也可能造成的一些挑戰。</span><span class="sxs-lookup"><span data-stu-id="b307f-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="b307f-112">使用空間</span><span class="sxs-lookup"><span data-stu-id="b307f-112">Using spaces</span></span>

<span data-ttu-id="b307f-113">需要縮排時，您必須使用空間，而不是索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b307f-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="b307f-114">需要至少一個空白字元。</span><span class="sxs-lookup"><span data-stu-id="b307f-114">At least one space is required.</span></span> <span data-ttu-id="b307f-115">您的組織可以建立以指定要用來縮排; 的空格數目編碼標準通常會發生縮排每個層級的縮排的兩個、 三或四個空格。</span><span class="sxs-lookup"><span data-stu-id="b307f-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="b307f-116">**我們建議您縮排每 4 個空格。**</span><span class="sxs-lookup"><span data-stu-id="b307f-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="b307f-117">話雖如此，縮排程式是主觀。</span><span class="sxs-lookup"><span data-stu-id="b307f-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="b307f-118">變化 [確定]，但是您應該遵循的第一個規則*縮排的一致性*。</span><span class="sxs-lookup"><span data-stu-id="b307f-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="b307f-119">選擇公認的縮排樣式，並在整個程式碼基底有系統地使用它。</span><span class="sxs-lookup"><span data-stu-id="b307f-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="b307f-120">格式化差別等位宣告</span><span class="sxs-lookup"><span data-stu-id="b307f-120">Formatting discriminated union declarations</span></span>

<span data-ttu-id="b307f-121">縮排`|`由 4 個空格的類型定義中：</span><span class="sxs-lookup"><span data-stu-id="b307f-121">Indent `|` in type definition by 4 spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

<span data-ttu-id="b307f-122">具現化差別等位分成多行，應該提供包含的資料包含縮排新的範圍：</span><span class="sxs-lookup"><span data-stu-id="b307f-122">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="b307f-123">右括號也可以是新的一行：</span><span class="sxs-lookup"><span data-stu-id="b307f-123">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-tuples"></a><span data-ttu-id="b307f-124">Tuple 的格式化</span><span class="sxs-lookup"><span data-stu-id="b307f-124">Formatting tuples</span></span>

<span data-ttu-id="b307f-125">Tuple 的具現化應該是括號括住，而且內分隔逗號後面必須接著一個空格，例如： `(1, 2)`， `(x, y, z)`。</span><span class="sxs-lookup"><span data-stu-id="b307f-125">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="b307f-126">普遍接受的例外狀況是 tuple 的省略括號中的模式比對：</span><span class="sxs-lookup"><span data-stu-id="b307f-126">A commonly accepted exception is to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a><span data-ttu-id="b307f-127">格式化的資料錄</span><span class="sxs-lookup"><span data-stu-id="b307f-127">Formatting records</span></span>

<span data-ttu-id="b307f-128">簡短的記錄可以撰寫在一行中：</span><span class="sxs-lookup"><span data-stu-id="b307f-128">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="b307f-129">記錄的長度應該使用新行的標籤：</span><span class="sxs-lookup"><span data-stu-id="b307f-129">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="b307f-130">將左語彙基元放在同一行和新的一行的結尾語彙基元是也可以：</span><span class="sxs-lookup"><span data-stu-id="b307f-130">Placing the opening token on the same line and the closing token on a new line is also fine:</span></span>

```fsharp
let rainbow = {
    Boss1 = "Jeffrey"
    Boss2 = "Jeffrey"
    Boss3 = "Jeffrey"
    Boss4 = "Jeffrey"
    Boss5 = "Jeffrey"
    Boss6 = "Jeffrey"
    Boss7 = "Jeffrey"
    Boss8 = "Jeffrey"
    Lackeys = ["Zippy"; "George"; "Bungle"]
}
```

<span data-ttu-id="b307f-131">清單和陣列項目套用相同的規則。</span><span class="sxs-lookup"><span data-stu-id="b307f-131">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="b307f-132">格式設定清單和陣列</span><span class="sxs-lookup"><span data-stu-id="b307f-132">Formatting lists and arrays</span></span>

<span data-ttu-id="b307f-133">寫入`x :: l`前後的空格與`::`運算子 (`::`是中置運算子，因此，以空格) 和`[1; 2; 3]`(`;`是分隔符號，因此後接空格)。</span><span class="sxs-lookup"><span data-stu-id="b307f-133">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces) and `[1; 2; 3]` (`;` is a delimiter, hence followed by a space).</span></span>

<span data-ttu-id="b307f-134">一律使用至少一個兩個不同的大括號類似運算子之間的空間。</span><span class="sxs-lookup"><span data-stu-id="b307f-134">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="b307f-135">例如，將保留之間的空格`[`和`{`。</span><span class="sxs-lookup"><span data-stu-id="b307f-135">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="b307f-136">清單和陣列分成多行，請依照下列類似的規則一樣記錄：</span><span class="sxs-lookup"><span data-stu-id="b307f-136">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a><span data-ttu-id="b307f-137">如果格式運算式</span><span class="sxs-lookup"><span data-stu-id="b307f-137">Formatting if expressions</span></span>

<span data-ttu-id="b307f-138">縮排的條件取決於它們構成的運算式的大小。</span><span class="sxs-lookup"><span data-stu-id="b307f-138">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="b307f-139">如果`cond`，`e1`和`e2`很小，只要將它們寫入在一行上：</span><span class="sxs-lookup"><span data-stu-id="b307f-139">If `cond`, `e1` and `e2` are small, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="b307f-140">如果`e1`和`cond`很小，但`e2`大：</span><span class="sxs-lookup"><span data-stu-id="b307f-140">If `e1` and `cond` are small, but `e2` is large:</span></span>

```fsharp
if cond then e1
else
    e2
```

<span data-ttu-id="b307f-141">如果`e1`和`cond`大和`e2`小：</span><span class="sxs-lookup"><span data-stu-id="b307f-141">If `e1` and `cond` are large and `e2` is small:</span></span>

```fsharp
if cond then
    e1
else e2
```

<span data-ttu-id="b307f-142">如果所有運算式都是大型的：</span><span class="sxs-lookup"><span data-stu-id="b307f-142">If all the expressions are large:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="b307f-143">使用多個條件`elif`和`else`縮排在相同範圍`if`:</span><span class="sxs-lookup"><span data-stu-id="b307f-143">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="b307f-144">模式比對的建構</span><span class="sxs-lookup"><span data-stu-id="b307f-144">Pattern matching constructs</span></span>

<span data-ttu-id="b307f-145">使用`|`相符項目的每個子句不縮排。</span><span class="sxs-lookup"><span data-stu-id="b307f-145">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="b307f-146">如果運算式是短，您可以使用單行。</span><span class="sxs-lookup"><span data-stu-id="b307f-146">If the expression is short, you can use a single line.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"

// OK
match l with [] -> false | _ :: _ -> true
```

<span data-ttu-id="b307f-147">如果在模式比對箭號右邊的運算式太大，將它移至下列的行縮排一個步驟，從`match` / `|`。</span><span class="sxs-lookup"><span data-stu-id="b307f-147">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="b307f-148">模式比對的匿名函式，來啟動`function`，應該通常不縮排太遠。</span><span class="sxs-lookup"><span data-stu-id="b307f-148">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="b307f-149">例如，縮排一個範圍，如下所示是可以：</span><span class="sxs-lookup"><span data-stu-id="b307f-149">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="b307f-150">模式比對所定義的函式中`let`或`let rec`之後開始進行縮排 4 個空格`let`，即使`function`關鍵字使用：</span><span class="sxs-lookup"><span data-stu-id="b307f-150">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="b307f-151">我們不建議對齊箭號。</span><span class="sxs-lookup"><span data-stu-id="b307f-151">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="b307f-152">格式化的 try / with 運算式</span><span class="sxs-lookup"><span data-stu-id="b307f-152">Formatting try/with expressions</span></span>

<span data-ttu-id="b307f-153">模式比對的例外狀況類型，應該在相同的層級縮排`with`。</span><span class="sxs-lookup"><span data-stu-id="b307f-153">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="b307f-154">格式函式參數的應用程式</span><span class="sxs-lookup"><span data-stu-id="b307f-154">Formatting function parameter application</span></span>

<span data-ttu-id="b307f-155">一般而言，大部分函式參數的應用程式是在同一行。</span><span class="sxs-lookup"><span data-stu-id="b307f-155">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="b307f-156">如果您想要套用至新的一行函式的參數，則縮排一個領域。</span><span class="sxs-lookup"><span data-stu-id="b307f-156">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="b307f-157">匿名函式引數可以是下一行，或使用懸空`fun`引數的一行：</span><span class="sxs-lookup"><span data-stu-id="b307f-157">Anonymous function arguments can be either on next line or with a dangling `fun` on the argument line:</span></span>

```fsharp
// OK
let printListWithOffset a list1 =
    List.iter (fun elem ->
        printfn "%d" (a + elem)) list1

// OK, but prefer previous
let printListWithOffset a list1 =
    List.iter (
        fun elem ->
            printfn "%d" (a + elem)) list1
```

### <a name="formatting-infix-operators"></a><span data-ttu-id="b307f-158">格式化的中置運算子</span><span class="sxs-lookup"><span data-stu-id="b307f-158">Formatting infix operators</span></span>

<span data-ttu-id="b307f-159">以空格分開的運算子。</span><span class="sxs-lookup"><span data-stu-id="b307f-159">Separate operators by spaces.</span></span> <span data-ttu-id="b307f-160">此規則的明顯例外狀況是`!`和`.`運算子。</span><span class="sxs-lookup"><span data-stu-id="b307f-160">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="b307f-161">中置運算式是在相同的資料行上的內容 [確定]:</span><span class="sxs-lookup"><span data-stu-id="b307f-161">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="b307f-162">格式設定管線運算子</span><span class="sxs-lookup"><span data-stu-id="b307f-162">Formatting pipeline operators</span></span>

<span data-ttu-id="b307f-163">管線`|>`運算子都應之下操作的運算式。</span><span class="sxs-lookup"><span data-stu-id="b307f-163">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="b307f-164">格式化的模組</span><span class="sxs-lookup"><span data-stu-id="b307f-164">Formatting modules</span></span>

<span data-ttu-id="b307f-165">在本機的模組中的程式碼必須縮排相對於模組，但應該不會縮排在最上層的模組中的程式碼。</span><span class="sxs-lookup"><span data-stu-id="b307f-165">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="b307f-166">命名空間元素不具有縮排。</span><span class="sxs-lookup"><span data-stu-id="b307f-166">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="b307f-167">格式化的物件運算式和介面</span><span class="sxs-lookup"><span data-stu-id="b307f-167">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="b307f-168">物件運算式和介面應該有相同的方式對齊`member`要縮排後 4 個空格。</span><span class="sxs-lookup"><span data-stu-id="b307f-168">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a><span data-ttu-id="b307f-169">格式運算式中的空白字元</span><span class="sxs-lookup"><span data-stu-id="b307f-169">Formatting whitespace in expressions</span></span>

<span data-ttu-id="b307f-170">請避免多餘的空白字元，F # 運算式中。</span><span class="sxs-lookup"><span data-stu-id="b307f-170">Avoid extraneous whitespace in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="b307f-171">具名引數也不應該有周圍的空間`=`:</span><span class="sxs-lookup"><span data-stu-id="b307f-171">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="b307f-172">格式化空白行</span><span class="sxs-lookup"><span data-stu-id="b307f-172">Formatting blank lines</span></span>

* <span data-ttu-id="b307f-173">個別最上層函式和類別定義具有兩個空白的行。</span><span class="sxs-lookup"><span data-stu-id="b307f-173">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="b307f-174">在類別內的方法定義會以單一的空白列分隔。</span><span class="sxs-lookup"><span data-stu-id="b307f-174">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="b307f-175">額外的空白的線條可能謹慎 （） 來分隔的相關函式群組。</span><span class="sxs-lookup"><span data-stu-id="b307f-175">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="b307f-176">一堆相關 one-liners （例如，一組虛擬實作） 之間，可能會省略空白的行。</span><span class="sxs-lookup"><span data-stu-id="b307f-176">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="b307f-177">用於空白的行在函數中，謹慎使用，表示邏輯區段。</span><span class="sxs-lookup"><span data-stu-id="b307f-177">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="b307f-178">格式化的註解</span><span class="sxs-lookup"><span data-stu-id="b307f-178">Formatting comments</span></span>

<span data-ttu-id="b307f-179">通常，而不用多個雙斜線註解 ML 樣式區塊註解。</span><span class="sxs-lookup"><span data-stu-id="b307f-179">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    Generally avoid these kinds of comments.
*)
```

<span data-ttu-id="b307f-180">內嵌註解應該將第一個字母變成大寫。</span><span class="sxs-lookup"><span data-stu-id="b307f-180">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="b307f-181">命名規範</span><span class="sxs-lookup"><span data-stu-id="b307f-181">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="b307f-182">使用 camelCase 類別繫結、 運算式繫結和繫結模式值和函式</span><span class="sxs-lookup"><span data-stu-id="b307f-182">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="b307f-183">它通常會和接受的 F # 樣式 camelCase 用於所有名稱繫結，做為本機變數，或在模式比對和函式定義中。</span><span class="sxs-lookup"><span data-stu-id="b307f-183">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="b307f-184">本機繫結類別中的函式也應該使用 camelCase。</span><span class="sxs-lookup"><span data-stu-id="b307f-184">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="b307f-185">CamelCase 用於內部及私人模組繫結值和函式</span><span class="sxs-lookup"><span data-stu-id="b307f-185">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="b307f-186">CamelCase 用於私用模組繫結值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b307f-186">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="b307f-187">臨機操作指令碼中的函式</span><span class="sxs-lookup"><span data-stu-id="b307f-187">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="b307f-188">構成模組或類型的內部實作的值</span><span class="sxs-lookup"><span data-stu-id="b307f-188">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="b307f-189">使用 camelCase 參數</span><span class="sxs-lookup"><span data-stu-id="b307f-189">Use camelCase for parameters</span></span>

<span data-ttu-id="b307f-190">所有參數都應該都使用 camelCase 根據.NET 命名慣例。</span><span class="sxs-lookup"><span data-stu-id="b307f-190">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="b307f-191">使用 PascalCase 模組</span><span class="sxs-lookup"><span data-stu-id="b307f-191">Use PascalCase for modules</span></span>

<span data-ttu-id="b307f-192">（最上層、 內部、 私用、 巢狀） 的所有模組都應該都使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="b307f-192">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="b307f-193">PascalCase 用於宣告類型、 成員和標籤</span><span class="sxs-lookup"><span data-stu-id="b307f-193">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="b307f-194">類別、 介面、 結構、 列舉型別、 委派、 記錄和差別聯的集應該全部是名為 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="b307f-194">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="b307f-195">型別和記錄和差別聯的集的標籤內的成員也應該使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="b307f-195">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="b307f-196">PascalCase 用於建構內建的.NET</span><span class="sxs-lookup"><span data-stu-id="b307f-196">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="b307f-197">命名空間、 例外狀況、 事件和專案 /`.dll`名稱也應該使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="b307f-197">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="b307f-198">不僅這樣做耗用量其他.NET 語言的感覺更自然的取用者，也是.NET 命名慣例，系統可能會遇到與一致。</span><span class="sxs-lookup"><span data-stu-id="b307f-198">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="b307f-199">避免在名稱中的底線</span><span class="sxs-lookup"><span data-stu-id="b307f-199">Avoid underscores in names</span></span>

<span data-ttu-id="b307f-200">在過去，有些 F # 程式庫名稱中使用底線。</span><span class="sxs-lookup"><span data-stu-id="b307f-200">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="b307f-201">不過，這是不再被廣泛接受，這是因為它與.NET 的命名慣例發生衝突。</span><span class="sxs-lookup"><span data-stu-id="b307f-201">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="b307f-202">話雖如此，某些 F # 程式設計人員使用底線有很大，部分由於歷史原因，並容忍度及方面很重要。</span><span class="sxs-lookup"><span data-stu-id="b307f-202">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="b307f-203">不過，請注意樣式通常 disliked 其他人可以選擇要使用它。</span><span class="sxs-lookup"><span data-stu-id="b307f-203">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="b307f-204">有些例外狀況包含間的互通性與原生元件，其中底線很常見。</span><span class="sxs-lookup"><span data-stu-id="b307f-204">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="b307f-205">使用標準的 F # 運算子</span><span class="sxs-lookup"><span data-stu-id="b307f-205">Use standard F# operators</span></span>

<span data-ttu-id="b307f-206">下列運算子定義在 F # 標準程式庫，而且應該用於而不是定義對等項目。</span><span class="sxs-lookup"><span data-stu-id="b307f-206">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="b307f-207">因為它會使程式碼更容易讀取與慣用語，被建議使用這些運算子。</span><span class="sxs-lookup"><span data-stu-id="b307f-207">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="b307f-208">具有背景 OCaml 或其他功能的程式設計語言的開發人員可能會不同語言的習慣。</span><span class="sxs-lookup"><span data-stu-id="b307f-208">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="b307f-209">下列清單摘要說明建議的 F # 運算子。</span><span class="sxs-lookup"><span data-stu-id="b307f-209">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Throwing away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="b307f-210">使用泛型的前置詞的語法 (`Foo<T>`) 而非後置語法 (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="b307f-210">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="b307f-211">F # 繼承這兩個的後置 ML 樣式命名泛型型別 (比方說， `int list`) 以及.NET 樣式的前置詞 (例如， `list<int>`)。</span><span class="sxs-lookup"><span data-stu-id="b307f-211">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="b307f-212">偏好的.NET 樣式，除了特定的四種類型：</span><span class="sxs-lookup"><span data-stu-id="b307f-212">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="b307f-213">F # 列出，請使用後置格式：`int list`而不是`list<int>`。</span><span class="sxs-lookup"><span data-stu-id="b307f-213">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="b307f-214">使用 F # 選項，請使用 後置格式：`int option`而不是`option<int>`。</span><span class="sxs-lookup"><span data-stu-id="b307f-214">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="b307f-215">F # 陣列，使用的語法名稱`int[]`而`int array`或`array<int>`。</span><span class="sxs-lookup"><span data-stu-id="b307f-215">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="b307f-216">參考儲存格，使用`int ref`而`ref<int>`或`Ref<int>`。</span><span class="sxs-lookup"><span data-stu-id="b307f-216">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="b307f-217">對於所有其他類型，使用的前置格式。</span><span class="sxs-lookup"><span data-stu-id="b307f-217">For all other types, use the prefix form.</span></span>