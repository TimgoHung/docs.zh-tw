---
title: let 繫結 (F#)
description: 了解如何使用 F# 'let' 繫結，其關聯的值或函式的識別項。
ms.date: 05/16/2016
ms.openlocfilehash: 1a35b5a39f2768a18665b5c7fe768af0e7714577
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2018
ms.locfileid: "43777466"
---
# <a name="let-bindings"></a>let 繫結

A*繫結*關聯的值或函式的識別項。 您使用`let`關鍵字來將名稱繫結至值或函式。

## <a name="syntax"></a>語法

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>備註

`let`關鍵字可用於繫結來定義值或一或多個名稱的函式值的運算式。 最簡單的形式`let`運算式繫結名稱為簡單的值，如下所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

如果您使用新的一行分隔識別碼中的運算式，您必須縮排每一行的運算式，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

而非只是名稱，可以指定包含名稱的模式，例如，一個 tuple，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

*主體運算式*是所用的名稱的運算式。 主體運算式會出現在它自己的一行，將其完全與中的第一個字元縮排到行向上`let`關鍵字：

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

A`let`繫結可以出現在模組層級，定義中的類別類型，或在區域範圍，例如內嵌函式定義。 A`let`最上層的類別類型或模組中的繫結不需要具有主體運算式，但在其他領域層級中，主體必須是運算式。 繫結的名稱可定義，但不是在任何時間點之前時間點之後`let`繫結隨即出現，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a>函式繫結

函式繫結會遵循值繫結的規則，不同之處在於函式繫結包含函式名稱和參數，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

一般情況下，參數為模式，例如 tuple 模式：

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

A`let`繫結運算式評估為最後一個運算式的值。 因此，在下列程式碼範例中，值`result`從計算`100 * function3 (1, 2)`，它會評估為`300`。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

如需詳細資訊，請參閱[函式](index.md)。

## <a name="type-annotations"></a>型別註釋

包含冒號 （:） 後面接著類型的名稱，為所有以括號顯示，您可以指定參數的類型。 您也可以在最後一個參數後附加冒號和型別，以指定傳回值的型別。 完整型別註釋`function1`，做為參數類型的整數，是，如下所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

沒有明確的類型參數時，型別推斷來判斷函式參數的類型。 這可能包括自動一般化成為泛型參數的型別。

如需詳細資訊，請參閱 <<c0> [ 自動一般化](../generics/automatic-generalization.md)並[型別推斷](../type-inference.md)。

## <a name="let-bindings-in-classes"></a>類別中的 let 繫結

A`let`繫結可以出現在類別類型，但不是在結構或記錄類型。 若要使用 let 繫結中的類別類型，類別必須具有主要建構函式。 建構函式參數必須出現在類別定義的型別名稱之後。 A`let`中的類別類型的繫結定義私用欄位和成員，該類別類型，並搭配`do`類型中的繫結表單類型的主要建構函式的程式碼。 下列程式碼範例顯示類別`MyClass`私用欄位`field1`和`field2`。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

範圍`field1`和`field2`僅限於其宣告的型別。 如需詳細資訊，請參閱 < [ `let`類別中的繫結](../members/let-bindings-in-classes.md)並[類別](../classes.md)。

## <a name="type-parameters-in-let-bindings"></a>型別參數中的 let 繫結

A`let`繫結，在模組層級，在類型中，或在 計算運算式中可以有明確的型別參數。 Let 繫結中的運算式，例如函式定義內不得有類型參數。 如需詳細資訊，請參閱[泛型](../generics/index.md)。

## <a name="attributes-on-let-bindings"></a>屬性的 let 繫結

屬性可以套用至最上層`let`繫結，在模組中，如下列程式碼所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a>範圍和協助工具的 Let 繫結

使用 let 繫結所宣告的實體的範圍僅限於包含的部分繫結出現之後，範圍 （例如函式、 模組、 檔案或類別）。 因此，它可說是 let 繫結引入的名稱，進入範圍內。 在模組中，讓繫結值或函式是模組的用戶端可以存取為模組可供存取，因為在模組中的 let 繫結會編譯成模組的公用函式。 相反地，類別中的 let 繫結是私用類別。

一般來說，模組中的函式必須使用用戶端程式碼時的模組名稱所限定。 例如，如果模組`Module1`函式`function1`，使用者會指定`Module1.function1`參考函式。

模組的使用者可以使用匯入宣告，而不限定的模組名稱，使該模組內的函式可供使用。 在上述範例中，模組的使用者可以在此情況下開啟模組使用匯入宣告開放`Module1`，而且之後參考`function1`直接。

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

某些模組具有屬性[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)，這表示它們所公開的函式必須以模組名稱加以限定。 比方說，F# 清單模組具有此屬性。

如需有關模組和存取控制的詳細資訊，請參閱 <<c0> [ 模組](../modules.md)並[存取控制](../access-control.md)。

## <a name="see-also"></a>另請參閱

- [函式](index.md)
- [類別中的 `let` 繫結](../members/let-bindings-in-classes.md)
