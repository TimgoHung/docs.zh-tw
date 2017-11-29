---
title: "運算子多載 (F#)"
description: "了解如何在類別或記錄類型，F # 中的全域層級的算術運算子多載。"
keywords: "Visual F#, F#, 函式程式設計"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 019277ed-f649-4fa5-ad43-097865f449d9
ms.openlocfilehash: 76ddab5339e11d71bb326b60d727017eb838ccf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="operator-overloading"></a><span data-ttu-id="0ce1c-104">運算子多載</span><span class="sxs-lookup"><span data-stu-id="0ce1c-104">Operator Overloading</span></span>

<span data-ttu-id="0ce1c-105">本主題描述如何在類別或記錄類型，也可以在全域層級的算術運算子多載。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-105">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>


## <a name="syntax"></a><span data-ttu-id="0ce1c-106">語法</span><span class="sxs-lookup"><span data-stu-id="0ce1c-106">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="0ce1c-107">備註</span><span class="sxs-lookup"><span data-stu-id="0ce1c-107">Remarks</span></span>
<span data-ttu-id="0ce1c-108">在先前的語法，*運算子符號*是其中一個`+`， `-`， `*`， `/`， `=`，依此類推。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-108">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="0ce1c-109">*參數清單*它們出現在一般的語法，該運算子的順序指定的運算元。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-109">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="0ce1c-110">*方法主體*建構產生的值。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-110">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="0ce1c-111">運算子多載運算子都必須是靜態的。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-111">Operator overloads for operators must be static.</span></span> <span data-ttu-id="0ce1c-112">運算子多載一元運算子，例如`+`和`-`，必須使用波狀符號 (`~`) 中*運算子符號*來表示運算子是一元運算子和二元的運算子，如中所示下列宣告。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-112">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="0ce1c-113">下列程式碼說明只有兩個運算子的向量類別，一個運算子用於一元減號運算，一個運算子用於純量乘法。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-113">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="0ce1c-114">在範例中，因為運算子必須使用向量和純量出現的順序為何，所需的純量乘法的兩個多載。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-114">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="0ce1c-115">建立新的運算子</span><span class="sxs-lookup"><span data-stu-id="0ce1c-115">Creating New Operators</span></span>
<span data-ttu-id="0ce1c-116">您可以多載所有標準的運算子，但您也可以建立新的運算子，超出特定的字元序列。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-116">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="0ce1c-117">允許的運算子字元為`!`， `%`， `&`， `*`， `+`， `-`， `.`， `/`， `<`， `=`， `>`， `?`， `@`， `^`， `|`，和`~`。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-117">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="0ce1c-118">`~`字元具有特殊意義的一元運算子，並不是運算子字元序列的一部分。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-118">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="0ce1c-119">並非所有運算子都無法都進行一元 （unary）。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-119">Not all operators can be made unary.</span></span>

<span data-ttu-id="0ce1c-120">根據您使用的確切的字元序列，您的運算子會有特定優先順序和關聯性。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-120">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="0ce1c-121">關聯性可以在從左至右或由右至左可能保留，且不含括弧的順序出現相同層級的優先順序的運算子時，都會使用。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-121">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="0ce1c-122">運算子字元`.`以便比方說，如果您想要定義您自己有相同的優先順序和順序關聯性與一般乘法的乘法的版本，您可以建立運算子，例如，不會影響優先順序，`.*`.</span><span class="sxs-lookup"><span data-stu-id="0ce1c-122">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="0ce1c-123">只有運算子`?`和`?<-`可能開頭`?`。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-123">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="0ce1c-124">可以在中找到的資料表是顯示 F # 中的所有運算子的優先順序[符號和運算子參考](symbol-and-operator-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-124">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span></span>


## <a name="overloaded-operator-names"></a><span data-ttu-id="0ce1c-125">多載的運算子名稱</span><span class="sxs-lookup"><span data-stu-id="0ce1c-125">Overloaded Operator Names</span></span>
<span data-ttu-id="0ce1c-126">當 F # 編譯器編譯的運算子的運算式時，它會產生具有編譯器產生的名稱，該運算子的方法。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-126">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="0ce1c-127">這是出現在方法的 Microsoft intermediate language (MSIL)，也在反映和 IntelliSense 的名稱。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-127">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="0ce1c-128">您通常不需要在 F # 程式碼中使用這些名稱。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-128">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="0ce1c-129">下表顯示標準的運算子和其對應產生的名稱。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-129">The following table shows the standard operators and their corresponding generated names.</span></span>



