---
title: ICLRValidator 介面
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cefd47d3c7298f9cc4b15eb2946f3d95aeae759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437995"
---
# <a name="iclrvalidator-interface"></a>ICLRValidator 介面
提供方法來驗證的可攜式執行檔 (PE) 影像，以及回報驗證錯誤。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[FormatEventInfo 方法](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-formateventinfo-method.md)|取得有關指定之驗證錯誤的詳細的訊息。|  
|[Validate 方法](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)|驗證的可攜式執行檔或 Microsoft 中繼語言 (MSIL)，在指定的檔案。|  
  
## <a name="requirements"></a>需求  
 **平台：** 看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** IValidator.idl、 IValidator.h  
  
 **程式庫：** 包含做為 MSCorEE.dll 中的資源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [ICLRErrorReportingManager 介面](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [裝載介面](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CLRRuntimeHost Coclass](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
