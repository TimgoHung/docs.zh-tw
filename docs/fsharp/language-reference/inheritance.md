---
title: "繼承 (F#)"
description: "了解如何指定 F # 繼承關聯性使用 'inherit' 關鍵字。"
keywords: "Visual F#, F#, 函式程式設計"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b38ab2f6-7ba7-4839-8eff-e6bd6cfd2b2f
ms.openlocfilehash: 331c8f4e39aacd9d5e55bfbaf584f037e58d36a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="inheritance"></a><span data-ttu-id="ce344-104">繼承</span><span class="sxs-lookup"><span data-stu-id="ce344-104">Inheritance</span></span>

<span data-ttu-id="ce344-105">繼承用來建立模型的 「 是-a"關聯性，或子物件導向程式設計中。</span><span class="sxs-lookup"><span data-stu-id="ce344-105">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>


## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="ce344-106">指定繼承關聯性</span><span class="sxs-lookup"><span data-stu-id="ce344-106">Specifying Inheritance Relationships</span></span>
<span data-ttu-id="ce344-107">使用指定的繼承關聯性`inherit`類別宣告中的關鍵字。</span><span class="sxs-lookup"><span data-stu-id="ce344-107">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="ce344-108">基本語法形式是由下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="ce344-108">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="ce344-109">類別可以有最多一個直接基底類別。</span><span class="sxs-lookup"><span data-stu-id="ce344-109">A class can have at most one direct base class.</span></span> <span data-ttu-id="ce344-110">如果您未指定基底類別使用`inherit`關鍵字，在類別隱含繼承自`System.Object`。</span><span class="sxs-lookup"><span data-stu-id="ce344-110">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>


## <a name="inherited-members"></a><span data-ttu-id="ce344-111">繼承的成員</span><span class="sxs-lookup"><span data-stu-id="ce344-111">Inherited Members</span></span>
<span data-ttu-id="ce344-112">如果類別繼承自另一個類別，方法和基底類別成員可用來在衍生類別的使用者，就像是在衍生類別的直接成員一樣。</span><span class="sxs-lookup"><span data-stu-id="ce344-112">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="ce344-113">任何 let 繫結和建構函式參數都是私用至類別，因此，無法從衍生類別存取。</span><span class="sxs-lookup"><span data-stu-id="ce344-113">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="ce344-114">關鍵字`base`隨附在衍生類別中，參考的基底類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="ce344-114">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="ce344-115">它當成自我識別項。</span><span class="sxs-lookup"><span data-stu-id="ce344-115">It is used like the self-identifier.</span></span>


## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="ce344-116">虛擬方法，並覆寫</span><span class="sxs-lookup"><span data-stu-id="ce344-116">Virtual Methods and Overrides</span></span>
<span data-ttu-id="ce344-117">虛擬方法 （和屬性） 運作方式稍有不同 F # 中相較於其他.NET 語言。</span><span class="sxs-lookup"><span data-stu-id="ce344-117">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="ce344-118">若要宣告新的虛擬成員，您使用`abstract`關鍵字。</span><span class="sxs-lookup"><span data-stu-id="ce344-118">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="ce344-119">要這麼做，不論您是否提供該方法的預設實作。</span><span class="sxs-lookup"><span data-stu-id="ce344-119">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="ce344-120">因此在基底類別虛擬方法的完整定義會遵循下列模式：</span><span class="sxs-lookup"><span data-stu-id="ce344-120">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="ce344-121">並在衍生類別中覆寫此虛擬方法遵循下列模式：</span><span class="sxs-lookup"><span data-stu-id="ce344-121">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="ce344-122">如果您省略基底類別中的預設實作，基底類別變成抽象類別。</span><span class="sxs-lookup"><span data-stu-id="ce344-122">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="ce344-123">下列程式碼範例將說明新的虛擬方法的宣告`function1`基底類別，以及如何在衍生類別中覆寫它。</span><span class="sxs-lookup"><span data-stu-id="ce344-123">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a><span data-ttu-id="ce344-124">建構函式和繼承</span><span class="sxs-lookup"><span data-stu-id="ce344-124">Constructors and Inheritance</span></span>
<span data-ttu-id="ce344-125">在衍生類別中，必須先呼叫基底類別的建構函式。</span><span class="sxs-lookup"><span data-stu-id="ce344-125">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="ce344-126">基底類別建構函式的引數出現在引數清單中`inherit`子句。</span><span class="sxs-lookup"><span data-stu-id="ce344-126">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="ce344-127">可用的值必須由衍生的類別建構函式提供的引數。</span><span class="sxs-lookup"><span data-stu-id="ce344-127">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="ce344-128">下列程式碼將示範基底類別和衍生的類別，其中衍生的類別繼承子句中呼叫基底類別建構函式：</span><span class="sxs-lookup"><span data-stu-id="ce344-128">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="ce344-129">在多個建構函式的情況下可以使用下列程式碼。</span><span class="sxs-lookup"><span data-stu-id="ce344-129">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="ce344-130">在衍生的類別建構函式的第一行是`inherit`子句和欄位會顯示為以宣告的明確欄位`val`關鍵字。</span><span class="sxs-lookup"><span data-stu-id="ce344-130">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="ce344-131">如需詳細資訊，請參閱[明確欄位：`val`關鍵字](members/explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="ce344-131">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="ce344-132">繼承的替代方案</span><span class="sxs-lookup"><span data-stu-id="ce344-132">Alternatives to Inheritance</span></span>
<span data-ttu-id="ce344-133">在需要稍微修改的類型的地方的情況下，請考慮使用物件運算式作為繼承的替代方案。</span><span class="sxs-lookup"><span data-stu-id="ce344-133">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="ce344-134">下列範例將說明建立新的衍生的類型的替代方式為物件運算式使用：</span><span class="sxs-lookup"><span data-stu-id="ce344-134">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="ce344-135">如需物件運算式的詳細資訊，請參閱[物件運算式](object-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="ce344-135">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="ce344-136">當您建立的物件階層架構時，請考慮使用差別聯集而非繼承。</span><span class="sxs-lookup"><span data-stu-id="ce344-136">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="ce344-137">差別等位也可以各不相同的模型行為的不同共用通用的整體類型的物件。</span><span class="sxs-lookup"><span data-stu-id="ce344-137">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="ce344-138">單一的差別聯集通常不需要的數目彼此次要變化的衍生類別。</span><span class="sxs-lookup"><span data-stu-id="ce344-138">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="ce344-139">差別等位的相關資訊，請參閱[差別等位](discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="ce344-139">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="ce344-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce344-140">See Also</span></span>
[<span data-ttu-id="ce344-141">物件運算式</span><span class="sxs-lookup"><span data-stu-id="ce344-141">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="ce344-142">F# 語言參考</span><span class="sxs-lookup"><span data-stu-id="ce344-142">F# Language Reference</span></span>](index.md)