---
title: AddFile Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.AddFile
- AddFile
api_location: alink.dll
api_type: COM
f1_keywords: AddFile
helpviewer_keywords: AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9463f2c41f56287ebfc4fb55aa8208c37522a57f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="addfile-method1"></a><span data-ttu-id="66c12-102">AddFile Method1</span><span class="sxs-lookup"><span data-stu-id="66c12-102">AddFile Method1</span></span>
<span data-ttu-id="66c12-103">將檔案加入至組件。</span><span class="sxs-lookup"><span data-stu-id="66c12-103">Adds files to the assembly.</span></span> <span data-ttu-id="66c12-104">也可以用來建立未繫結的模組。</span><span class="sxs-lookup"><span data-stu-id="66c12-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66c12-105">語法</span><span class="sxs-lookup"><span data-stu-id="66c12-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66c12-106">參數</span><span class="sxs-lookup"><span data-stu-id="66c12-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="66c12-107">要當做引數的組件的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="66c12-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="66c12-108">要加入檔案的完整限定的名稱。</span><span class="sxs-lookup"><span data-stu-id="66c12-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="66c12-109">COM + FileDef 旗標，例如`ffContainsNoMetaData`和`ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="66c12-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="66c12-110">`dwFlags`傳遞至[DefineFile 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="66c12-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="66c12-111">[IMetaDataEmit 介面](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)用來發出中繼資料，如有必要的介面。</span><span class="sxs-lookup"><span data-stu-id="66c12-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="66c12-112">若要加入的檔案的唯一識別碼的儲存位置的指標。</span><span class="sxs-lookup"><span data-stu-id="66c12-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66c12-113">傳回值</span><span class="sxs-lookup"><span data-stu-id="66c12-113">Return Value</span></span>  
 <span data-ttu-id="66c12-114">如果方法成功則傳回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="66c12-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66c12-115">需求</span><span class="sxs-lookup"><span data-stu-id="66c12-115">Requirements</span></span>  
 <span data-ttu-id="66c12-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="66c12-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c12-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66c12-117">See Also</span></span>  
 [<span data-ttu-id="66c12-118">IALink 介面</span><span class="sxs-lookup"><span data-stu-id="66c12-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="66c12-119">IALink2 介面</span><span class="sxs-lookup"><span data-stu-id="66c12-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="66c12-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="66c12-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)