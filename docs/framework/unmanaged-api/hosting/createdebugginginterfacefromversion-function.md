---
title: "CreateDebuggingInterfaceFromVersion 函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CreateDebuggingInterfaceFromVersion
helpviewer_keywords: CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cc352603ef1c3610edf99f7bdd877c6bb0e5d9fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="049bf-102">CreateDebuggingInterfaceFromVersion 函式</span><span class="sxs-lookup"><span data-stu-id="049bf-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="049bf-103">建立[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)物件會根據指定的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="049bf-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="049bf-104">此函式中已過時[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="049bf-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="049bf-105">相反地，若要取得 common language runtime (CLR) 2.0 介面，請使用[iclrruntimeinfo:: Getinterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)方法並指定的類別識別項 CLSID_CLRDebuggingLegacy 和 IID_ICorDebug 介面識別項。</span><span class="sxs-lookup"><span data-stu-id="049bf-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="049bf-106">若要取得的介面，CLR 4 或更新版本中，呼叫[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函式，並指定的類別識別項 CLSID_CLRDebugging 和 IID_ICLRDebugging 介面識別項。</span><span class="sxs-lookup"><span data-stu-id="049bf-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="049bf-107">語法</span><span class="sxs-lookup"><span data-stu-id="049bf-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="049bf-108">參數</span><span class="sxs-lookup"><span data-stu-id="049bf-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="049bf-109">[in]版本`ICorDebug`預期偵錯工具。</span><span class="sxs-lookup"><span data-stu-id="049bf-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="049bf-110">請參閱[CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)列舉值是否有效。</span><span class="sxs-lookup"><span data-stu-id="049bf-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="049bf-111">[in]要進行偵錯的應用程式或處理序相關聯之 common language runtime 版本。</span><span class="sxs-lookup"><span data-stu-id="049bf-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="049bf-112">請參閱[GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)或[GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)擷取此值的詳細資訊的方法。</span><span class="sxs-lookup"><span data-stu-id="049bf-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="049bf-113">[out]接收資料指標的位置`ICorDebug`物件。</span><span class="sxs-lookup"><span data-stu-id="049bf-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="049bf-114">傳回值</span><span class="sxs-lookup"><span data-stu-id="049bf-114">Return Value</span></span>  
 <span data-ttu-id="049bf-115">這個方法會傳回下列值除了 WinError.h 檔案中定義的標準 COM 錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="049bf-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="049bf-116">傳回碼</span><span class="sxs-lookup"><span data-stu-id="049bf-116">Return code</span></span>|<span data-ttu-id="049bf-117">描述</span><span class="sxs-lookup"><span data-stu-id="049bf-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="049bf-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="049bf-118">S_OK</span></span>|<span data-ttu-id="049bf-119">已成功完成命令。</span><span class="sxs-lookup"><span data-stu-id="049bf-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="049bf-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="049bf-120">E_INVALIDARG</span></span>|<span data-ttu-id="049bf-121">`szDebuggeeVersion`或`ppCordb`是 null 或版本字串不正確。</span><span class="sxs-lookup"><span data-stu-id="049bf-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="049bf-122">備註</span><span class="sxs-lookup"><span data-stu-id="049bf-122">Remarks</span></span>  
 <span data-ttu-id="049bf-123">`szDebuggeeVersion`參數對應至對應的 MSCorDbi.dll 版本。</span><span class="sxs-lookup"><span data-stu-id="049bf-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="049bf-124">需求</span><span class="sxs-lookup"><span data-stu-id="049bf-124">Requirements</span></span>  
 <span data-ttu-id="049bf-125">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="049bf-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="049bf-126">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="049bf-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="049bf-127">**程式庫：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="049bf-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="049bf-128">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="049bf-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="049bf-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="049bf-129">See Also</span></span>  
 [<span data-ttu-id="049bf-130">已被取代的 CLR 裝載函式</span><span class="sxs-lookup"><span data-stu-id="049bf-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)