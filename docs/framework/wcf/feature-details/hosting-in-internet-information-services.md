---
title: 在網際網路資訊服務中裝載
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: e9d0e5a165eb2eabae95da9fd1e744a9bd1c201b
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085104"
---
# <a name="hosting-in-internet-information-services"></a>在網際網路資訊服務中裝載
裝載 Windows Communication Foundation (WCF) 服務的其中一個選項是在 Internet Information Services (IIS) 應用程式內。 這個裝載模型與 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 和 ASP.NET (ASMX) Web 服務所使用的模型很類似。  
  
## <a name="versions-of-iis"></a>IIS 的版本  
 WCF 可以裝載在下列作業系統上的下列 IIS 版本：  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)] 上的 IIS 5.1。 這個環境適合用來設計與開發 IIS 裝載的應用程式，以便稍後部署到 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 之類的伺服器作業系統中。  
  
-   [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 上的 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]。 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 提供進階處理模型，具有改良的延展性、可靠性和應用程式隔離。 此環境適合用來以獨佔模式使用 HTTP 通訊的 WCF 服務的生產環境部署。  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)] 和 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上的 IIS 7.0。 雖然 IIS 7.0 提供和 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 相同的進階處理模型，但是使用 Windows Process Activation Service (WAS) 來允許在 HTTP 以外的通訊協定上進行啟動和網路通訊。 此環境適合用來透過 WCF （包括 HTTP、 net.tcp、 net.pipe 和 net.msmq） 所支援的任何網路通訊協定進行通訊的 WCF 服務的開發。 如需 WAS 的詳細資訊，請參閱[在 Windows Process Activation Service 中裝載](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)。  
  
-   [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496)搭配[!INCLUDE[iisver](../../../../includes/iisver-md.md)]和 Windows Process Activation Service (WAS) 來提供豐富的應用程式裝載環境，為 NET4 WCF 和 WF 服務。 這些優點包括處理序生命週期管理、處理序回收、共用裝載、快速失敗保護、處理序損壞、隨選啟動和健康監視。 如需詳細資訊，請參閱 < [AppFabric 主控功能](https://go.microsoft.com/fwlink/?LinkId=196494)並[AppFabric 主控概念](https://go.microsoft.com/fwlink/?LinkId=196495)。  
  
## <a name="benefits-of-iis-hosting"></a>IIS 裝載的優點  
 裝載在 IIS 中的 WCF 服務有幾項優點：  
  
-   在 IIS 中裝載的 WCF 服務部署與管理其他任何類型 IIS 應用程式，包括[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]應用程式和 ASMX。  
  
-   IIS 可提供處理序啟動、系統健康狀態管理，與回收功能來增加所裝載之應用程式的可靠性。  
  
-   像是[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]，WCF 服務裝載於[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]可以利用[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]以改進的伺服器密度及延展性的一般背景工作處理序中的多個應用程式所在的共用裝載模型。  
  
-   在 IIS 中裝載的 WCF 服務使用相同的動態編譯模型[!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]、 可簡化開發和部署的託管服務。  
  
 決定要在 IIS 中裝載 WCF 服務時，務必記得 IIS 5.1 和[!INCLUDE[iis601](../../../../includes/iis601-md.md)]僅限於 HTTP 通訊用途。 如需有關選擇裝載環境的詳細資訊，請參閱 <<c0> [ 裝載的服務](../../../../docs/framework/wcf/hosting-services.md)。  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>部署 IIS 裝載的 WCF 服務  
 開發及部署 IIS 裝載的 WCF 服務包含下列工作：  
  
-   確定，IIS、 ASP.NET、 WCF 和 WCF HTTP 啟動元件已正確安裝並註冊。  
  
-   建立新的 IIS 應用程式，或是重複使用現有的 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 應用程式。  
  
-   建立 WCF 服務.svc 檔案。  
  
-   將服務實作部署到 IIS 應用程式。  
  
-   設定 WCF 服務。  
  
 每個工作的討論，請參閱 <<c0> [ 部署 Internet Information Services-Hosted 的 WCF 服務](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)。  
  
## <a name="wcf-services-and-aspnet"></a>WCF 服務與 ASP.NET  
 WCF 服務可以裝載任一--與並存[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]或是在[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]所在的服務可以充分利用所提供的功能的相容性模式[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web 應用程式平台。 如需這些功能的討論，請參閱 < [WCF 服務與 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)。  
  
## <a name="see-also"></a>另請參閱  
 [使用 ServiceHostFactory 擴充裝載](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 [部署已裝載 Internet Information Services 的 WCF 服務](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)  
 [WCF 服務與 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [Internet Information Services 裝載最佳做法](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [設定 Internet Information Services 7.0 for Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)  
 [Windows Server App Fabric 主控功能](https://go.microsoft.com/fwlink/?LinkId=201276)
