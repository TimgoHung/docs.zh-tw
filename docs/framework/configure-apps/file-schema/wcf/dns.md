---
title: '&lt;dns&gt;'
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 2f5b9d5e1bc57230adbb32664e9ae15d3c71d46f
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862474"
---
# <a name="ltdnsgt"></a>&lt;dns&gt;
指定伺服器的預期身分識別。 如果伺服器的憑證包含具有相同值的 DNS，這個身分識別對於 X509 憑證驗證模式是有效的。 如果 SPN 具有相同的值，則對於 Windows 驗證模式也是有效的。  
  
 如需設定項目值的詳細資訊，請參閱 <<c0> [ 服務身分識別和驗證](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。  
  
 \<身分識別 >  
\<dns >  
  
## <a name="syntax"></a>語法  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|value|憑證的 DNS。 DNS 是業界標準通訊協定，用來尋找 IP 網路上的電腦。 使用者可以記住顯示名稱，例如[ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929)或是[ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165)、 數字為基礎的位址，例如 207.46.131.137 比更容易。|  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<身分識別 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|指定要由用戶端驗證之服務的身分識別。|  
  
## <a name="example"></a>範例  
 下列組態程式碼會指定用來驗證伺服器之 X.509 憑證的 DNS。  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [服務身分識別和驗證](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<身分識別 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
