---
title: "NameValueSectionHandler 和 DictionarySectionHandler 自訂項目"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords: custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9722493ec62952d7cbc07d478687b8495d24f95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="64e83-102">NameValueSectionHandler 和 DictionarySectionHandler 自訂項目</span><span class="sxs-lookup"><span data-stu-id="64e83-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="64e83-103">定義自訂組態區段，使用設定<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>類別。</span><span class="sxs-lookup"><span data-stu-id="64e83-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="64e83-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="64e83-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="64e83-105">&nbsp;&nbsp;**\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="64e83-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="64e83-106">屬性</span><span class="sxs-lookup"><span data-stu-id="64e83-106">Attributes</span></span>

<span data-ttu-id="64e83-107">無</span><span class="sxs-lookup"><span data-stu-id="64e83-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="64e83-108">父項目</span><span class="sxs-lookup"><span data-stu-id="64e83-108">Parent element</span></span>

|     | <span data-ttu-id="64e83-109">說明</span><span class="sxs-lookup"><span data-stu-id="64e83-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="64e83-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="64e83-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="64e83-111">通用語言執行平台和 .NET Framework 應用程式所使用之每個組態檔中的根項目。</span><span class="sxs-lookup"><span data-stu-id="64e83-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="64e83-112">子元素</span><span class="sxs-lookup"><span data-stu-id="64e83-112">Child elements</span></span>

|     | <span data-ttu-id="64e83-113">說明</span><span class="sxs-lookup"><span data-stu-id="64e83-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="64e83-114">[**\<新增 >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md)如<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="64e83-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="64e83-115">加入自訂應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="64e83-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="64e83-116">[**\<移除 >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md)如<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="64e83-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> |    <span data-ttu-id="64e83-117">移除先前定義的設定。</span><span class="sxs-lookup"><span data-stu-id="64e83-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="64e83-118">[**\<清除 >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md)如<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="64e83-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="64e83-119">清除所有先前定義的設定區段中。</span><span class="sxs-lookup"><span data-stu-id="64e83-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="64e83-120">備註</span><span class="sxs-lookup"><span data-stu-id="64e83-120">Remarks</span></span>

<span data-ttu-id="64e83-121">**\<SectionName >**項目是所定義的自訂項目**\<區段 >**標記 **\<c >**項目。</span><span class="sxs-lookup"><span data-stu-id="64e83-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="64e83-122">下表顯示每個組態區段處理常式會傳回物件 ConfigurationSettings.GetConfig 方法的型別：</span><span class="sxs-lookup"><span data-stu-id="64e83-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="64e83-123">組態區段處理常式</span><span class="sxs-lookup"><span data-stu-id="64e83-123">Configuration section handler</span></span>                        | <span data-ttu-id="64e83-124">傳回型別</span><span class="sxs-lookup"><span data-stu-id="64e83-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="64e83-125">範例</span><span class="sxs-lookup"><span data-stu-id="64e83-125">Example</span></span>

<span data-ttu-id="64e83-126">下列範例示範如何宣告使用的區段<xref:System.Configuration.DictionarySectionHandler>和<xref:System.Configuration.NameValueSectionHandler>類別。</span><span class="sxs-lookup"><span data-stu-id="64e83-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span> 

<span data-ttu-id="64e83-127">第一個自訂的元素是 **\<dictionarySample >**，其中包含所讀取的設定<xref:System.Configuration.DictionarySectionHandler>類別`System.dll`組件。</span><span class="sxs-lookup"><span data-stu-id="64e83-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="64e83-128">第二個自訂項目，則 **\<mySection >**，其中包含所讀取的設定<xref:System.Configuration.NameValueSectionHandler>類別`System.dll`組件。</span><span class="sxs-lookup"><span data-stu-id="64e83-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="64e83-129">組態檔</span><span class="sxs-lookup"><span data-stu-id="64e83-129">Configuration file</span></span>

<span data-ttu-id="64e83-130">此項目可以用於應用程式組態檔中，電腦組態檔 (*Machine.config*)，和*Web.config*不在應用程式目錄層級的檔案。</span><span class="sxs-lookup"><span data-stu-id="64e83-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="64e83-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="64e83-131">See also</span></span>

[<span data-ttu-id="64e83-132">適用於.NET Framework 組態檔結構描述</span><span class="sxs-lookup"><span data-stu-id="64e83-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)