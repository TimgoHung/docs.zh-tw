---
title: IMetaDataEmit::DefineEvent 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce94765467899ac7c906b0dfcdf0ceb78c659b5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448200"
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent 方法
指定的中繼資料簽章，以建立事件，並取得該事件定義語彙基元。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
#### <a name="parameters"></a>參數  
 `td`  
 [in]目標類別或介面之語彙基元。 這可能是`mdTypeDef`或`mdTypeDefNil`語彙基元。  
  
 `szEvent`  
 [in]事件的名稱。  
  
 `dwEventFlags`  
 [in]事件的旗標。  
  
 `tkEventType`  
 [in]事件類別之語彙基元。 這是`mdTypeDef`、 `mdTypeRef`，或`mdTokenNil`語彙基元。  
  
 `mdAddOn`  
 [in]用來訂閱的事件或為 null 的方法。  
  
 `mdRemoveOn`  
 [in]用來取消訂閱的事件或為 null 的方法。  
  
 `mdFire`  
 [in]（由衍生類別） 用來引發事件的方法。  
  
 `rmdOtherMethods[]`  
 [in]陣列的其他方法與事件相關聯的語彙基元。 陣列結尾`mdMethodDefNil`語彙基元。  
  
 `pmdEvent`  
 [out]指派給事件中繼資料語彙基元。  
  
## <a name="requirements"></a>需求  
 **平台：** 看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** Cor.h  
  
 **程式庫：** 做為 MSCorEE.dll 中的資源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [IMetaDataEmit 介面](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 介面](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
