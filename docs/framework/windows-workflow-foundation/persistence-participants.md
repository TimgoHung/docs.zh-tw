---
title: 持續性參與者
ms.date: 03/30/2017
ms.assetid: f84d2d5d-1c1b-4f19-be45-65b552d3e9e3
ms.openlocfilehash: f2875ead24e4c072d267a8bb6cddddc7f9b96d86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519806"
---
# <a name="persistence-participants"></a>持續性參與者
持續性參與者可參與由應用程式主機所觸發的持續性作業 (「儲存」或「載入」)。 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]隨附兩個抽象類別， **PersistenceParticipant**和**PersistenceIOParticipant**，讓您可以用來建立持續性參與者。 持續性參與者會衍生自這些類別的其中一個、實作感興趣的方法，然後將類別的執行個體加入至 <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> 上的 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 集合。 應用程式主機保存工作流程執行個體時，可能會尋找此類工作流程擴充功能，並且在適當的時間於持續性參與者上叫用適當的方法。  
  
 以下清單描述持續性子系統在不同階段的「保存」(儲存) 作業時所執行的工作。 持續性參與者會用於第三與第四階段。 如果參與者是 I/O 參與者 （亦同時參與 I/O 作業的持續性參與者），參與者也會用在第六個階段中。  
  
1.  收集內建值，包含工作流程狀態、書籤、對應的變數以及時間戳記。  
  
2.  收集加入至與工作流程執行個體相關之擴充集合的所有持續性參與者。  
  
3.  叫用由所有持續性參與者實作的 <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> 方法。  
  
4.  叫用由所有持續性參與者實作的 <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> 方法。  
  
5.  保存工作流程，或將工作流程儲存至持續性存放區中。  
  
6.  叫用<xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A>在所有 I/O 持續性參與者上的方法。 如果參與者並非 I/O 參與者，則會略過這項工作。 如果持續性的時段屬於交易性質，則交易會在 Transaction.Current 屬性中提供。  
  
7.  等候所有持續性參與者完成。 如果所有參與者成功保存執行個體資料，則認可交易。  
  
 持續性參與者衍生自**PersistenceParticipant**類別，並可能實作**CollectValues**和**MapValues**方法。 I/O 持續性參與者衍生自**PersistenceIOParticipant**類別，並可能實作**BeginOnSave**方法，除了實作**CollectValues**和**MapValues**方法。  
  
 每個階段都會先完成，再開始進行下一個階段。 例如，值從收集**所有**第一階段的持續性參與者。 然後，會將在第一階段中收集到的所有值提供給第二階段中的所有持續性參與者，以進行對應。 接著，會將在第一和第二階段中收集到的所有值提供給第三階段中的所有持續性參與者，以進行對應，依此類推。  
  
 以下清單描述持續性子系統在不同階段的「載入」作業時所執行的工作。 持續性參與者會用於第四階段。 持續性 I/O 參與者 （也在 I/O 操作中參與持續性參與者） 也會用於第三個階段。  
  
1.  收集加入至與工作流程執行個體相關之擴充集合的所有持續性參與者。  
  
2.  自持續性存放區載入工作流程。  
  
3.  叫用<xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A>上所有的 I/O 持續性參與者並等候所有持續性參與者完成。 如果持續性的時段屬於異動性質，則異動會在 Transaction.Current 中提供。  
  
4.  根據從持續性存放區所擷取的資料，載入記憶體中的工作流程執行個體。  
  
5.  叫用每個持續性參與者上的 <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A>。  
  
 持續性參與者衍生自**PersistenceParticipant**類別，並可能實作**PublishValues**方法。 I/O 持續性參與者衍生自**PersistenceIOParticipant**類別，並可能實作**BeginOnLoad**方法，除了實作**PublishValues**方法。  
  
 載入工作流程執行個體時，持續性提供者會建立該執行個體的鎖定。 這可防止在多節點的案例中，多個主機載入執行個體。 如果您嘗試載入已鎖定的工作流程執行個體您會看到類似下列的例外狀況： 例外狀況"System.ServiceModel.Persistence.InstanceLockException： 要求的作業無法完成，因為鎖定執行個體 '00000000-0000-0000-0000-000000000000' 無法取得"。 當下列任一情形發生時，就會發生這個錯誤：  
  
-   在多節點的案例中，執行個體是由另一個主機載入。  有幾個不同的方法來解決這些類型的衝突：將處理轉送到擁有鎖定的節點然後重試，或是強制載入，這會導致其他主機無法儲存它們的工作。  
  
-   在單一節點的案例中且主機毀損。  當主機再次啟動時 (處理序回收或建立新的持續性提供者處理站)，新主機嘗試載入執行個體，但此執行個體仍被舊主機鎖定，因為鎖定尚未到期。  
  
-   在單一節點的案例中，出現問題的執行個體已在某個時間點中止，新的持續性提供者執行個體已建立，其具有不同的主機 ID。  
  
 鎖定逾時值預設為 5 分鐘，您可以在呼叫 <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A> 時指定不同的逾時值。  
  
## <a name="in-this-section"></a>本節內容  
  
-   [如何：建立自訂持續性參與者](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-persistence-participant.md)  
  
## <a name="see-also"></a>另請參閱  
 [存放區擴充性](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)
