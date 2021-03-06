---
title: HOW TO：控制服務執行個體
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: b9e622903f871564495796b1690ab4e3a1f66fb7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514820"
---
# <a name="how-to-control-service-instancing"></a>HOW TO：控制服務執行個體
設定服務的執行個體模式，可讓您指定 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (及其相關之使用者定義的服務物件) 建立的時機。 如需可能的模式，請參閱 <xref:System.ServiceModel.InstanceContextMode> 列舉。 如需行為的詳細資訊，請參閱[設定和擴充執行階段行為](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)。 如需實用範例，請參閱[行為](../../../../docs/framework/wcf/samples/behaviors.md)。  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a>使用程式碼控制服務執行個體存留期  
  
1.  將 <xref:System.ServiceModel.ServiceBehaviorAttribute> 套用至服務類別。  
  
2.  將 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 屬性設定為下列其中一值：<xref:System.ServiceModel.InstanceContextMode.PerCall>、<xref:System.ServiceModel.InstanceContextMode.PerSession> 或 <xref:System.ServiceModel.InstanceContextMode.Single>。  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a>範例  
 下列程式碼範例會將 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 屬性 (Attribute) 的 <xref:System.ServiceModel.ServiceBehaviorAttribute> 屬性 (Property) 設定為 <xref:System.ServiceModel.InstanceContextMode.PerCall>。  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>  
 <xref:System.ServiceModel.InstanceContextMode>  
 [服務： 行為範例](https://msdn.microsoft.com/library/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)
