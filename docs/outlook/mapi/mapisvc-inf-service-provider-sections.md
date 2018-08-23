---
title: MapiSvc.inf 服务提供程序部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ab17dcf2-409b-4a57-9cc4-5794f995cd3e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 05666d8d6b7279588b4b442151640fa1696aedda
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586779"
---
# <a name="mapisvcinf-service-provider-sections"></a><span data-ttu-id="6d300-103">MapiSvc.inf 服务提供程序部分</span><span class="sxs-lookup"><span data-stu-id="6d300-103">MapiSvc.inf Service Provider Sections</span></span>

<span data-ttu-id="6d300-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6d300-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6d300-105">Mapisvc.inf 上述邮件服务部分中的**提供程序**条目中列出的项的每个包含服务提供程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="6d300-105">Mapisvc.inf includes one service provider section for each of the entries listed in the **Providers** entry in the preceding message services section.</span></span> <span data-ttu-id="6d300-106">**服务**提供程序部分是邮件服务节相似，，这两种类型的各节包含采用以下格式的条目：</span><span class="sxs-lookup"><span data-stu-id="6d300-106">**Service** provider sections are similar to message service sections in that both types of sections contain entries in this format:</span></span> 
  
<span data-ttu-id="6d300-107">**属性标记**= 属性值</span><span class="sxs-lookup"><span data-stu-id="6d300-107">**property tag** = property value</span></span> 
  
<span data-ttu-id="6d300-108">但是，服务提供程序节和消息服务节不同，此类属性条目都是唯一的服务提供程序部分中包含的条目类型。</span><span class="sxs-lookup"><span data-stu-id="6d300-108">However, service provider sections and message service sections differ in that such property entries are the only type of entry included in service provider sections.</span></span> <span data-ttu-id="6d300-109">可以有服务提供商; 没有其他或链接部分一个节中必须包含所有服务提供商信息。</span><span class="sxs-lookup"><span data-stu-id="6d300-109">There can be no additional or linked sections for service providers; all service provider information must be contained within the one section.</span></span> 
  
<span data-ttu-id="6d300-110">设置消息服务各节中的属性的一些也设置在服务提供程序部分因为这些属性有意义的同时。</span><span class="sxs-lookup"><span data-stu-id="6d300-110">Some of the properties set in message service sections are also set in service provider sections because these properties make sense for both.</span></span> <span data-ttu-id="6d300-111">**PR_DISPLAY_NAME**属性是一个示例。</span><span class="sxs-lookup"><span data-stu-id="6d300-111">The **PR_DISPLAY_NAME** property is an example.</span></span> <span data-ttu-id="6d300-112">服务提供商和消息服务具有用于配置用户界面中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="6d300-112">Both service providers and message services have a name that is used for display in the configuration user interface.</span></span> <span data-ttu-id="6d300-113">根据服务提供商，该名称可能也可能不能相同。</span><span class="sxs-lookup"><span data-stu-id="6d300-113">Depending on the service provider, that name may or may not be the same.</span></span> <span data-ttu-id="6d300-114">其他属性是特定于服务提供商。</span><span class="sxs-lookup"><span data-stu-id="6d300-114">Other properties are specific to service providers.</span></span> 
  
<span data-ttu-id="6d300-115">典型的服务提供程序部分包含以下各项，所有这些都需要：</span><span class="sxs-lookup"><span data-stu-id="6d300-115">Typical service provider sections include the following entries, all of which are required:</span></span>
  
<span data-ttu-id="6d300-116">**PR_DISPLAY_NAME** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="6d300-116">**PR_DISPLAY_NAME** =  _string_</span></span>
  
<span data-ttu-id="6d300-117">**PR_PROVIDER_DISPLAY** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="6d300-117">**PR_PROVIDER_DISPLAY** =  _string_</span></span>
  
<span data-ttu-id="6d300-118">**PR_PROVIDER_DLL_NAME** =  _DLL 文件的名称_</span><span class="sxs-lookup"><span data-stu-id="6d300-118">**PR_PROVIDER_DLL_NAME** =  _name of DLL file_</span></span>
  
<span data-ttu-id="6d300-119">**PR_RESOURCE_TYPE** =  _长_</span><span class="sxs-lookup"><span data-stu-id="6d300-119">**PR_RESOURCE_TYPE** =  _long_</span></span>
  
<span data-ttu-id="6d300-120">**PR_RESOURCE_FLAGS** =  _位掩码_</span><span class="sxs-lookup"><span data-stu-id="6d300-120">**PR_RESOURCE_FLAGS** =  _bitmask_</span></span>
  
