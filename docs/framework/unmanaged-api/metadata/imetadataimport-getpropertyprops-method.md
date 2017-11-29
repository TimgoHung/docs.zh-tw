---
title: "IMetaDataImport::GetPropertyProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc3a1ce1d07bda50b2b578e7d20870324d60edc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="df7a1-102">IMetaDataImport::GetPropertyProps 方法</span><span class="sxs-lookup"><span data-stu-id="df7a1-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="df7a1-103">取得指定語彙基元所表示之屬性的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="df7a1-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df7a1-104">語法</span><span class="sxs-lookup"><span data-stu-id="df7a1-104">Syntax</span></span>  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df7a1-105">參數</span><span class="sxs-lookup"><span data-stu-id="df7a1-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="df7a1-106">[in]語彙基元，代表要傳回的中繼資料的屬性。</span><span class="sxs-lookup"><span data-stu-id="df7a1-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="df7a1-107">[out]表示實作屬性的型別 TypeDef 語彙基元的指標。</span><span class="sxs-lookup"><span data-stu-id="df7a1-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="df7a1-108">[out]要保存的屬性名稱的緩衝區。</span><span class="sxs-lookup"><span data-stu-id="df7a1-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="df7a1-109">[in]中的寬字元大小`szProperty`。</span><span class="sxs-lookup"><span data-stu-id="df7a1-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="df7a1-110">[out]傳回的寬字元數目`szProperty`。</span><span class="sxs-lookup"><span data-stu-id="df7a1-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="df7a1-111">[out]套用至屬性的任何屬性旗標指標。</span><span class="sxs-lookup"><span data-stu-id="df7a1-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="df7a1-112">這個值是從位元遮罩[CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)列舉型別。</span><span class="sxs-lookup"><span data-stu-id="df7a1-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="df7a1-113">[out]屬性的中繼資料簽章指標。</span><span class="sxs-lookup"><span data-stu-id="df7a1-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="df7a1-114">[out]在傳回的位元組數目`ppvSig`。</span><span class="sxs-lookup"><span data-stu-id="df7a1-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="df7a1-115">[out]旗標，指定為預設值之屬性的常數類型。</span><span class="sxs-lookup"><span data-stu-id="df7a1-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="df7a1-116">這個值是從 CorElementType 列舉。</span><span class="sxs-lookup"><span data-stu-id="df7a1-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="df7a1-117">[out]儲存這個屬性的預設值的位元組指標。</span><span class="sxs-lookup"><span data-stu-id="df7a1-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="df7a1-118">[out]中的寬字元大小`ppDefaultValue`，如果`pdwCPlusTypeFlag`是 ELEMENT_TYPE_STRING; 否則此值不相關。</span><span class="sxs-lookup"><span data-stu-id="df7a1-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="df7a1-119">在此情況下，長度`ppDefaultValue`會從所指定的型別推斷`pdwCPlusTypeFlag`。</span><span class="sxs-lookup"><span data-stu-id="df7a1-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="df7a1-120">[out]代表屬性 set 存取子方法的 MethodDef 語彙基元指標。</span><span class="sxs-lookup"><span data-stu-id="df7a1-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="df7a1-121">[out]表示屬性的 get 存取子方法的 MethodDef 語彙基元指標。</span><span class="sxs-lookup"><span data-stu-id="df7a1-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="df7a1-122">[out]代表與屬性相關聯的其他方法的 methoddef 語彙基元的陣列。</span><span class="sxs-lookup"><span data-stu-id="df7a1-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="df7a1-123">[in] `rmdOtherMethod` 陣列的大小上限。</span><span class="sxs-lookup"><span data-stu-id="df7a1-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="df7a1-124">如果您未提供足以容納所有方法的陣列，則會略過而不發出警告。</span><span class="sxs-lookup"><span data-stu-id="df7a1-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="df7a1-125">[out]傳回的 methoddef 語彙基元數目`rmdOtherMethod`。</span><span class="sxs-lookup"><span data-stu-id="df7a1-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df7a1-126">需求</span><span class="sxs-lookup"><span data-stu-id="df7a1-126">Requirements</span></span>  
 <span data-ttu-id="df7a1-127">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df7a1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df7a1-128">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="df7a1-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df7a1-129">**程式庫：**包含做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="df7a1-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df7a1-130">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df7a1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7a1-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="df7a1-131">See Also</span></span>  
 [<span data-ttu-id="df7a1-132">IMetaDataImport 介面</span><span class="sxs-lookup"><span data-stu-id="df7a1-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="df7a1-133">IMetaDataImport2 介面</span><span class="sxs-lookup"><span data-stu-id="df7a1-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)