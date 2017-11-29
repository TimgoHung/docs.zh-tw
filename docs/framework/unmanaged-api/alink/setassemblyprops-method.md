---
title: "SetAssemblyProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetAssemblyProps
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyProps
helpviewer_keywords: SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0245b6b1e30174bb3496d3d6ab674ccc00fb9fee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="df0fa-102">SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="df0fa-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="df0fa-103">指定組件層級的屬性。</span><span class="sxs-lookup"><span data-stu-id="df0fa-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df0fa-104">語法</span><span class="sxs-lookup"><span data-stu-id="df0fa-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df0fa-105">參數</span><span class="sxs-lookup"><span data-stu-id="df0fa-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="df0fa-106">組件的識別碼。</span><span class="sxs-lookup"><span data-stu-id="df0fa-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="df0fa-107">定義屬性的檔案。</span><span class="sxs-lookup"><span data-stu-id="df0fa-107">File that defines the property.</span></span> <span data-ttu-id="df0fa-108">可以是 NULL，如果`AssemblyID`不會指出未繫結的 netmodule。</span><span class="sxs-lookup"><span data-stu-id="df0fa-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="df0fa-109">指出修改的選項。</span><span class="sxs-lookup"><span data-stu-id="df0fa-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="df0fa-110">新的選項值。</span><span class="sxs-lookup"><span data-stu-id="df0fa-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df0fa-111">傳回值</span><span class="sxs-lookup"><span data-stu-id="df0fa-111">Return Value</span></span>  
 <span data-ttu-id="df0fa-112">如果方法成功則傳回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="df0fa-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df0fa-113">需求</span><span class="sxs-lookup"><span data-stu-id="df0fa-113">Requirements</span></span>  
 <span data-ttu-id="df0fa-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="df0fa-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0fa-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="df0fa-115">See Also</span></span>  
 [<span data-ttu-id="df0fa-116">IALink 介面</span><span class="sxs-lookup"><span data-stu-id="df0fa-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="df0fa-117">IALink2 介面</span><span class="sxs-lookup"><span data-stu-id="df0fa-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="df0fa-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="df0fa-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)