<span data-ttu-id="6d300-121">**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 条目是类似于**PR_SERVICE_DLL_NAME**;包含服务提供商的 DLL 的它指示文件名。</span><span class="sxs-lookup"><span data-stu-id="6d300-121">The **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) entry is similar to **PR_SERVICE_DLL_NAME**; it indicates the filename for the DLL that contains the service provider.</span></span> <span data-ttu-id="6d300-122">消息服务代码可能具有相同的 DLL 文件中其服务提供商之一存储或作为单独的 DLL 存在。</span><span class="sxs-lookup"><span data-stu-id="6d300-122">Message service code may be stored with one of its service providers in the same DLL file or exist as a separate DLL.</span></span> <span data-ttu-id="6d300-123">请注意，无论目标平台; 条目中包含没有后缀MAPI 负责根据需要添加后缀。</span><span class="sxs-lookup"><span data-stu-id="6d300-123">Note that no suffix is included in the entry regardless of the target platform; MAPI takes care of adding a suffix if necessary.</span></span> 
  
<span data-ttu-id="6d300-124">**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 条目代表在服务提供程序; 的类型服务提供商将其设置为适当的预定义常量。</span><span class="sxs-lookup"><span data-stu-id="6d300-124">**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) entry represents the type of service provider; service providers set it to the appropriate predefined constant.</span></span> <span data-ttu-id="6d300-125">有效值包括 MAPI_STORE_PROVIDER、 MAPI_TRANSPORT_PROVIDER 和 MAPI_AB_PROVIDER。</span><span class="sxs-lookup"><span data-stu-id="6d300-125">Valid values include MAPI_STORE_PROVIDER, MAPI_TRANSPORT_PROVIDER, and MAPI_AB_PROVIDER.</span></span>
  
<span data-ttu-id="6d300-126">适用于消息服务和服务提供商的另一个属性条目， **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 条目指示选项。</span><span class="sxs-lookup"><span data-stu-id="6d300-126">Another property entry that applies to both message services and service providers, the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) entry indicates options.</span></span> <span data-ttu-id="6d300-127">此属性的项的设置将不同根据服务提供商。</span><span class="sxs-lookup"><span data-stu-id="6d300-127">The settings for this property entry can differ depending on the service provider.</span></span> <span data-ttu-id="6d300-128">例如，某些消息存储提供程序可能设置**PR_RESOURCE_FLAGS**为 STATUS_NO_DEFAULT_STORE 如果从不用作默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="6d300-128">For example, some message store providers might set **PR_RESOURCE_FLAGS** to STATUS_NO_DEFAULT_STORE if they can never operate as the default message store.</span></span> 
  
<span data-ttu-id="6d300-129">服务提供程序节的三个示例按照。</span><span class="sxs-lookup"><span data-stu-id="6d300-129">Three examples of service provider sections follow.</span></span> <span data-ttu-id="6d300-130">在 **[AB Provider]** 部分，默认通讯簿服务的服务提供程序部分。</span><span class="sxs-lookup"><span data-stu-id="6d300-130">The **[AB Provider]** section is the service provider section for the Default Address Book service.</span></span> <span data-ttu-id="6d300-131">**[MsgService Prov1]** 和 **[MsgService Prov2]** 部分属于我自己服务;第一个是通讯簿提供程序部分和第二个是消息存储提供程序部分。</span><span class="sxs-lookup"><span data-stu-id="6d300-131">The **[MsgService Prov1]** and **[MsgService Prov2]** sections belong to My Own Service; the first is an address-book provider section and the second is a message-store provider section.</span></span> 
  
```cpp
[AB Provider]
PR_DISPLAY_NAME=Default Address Book
PR_PROVIDER_DISPLAY=Default Address Book
PR_PROVIDER_DLL_NAME=AB.DLL
PR_RESOURCE_TYPE=MAPI_AB_PROVIDER
6600001e=C:\WINNT35\System32\DEFAB.TXT
[MsgService Prov1]
PR_DISPLAY_NAME=My Own Service
PR_PROVIDER_DISPLAY=My Own Address Book
PR_PROVIDER_DLL_NAME=MYXXX.DLL
PR_RESOURCE_TYPE=MAPI_AB_PROVIDER
[MsgService Prov2]
PR_DISPLAY_NAME=My Folders
PR_PROVIDER_DISPLAY=My Own Message Store
PR_RESOURCE_TYPE=MAPI_STORE_PROVIDER
PR_PROVIDER_DLL_NAME=MYZZZ.DLL
PR_RESOURCE_FLAGS=STATUS_NO_DEFAULT_STORE
66060003=00000000
66030003=00000000
34140102=78b2fa70aff711cd9bc800aa002fc45a
66090003=06000000
660A0003=03000000

```


