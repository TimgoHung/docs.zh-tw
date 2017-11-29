---
title: "ICorProfilerCallback::AssemblyUnloadFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 144f7af59afbb403d9ec1894f06c5c028b767416
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="957bd-102">ICorProfilerCallback::AssemblyUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="957bd-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="957bd-103">通知分析工具組件已卸載。</span><span class="sxs-lookup"><span data-stu-id="957bd-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="957bd-104">語法</span><span class="sxs-lookup"><span data-stu-id="957bd-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="957bd-105">參數</span><span class="sxs-lookup"><span data-stu-id="957bd-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="957bd-106">[in]識別正在卸載組件。</span><span class="sxs-lookup"><span data-stu-id="957bd-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="957bd-107">[in]HRESULT，指出組件是否已卸載成功。</span><span class="sxs-lookup"><span data-stu-id="957bd-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="957bd-108">備註</span><span class="sxs-lookup"><span data-stu-id="957bd-108">Remarks</span></span>  
 <span data-ttu-id="957bd-109">值`assemblyId`不正確資訊要求之後[icorprofilercallback:: Assemblyunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)方法會傳回。</span><span class="sxs-lookup"><span data-stu-id="957bd-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="957bd-110">卸載組件的某些部分可能會繼續之後`AssemblyUnloadFinished`回呼。</span><span class="sxs-lookup"><span data-stu-id="957bd-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="957bd-111">失敗的 HRESULT 中`hrStatus`表示失敗。</span><span class="sxs-lookup"><span data-stu-id="957bd-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="957bd-112">不過，成功 HRESULT 中`hrStatus`只會指出已成功卸載組件的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="957bd-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="957bd-113">需求</span><span class="sxs-lookup"><span data-stu-id="957bd-113">Requirements</span></span>  
 <span data-ttu-id="957bd-114">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="957bd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="957bd-115">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="957bd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="957bd-116">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="957bd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="957bd-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="957bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957bd-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="957bd-118">See Also</span></span>  
 [<span data-ttu-id="957bd-119">ICorProfilerCallback 介面</span><span class="sxs-lookup"><span data-stu-id="957bd-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)