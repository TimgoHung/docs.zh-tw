---
title: "IMetaDataTables::GetUserStringHeapSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetUserStringHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 69c78afddc50930d4390b516cece819f124a7933
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="b4f31-102">IMetaDataTables::GetUserStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="b4f31-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="b4f31-103">取得以位元組為單位的使用者字串堆積的大小。</span><span class="sxs-lookup"><span data-stu-id="b4f31-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f31-104">語法</span><span class="sxs-lookup"><span data-stu-id="b4f31-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4f31-105">參數</span><span class="sxs-lookup"><span data-stu-id="b4f31-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="b4f31-106">[out]大小，以位元組為單位，使用者字串堆積的指標。</span><span class="sxs-lookup"><span data-stu-id="b4f31-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f31-107">需求</span><span class="sxs-lookup"><span data-stu-id="b4f31-107">Requirements</span></span>  
 <span data-ttu-id="b4f31-108">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f31-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f31-109">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b4f31-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4f31-110">**程式庫：**做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="b4f31-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4f31-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f31-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f31-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b4f31-112">See Also</span></span>  
 [<span data-ttu-id="b4f31-113">IMetaDataTables 介面</span><span class="sxs-lookup"><span data-stu-id="b4f31-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="b4f31-114">IMetaDataTables2 介面</span><span class="sxs-lookup"><span data-stu-id="b4f31-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)