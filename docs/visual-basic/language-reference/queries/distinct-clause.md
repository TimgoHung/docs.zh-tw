---
title: Distinct 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 18d09d8018303aab6a69801c84c7ec9c6ea19ca9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083828"
---
# <a name="distinct-clause-visual-basic"></a>Distinct 子句 (Visual Basic)
限制目前的範圍變數，以消除重複的值，在後續的查詢子句中的值。  
  
## <a name="syntax"></a>語法  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>備註  
 您可以使用`Distinct`子句傳回唯一項目清單。 `Distinct`子句會使要忽略重複的查詢結果的查詢。 `Distinct`子句會套用到重複的值，所有傳回所指定的欄位`Select`子句。 如果沒有`Select`指定子句，則`Distinct`子句會套用到查詢中所識別的範圍變數`From`子句。 如果範圍變數不是不可變的類型，查詢將只略過查詢結果型別的所有成員符合現有的查詢結果。  
  
## <a name="example"></a>範例  
 下列查詢運算式會聯結一份客戶和客戶訂單的清單。 `Distinct`子句是包含要傳回的唯一客戶名稱清單，並在訂單日期。  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a>另請參閱  
 [Visual Basic 中的 LINQ 簡介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查詢](../../../visual-basic/language-reference/queries/index.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