|<span data-ttu-id="0ce1c-130">運算子</span><span class="sxs-lookup"><span data-stu-id="0ce1c-130">Operator</span></span>|<span data-ttu-id="0ce1c-131">產生的名稱</span><span class="sxs-lookup"><span data-stu-id="0ce1c-131">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|
<span data-ttu-id="0ce1c-132">其他未在此處列出的運算子字元的組合可用來當作運算子，且有下表中的個別字元的名稱串連起來所組成的名稱。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-132">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="0ce1c-133">例如，+ ！</span><span class="sxs-lookup"><span data-stu-id="0ce1c-133">For example, +!</span></span> <span data-ttu-id="0ce1c-134">會變成`op_PlusBang`。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-134">becomes `op_PlusBang`.</span></span>



|<span data-ttu-id="0ce1c-135">運算子字元</span><span class="sxs-lookup"><span data-stu-id="0ce1c-135">Operator character</span></span>|<span data-ttu-id="0ce1c-136">名稱</span><span class="sxs-lookup"><span data-stu-id="0ce1c-136">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="0ce1c-137">前置詞和中置運算子</span><span class="sxs-lookup"><span data-stu-id="0ce1c-137">Prefix and Infix Operators</span></span>
<span data-ttu-id="0ce1c-138">*前置詞*運算子應該放置在運算元或運算元，非常類似函式前面。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-138">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="0ce1c-139">*中置*運算子應該有兩個運算元之間。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-139">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="0ce1c-140">只有特定運算子可用來當做前置運算子。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-140">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="0ce1c-141">有些運算子永遠前置運算子，其他人可以是中置或前置詞，而且其餘部分永遠是中置運算子。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-141">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="0ce1c-142">開頭為 `!` 的運算子 (不包括 `!=`) 以及 `~` 運算子或 `~` 的重複序列一律為前置運算子。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-142">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="0ce1c-143">運算子`+`， `-`， `+.`， `-.`， `&`， `&&`， `%`，和`%%`可以是前置運算子或中置運算子。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-143">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="0ce1c-144">中置版本區分這些運算子的前置詞新版加`~`前置運算子定義時的開頭。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-144">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="0ce1c-145">`~`時只有在定義時，會使用運算子，不會使用。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-145">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="0ce1c-146">範例</span><span class="sxs-lookup"><span data-stu-id="0ce1c-146">Example</span></span>

<span data-ttu-id="0ce1c-147">下列程式碼說明如何使用運算子多載實作分數型別。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-147">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="0ce1c-148">分數的分子，分母所表示。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-148">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="0ce1c-149">此函式`hcf`用來判斷最高公因數，用來減少分數。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-149">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="0ce1c-150">**輸出：**</span><span class="sxs-lookup"><span data-stu-id="0ce1c-150">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="0ce1c-151">在全域層級的運算子</span><span class="sxs-lookup"><span data-stu-id="0ce1c-151">Operators at the Global Level</span></span>
<span data-ttu-id="0ce1c-152">您也可以定義的全域層級的運算子。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-152">You can also define operators at the global level.</span></span> <span data-ttu-id="0ce1c-153">下列程式碼定義的運算子`+?`。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-153">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="0ce1c-154">上述程式碼的輸出是`12`。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-154">The output of the above code is `12`.</span></span>

<span data-ttu-id="0ce1c-155">因為的範圍規則的 F # 聽寫的新定義的運算子的優先順序高於內建運算子，您可以重新定義以這種方式的一般算術運算子。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-155">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="0ce1c-156">關鍵字`inline`常搭配全域運算子，而這通常是最佳整合呼叫程式碼的小型函式。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-156">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="0ce1c-157">內嵌函式進行運算子也可讓它們使用來產生以統計方式解析的一般程式碼以統計方式解析的型別參數。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-157">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="0ce1c-158">如需詳細資訊，請參閱[內嵌函式](functions/inline-functions.md)和[以靜態方式解析的型別參數](generics/statically-resolved-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce1c-158">For more information, see [Inline Functions](functions/inline-functions.md) and [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ce1c-159">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ce1c-159">See Also</span></span>
[<span data-ttu-id="0ce1c-160">成員</span><span class="sxs-lookup"><span data-stu-id="0ce1c-160">Members</span></span>](members/index.md)