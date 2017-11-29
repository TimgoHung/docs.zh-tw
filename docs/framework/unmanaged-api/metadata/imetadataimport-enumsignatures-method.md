---
title: "IMetaDataImport::EnumSignatures 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumSignatures
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 25fb32b0780dc91157d39ece37f93d7abd582cf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="1ee4c-102">IMetaDataImport::EnumSignatures 方法</span><span class="sxs-lookup"><span data-stu-id="1ee4c-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="1ee4c-103">列舉代表目前範圍中獨立簽章的簽章語彙基元。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ee4c-104">語法</span><span class="sxs-lookup"><span data-stu-id="1ee4c-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ee4c-105">參數</span><span class="sxs-lookup"><span data-stu-id="1ee4c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1ee4c-106">[in、 out]列舉值的指標。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1ee4c-107">這必須是 NULL 的第一個呼叫此方法。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="1ee4c-108">[out]用來儲存簽章 token 的陣列。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1ee4c-109">[in] `rSignatures` 陣列的大小上限。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="1ee4c-110">[out]簽章權杖中傳回的數目`rSignatures`。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ee4c-111">傳回值</span><span class="sxs-lookup"><span data-stu-id="1ee4c-111">Return Value</span></span>  
  
|<span data-ttu-id="1ee4c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ee4c-112">HRESULT</span></span>|<span data-ttu-id="1ee4c-113">說明</span><span class="sxs-lookup"><span data-stu-id="1ee4c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1ee4c-114">`EnumSignatures`已成功傳回。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1ee4c-115">沒有列舉語彙基元。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="1ee4c-116">在此情況下，`pcSignatures`為零。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ee4c-117">備註</span><span class="sxs-lookup"><span data-stu-id="1ee4c-117">Remarks</span></span>  
 <span data-ttu-id="1ee4c-118">所建立的簽章權杖[imetadataemit:: Gettokenfromsig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ee4c-119">需求</span><span class="sxs-lookup"><span data-stu-id="1ee4c-119">Requirements</span></span>  
 <span data-ttu-id="1ee4c-120">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ee4c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ee4c-121">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1ee4c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ee4c-122">**程式庫：**包含做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="1ee4c-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ee4c-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ee4c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee4c-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1ee4c-124">See Also</span></span>  
 [<span data-ttu-id="1ee4c-125">IMetaDataImport 介面</span><span class="sxs-lookup"><span data-stu-id="1ee4c-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="1ee4c-126">IMetaDataImport2 介面</span><span class="sxs-lookup"><span data-stu-id="1ee4c-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)