---
title: "CorCallingConvention 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCallingConvention
helpviewer_keywords: CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c0fbbb5f2c8f73cb6c76137263fa457840cdddc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="fcc62-102">CorCallingConvention 列舉</span><span class="sxs-lookup"><span data-stu-id="fcc62-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="fcc62-103">包含值，這些值描述在 Managed 程式碼中進行的呼叫慣例類型。</span><span class="sxs-lookup"><span data-stu-id="fcc62-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc62-104">語法</span><span class="sxs-lookup"><span data-stu-id="fcc62-104">Syntax</span></span>  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="fcc62-105">成員</span><span class="sxs-lookup"><span data-stu-id="fcc62-105">Members</span></span>  
  
|<span data-ttu-id="fcc62-106">成員</span><span class="sxs-lookup"><span data-stu-id="fcc62-106">Member</span></span>|<span data-ttu-id="fcc62-107">說明</span><span class="sxs-lookup"><span data-stu-id="fcc62-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="fcc62-108">表示預設呼叫慣例。</span><span class="sxs-lookup"><span data-stu-id="fcc62-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="fcc62-109">表示此方法採用多個參數。</span><span class="sxs-lookup"><span data-stu-id="fcc62-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="fcc62-110">表示呼叫的欄位。</span><span class="sxs-lookup"><span data-stu-id="fcc62-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="fcc62-111">表示要區域方法呼叫。</span><span class="sxs-lookup"><span data-stu-id="fcc62-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="fcc62-112">表示呼叫的屬性。</span><span class="sxs-lookup"><span data-stu-id="fcc62-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="fcc62-113">表示呼叫未受管理。</span><span class="sxs-lookup"><span data-stu-id="fcc62-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="fcc62-114">表示泛型方法的具現化。</span><span class="sxs-lookup"><span data-stu-id="fcc62-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="fcc62-115">表示 64 位元 PInvoke 呼叫的方法，接受可變數目的參數。</span><span class="sxs-lookup"><span data-stu-id="fcc62-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="fcc62-116">描述無效的 4 位元值。</span><span class="sxs-lookup"><span data-stu-id="fcc62-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="fcc62-117">指出，最後四個位元所描述的呼叫慣例。</span><span class="sxs-lookup"><span data-stu-id="fcc62-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="fcc62-118">表示的最上層的位元描述`this`參數。</span><span class="sxs-lookup"><span data-stu-id="fcc62-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="fcc62-119">表示`this`參數是明確地描述簽章中。</span><span class="sxs-lookup"><span data-stu-id="fcc62-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="fcc62-120">表示泛型方法簽章，以明確的型別引數數目。</span><span class="sxs-lookup"><span data-stu-id="fcc62-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="fcc62-121">這位於一般參數計數。</span><span class="sxs-lookup"><span data-stu-id="fcc62-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fcc62-122">需求</span><span class="sxs-lookup"><span data-stu-id="fcc62-122">Requirements</span></span>  
 <span data-ttu-id="fcc62-123">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc62-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcc62-124">**標頭：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="fcc62-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fcc62-125">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc62-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc62-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fcc62-126">See Also</span></span>  
 [<span data-ttu-id="fcc62-127">中繼資料列舉</span><span class="sxs-lookup"><span data-stu-id="fcc62-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)