---
title: "ISymUnmanagedConstant::GetValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedConstant.GetValue
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: df55345b34340349c4c20213f75591e9586153cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="77776-102">ISymUnmanagedConstant::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="77776-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="77776-103">取得常數的值。</span><span class="sxs-lookup"><span data-stu-id="77776-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77776-104">語法</span><span class="sxs-lookup"><span data-stu-id="77776-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77776-105">參數</span><span class="sxs-lookup"><span data-stu-id="77776-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="77776-106">[out]變數接收值的指標。</span><span class="sxs-lookup"><span data-stu-id="77776-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77776-107">傳回值</span><span class="sxs-lookup"><span data-stu-id="77776-107">Return Value</span></span>  
 <span data-ttu-id="77776-108">如果方法成功則為 S_OK否則，E_FAIL 或其他錯誤程式碼。</span><span class="sxs-lookup"><span data-stu-id="77776-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77776-109">需求</span><span class="sxs-lookup"><span data-stu-id="77776-109">Requirements</span></span>  
 <span data-ttu-id="77776-110">**標頭：**於 CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="77776-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77776-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="77776-111">See Also</span></span>  
 [<span data-ttu-id="77776-112">ISymUnmanagedConstant 介面</span><span class="sxs-lookup"><span data-stu-id="77776-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="77776-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="77776-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="77776-114">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="77776-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)