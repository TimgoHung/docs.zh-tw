---
title: 整數型別表 (C# 參考)
description: 內建 C# 整數型別的概觀
ms.date: 08/20/2018
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
ms.openlocfilehash: 4ac16d185a52cdb03fcb22f57ebf7506f2fb2745
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078844"
---
# <a name="integral-types-table-c-reference"></a>整數型別表 (C# 參考)

下表顯示整數型別的大小和範圍，以構成簡單類型的子集。  
  
|類型|範圍|大小|  
|----------|-----------|----------|  
|[sbyte](sbyte.md)|-128 到 127|帶正負號的 8 位元整數|  
|[byte](byte.md)|0 到 255|不帶正負號的 8 位元整數|  
|[char](char.md)|U+0000 到 U+ffff|Unicode 16 位元字元|  
|[short](short.md)|-32,768 到 32,767|帶正負號的 16 位元整數|  
|[ushort](ushort.md)|0 到 65,535|不帶正負號的 16 位元整數|  
|[int](int.md)|-2,147,483,648 至 2,147,483,647|帶正負號的 32 位元整數|  
|[uint](uint.md)|0 到 4,294,967,295|不帶正負號的 32 位元整數|  
|[long](long.md)|-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807|帶正負號的 64 位元整數|  
|[ulong](ulong.md)|0 到 18,446,744,073,709,551,615|不帶正負號的 64 位元整數|  

## <a name="remarks"></a>備註
  
如果整數常值所代表的值超出 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>，就會發生編譯錯誤 [CS1021](../../misc/cs1021.md)。

使用 <xref:System.Numerics.BigInteger?displayProperty=nameWithType> 類別表示任意大、帶正負號的整數。
  
## <a name="see-also"></a>另請參閱

- [C# 參考](../index.md)
- [C# 程式設計指南](../../programming-guide/index.md)
- [C# 關鍵字](index.md)
- [型別的參考表](reference-tables-for-types.md)
- [浮點數類型表](floating-point-types-table.md)
- [預設值表](default-values-table.md)
- [格式化數值結果表](formatting-numeric-results-table.md)
- [內建型別表](built-in-types-table.md)
