---
title: CoreResponseData.m_ResponseHeaders Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: eaece5bfe9cda7d35905ecd7e1da503ec11faf9c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2018
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="e0862-102">CoreResponseData.m\_ResponseHeaders 欄位</span><span class="sxs-lookup"><span data-stu-id="e0862-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="e0862-103">`CoreResponseData.m_ResponseHeaders`是<xref:System.Net.WebHeaderCollection>與伺服器的回應相關聯的標頭。</span><span class="sxs-lookup"><span data-stu-id="e0862-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0862-104">語法</span><span class="sxs-lookup"><span data-stu-id="e0862-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="e0862-105">這個 API 不是直接在您的程式碼中使用。</span><span class="sxs-lookup"><span data-stu-id="e0862-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="e0862-106">相反地，您應該使用<xref:System.Diagnostics.DiagnosticSource>連結網路的程式碼。</span><span class="sxs-lookup"><span data-stu-id="e0862-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="e0862-107">請參閱[DiagnosticSource 使用者手冊 》](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)。</span><span class="sxs-lookup"><span data-stu-id="e0862-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="e0862-108">Microsoft 不支援在實際執行應用程式在任何情況下使用這個類別。</span><span class="sxs-lookup"><span data-stu-id="e0862-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e0862-109">需求</span><span class="sxs-lookup"><span data-stu-id="e0862-109">Requirements</span></span>

<span data-ttu-id="e0862-110">**命名空間：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="e0862-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="e0862-111">**組件：**系統 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="e0862-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="e0862-112">**.NET framework 版本：**自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="e0862-112">**.NET Framework versions:** Available since 2.0.</span></span>