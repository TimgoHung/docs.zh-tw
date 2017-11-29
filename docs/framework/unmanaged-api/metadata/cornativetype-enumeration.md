---
title: "CorNativeType 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeType
helpviewer_keywords: CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1c17abfc501b0d44981d2ed6cf7d69d60d9948b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="afe50-102">CorNativeType 列舉</span><span class="sxs-lookup"><span data-stu-id="afe50-102">CorNativeType Enumeration</span></span>
<span data-ttu-id="afe50-103">包含值，這些值描述原生 Unmanaged 類型。</span><span class="sxs-lookup"><span data-stu-id="afe50-103">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afe50-104">語法</span><span class="sxs-lookup"><span data-stu-id="afe50-104">Syntax</span></span>  
  
```  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,   
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a><span data-ttu-id="afe50-105">成員</span><span class="sxs-lookup"><span data-stu-id="afe50-105">Members</span></span>  
  
|<span data-ttu-id="afe50-106">成員</span><span class="sxs-lookup"><span data-stu-id="afe50-106">Member</span></span>|<span data-ttu-id="afe50-107">說明</span><span class="sxs-lookup"><span data-stu-id="afe50-107">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="afe50-108">已過時。</span><span class="sxs-lookup"><span data-stu-id="afe50-108">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="afe50-109">已過時。</span><span class="sxs-lookup"><span data-stu-id="afe50-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="afe50-110">4 位元組布林值，其中 TRUE 是非零，FALSE 是零。</span><span class="sxs-lookup"><span data-stu-id="afe50-110">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="afe50-111">8 位元帶正負號的整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-111">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="afe50-112">不帶正負號的 8 位元整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-112">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="afe50-113">帶正負號的 16 位元整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-113">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="afe50-114">不帶正負號的 16 位元整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-114">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="afe50-115">帶正負號的 32 位元整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-115">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="afe50-116">32 位元不帶正負號的整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-116">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="afe50-117">64 位元帶正負號的整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-117">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="afe50-118">不帶正負號的 64 位元整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-118">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="afe50-119">4 位元組浮點數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-119">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="afe50-120">8 位元組浮點數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-120">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="afe50-121">已過時。</span><span class="sxs-lookup"><span data-stu-id="afe50-121">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="afe50-122">已過時。</span><span class="sxs-lookup"><span data-stu-id="afe50-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="afe50-123">數字的 COM 型別對應至 managed<xref:System.Decimal>型別。</span><span class="sxs-lookup"><span data-stu-id="afe50-123">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="afe50-124">已過時。</span><span class="sxs-lookup"><span data-stu-id="afe50-124">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="afe50-125">已過時。</span><span class="sxs-lookup"><span data-stu-id="afe50-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="afe50-126">已過時。</span><span class="sxs-lookup"><span data-stu-id="afe50-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="afe50-127">COM Interop。</span><span class="sxs-lookup"><span data-stu-id="afe50-127">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="afe50-128">LPSTR 的字串值。</span><span class="sxs-lookup"><span data-stu-id="afe50-128">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="afe50-129">LPWSTR 的字串值。</span><span class="sxs-lookup"><span data-stu-id="afe50-129">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="afe50-130">LPTSTR 的字串值。</span><span class="sxs-lookup"><span data-stu-id="afe50-130">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="afe50-131">固定的系統定義的字串值。</span><span class="sxs-lookup"><span data-stu-id="afe50-131">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="afe50-132">已過時。</span><span class="sxs-lookup"><span data-stu-id="afe50-132">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="afe50-133">COM Interop。</span><span class="sxs-lookup"><span data-stu-id="afe50-133">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="afe50-134">COM Interop。</span><span class="sxs-lookup"><span data-stu-id="afe50-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="afe50-135">原生結構值。</span><span class="sxs-lookup"><span data-stu-id="afe50-135">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="afe50-136">COM Interop。</span><span class="sxs-lookup"><span data-stu-id="afe50-136">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="afe50-137">COM Interop。</span><span class="sxs-lookup"><span data-stu-id="afe50-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="afe50-138">固定長度的陣列值。</span><span class="sxs-lookup"><span data-stu-id="afe50-138">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="afe50-139">原生的 16 位元帶正負號的整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-139">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="afe50-140">原生的 16 位元不帶正負號的整數值。</span><span class="sxs-lookup"><span data-stu-id="afe50-140">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="afe50-141">已過時。</span><span class="sxs-lookup"><span data-stu-id="afe50-141">Obsolete.</span></span><br /><br /> <span data-ttu-id="afe50-142">使用 NATIVE_TYPE_STRUCT。</span><span class="sxs-lookup"><span data-stu-id="afe50-142">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="afe50-143">COM Interop。</span><span class="sxs-lookup"><span data-stu-id="afe50-143">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="afe50-144">COM Interop。</span><span class="sxs-lookup"><span data-stu-id="afe50-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="afe50-145">COM Interop。</span><span class="sxs-lookup"><span data-stu-id="afe50-145">COM Interop.</span></span><br /><br /> <span data-ttu-id="afe50-146">視平台選取 BSTR 或 ansibstr 的功能。</span><span class="sxs-lookup"><span data-stu-id="afe50-146">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="afe50-147">2 位元組布林值，其中為 true，則為-1，FALSE 為零。</span><span class="sxs-lookup"><span data-stu-id="afe50-147">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="afe50-148">函式指標。</span><span class="sxs-lookup"><span data-stu-id="afe50-148">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="afe50-149">任何原生類型的參考。</span><span class="sxs-lookup"><span data-stu-id="afe50-149">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="afe50-150">未指定類型的成員與陣列的參考。</span><span class="sxs-lookup"><span data-stu-id="afe50-150">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="afe50-151">結構的 32 位元整數指標。</span><span class="sxs-lookup"><span data-stu-id="afe50-151">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="afe50-152">自訂封送處理器的原生型別。</span><span class="sxs-lookup"><span data-stu-id="afe50-152">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="afe50-153">這後面必須使用下列格式的字串: 「 原生型別名稱/0Custom 封送處理器會輸入 cookie 的名稱/0Optional/0"或"{原生類型 GUID} / 0Custom 封送處理器類型名稱/0Optional cookie/0"</span><span class="sxs-lookup"><span data-stu-id="afe50-153">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="afe50-154">COM Interop。</span><span class="sxs-lookup"><span data-stu-id="afe50-154">COM Interop.</span></span><br /><br /> <span data-ttu-id="afe50-155">ELEMENT_TYPE_I4 與這個類型會對應至 VT_HRESULT。</span><span class="sxs-lookup"><span data-stu-id="afe50-155">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="afe50-156">原生`IInspectable`型別。</span><span class="sxs-lookup"><span data-stu-id="afe50-156">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="afe50-157">原生`HString`。</span><span class="sxs-lookup"><span data-stu-id="afe50-157">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="afe50-158">無效的值。</span><span class="sxs-lookup"><span data-stu-id="afe50-158">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="afe50-159">需求</span><span class="sxs-lookup"><span data-stu-id="afe50-159">Requirements</span></span>  
 <span data-ttu-id="afe50-160">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="afe50-160">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afe50-161">**標頭：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="afe50-161">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="afe50-162">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afe50-162">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe50-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="afe50-163">See Also</span></span>  
 <xref:System.Runtime.InteropServices.UnmanagedType>  
 [<span data-ttu-id="afe50-164">中繼資料列舉</span><span class="sxs-lookup"><span data-stu-id="afe50-164">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)