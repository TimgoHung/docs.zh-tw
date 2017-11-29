---
title: "ICLRStrongName::StrongNameGetBlobFromImage 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameGetBlobFromImage
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80edfa333f73854869c3fa6786e038c796b09087
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="a3e1d-102">ICLRStrongName::StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="a3e1d-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="a3e1d-103">取得組件映像的二進位表示法，在指定的記憶體位址。</span><span class="sxs-lookup"><span data-stu-id="a3e1d-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3e1d-104">語法</span><span class="sxs-lookup"><span data-stu-id="a3e1d-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3e1d-105">參數</span><span class="sxs-lookup"><span data-stu-id="a3e1d-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="a3e1d-106">[in]對應的組件資訊清單的記憶體位址。</span><span class="sxs-lookup"><span data-stu-id="a3e1d-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="a3e1d-107">[in]大小 （位元組），在映像的`pbBase`。</span><span class="sxs-lookup"><span data-stu-id="a3e1d-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="a3e1d-108">[in]包含影像的二進位表示法緩衝區。</span><span class="sxs-lookup"><span data-stu-id="a3e1d-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="a3e1d-109">[in、 out]要求的大小上限，以位元組為單位， `pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="a3e1d-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="a3e1d-110">傳回時，實際的大小，以位元組為單位的`pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="a3e1d-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3e1d-111">傳回值</span><span class="sxs-lookup"><span data-stu-id="a3e1d-111">Return Value</span></span>  
 <span data-ttu-id="a3e1d-112">`S_OK`如果方法成功。否則，表示失敗的 HRESULT 值 (請參閱[常見的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)清單)。</span><span class="sxs-lookup"><span data-stu-id="a3e1d-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3e1d-113">需求</span><span class="sxs-lookup"><span data-stu-id="a3e1d-113">Requirements</span></span>  
 <span data-ttu-id="a3e1d-114">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3e1d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3e1d-115">**標頭：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a3e1d-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a3e1d-116">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="a3e1d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3e1d-117">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3e1d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e1d-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a3e1d-118">See Also</span></span>  
 [<span data-ttu-id="a3e1d-119">StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="a3e1d-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="a3e1d-120">ICLRStrongName 介面</span><span class="sxs-lookup"><span data-stu-id="a3e1d-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)