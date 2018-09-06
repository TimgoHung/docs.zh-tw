---
title: 呼叫持續時間
ms.date: 03/30/2017
ms.assetid: e4973ec3-3c66-4c0b-b5d0-294b62c83f7d
ms.openlocfilehash: 1e1ee72f3dd8209cf8afa179d5590072466c5a63
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/05/2018
ms.locfileid: "43768339"
---
# <a name="calls-duration"></a><span data-ttu-id="202c3-102">呼叫持續時間</span><span class="sxs-lookup"><span data-stu-id="202c3-102">Calls Duration</span></span>
<span data-ttu-id="202c3-103">計數器名稱： 呼叫持續時間</span><span class="sxs-lookup"><span data-stu-id="202c3-103">Counter Name: Calls Duration</span></span>  
  
## <a name="description"></a><span data-ttu-id="202c3-104">描述</span><span class="sxs-lookup"><span data-stu-id="202c3-104">Description</span></span>  
 <span data-ttu-id="202c3-105">這個作業呼叫的平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="202c3-105">The average duration of calls to this operation.</span></span> <span data-ttu-id="202c3-106">平均持續時間是根據此方程式計算而來：(N1-N0)/(D1-D0)。</span><span class="sxs-lookup"><span data-stu-id="202c3-106">The average duration is calculated based on this equation: (N1-N0)/(D1-D0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="202c3-107">在非同步 WCF 服務上使用時呼叫持續時間計數器一定會傳回-1。</span><span class="sxs-lookup"><span data-stu-id="202c3-107">When used on an asynchronous WCF service the Calls Duration counter will always return -1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="202c3-108">另請參閱</span><span class="sxs-lookup"><span data-stu-id="202c3-108">See Also</span></span>  
 [<span data-ttu-id="202c3-109">PERF_AVERAGE_TIMER</span><span class="sxs-lookup"><span data-stu-id="202c3-109">PERF_AVERAGE_TIMER</span></span>](https://go.microsoft.com/fwlink/?LinkId=95015)