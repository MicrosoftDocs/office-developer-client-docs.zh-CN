---
title: mapisvc.inf 服务提供程序部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ab17dcf2-409b-4a57-9cc4-5794f995cd3e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ea192ec6356cc3b929bf8379567144d3a54223f2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405560"
---
# <a name="mapisvcinf-service-provider-sections"></a><span data-ttu-id="cce6d-103">mapisvc.inf 服务提供程序部分</span><span class="sxs-lookup"><span data-stu-id="cce6d-103">MapiSvc.inf Service Provider Sections</span></span>

<span data-ttu-id="cce6d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cce6d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cce6d-105">对于前面的 "邮件服务" 一节中的 "**提供程序**" 条目中列出的每个条目, mapisvc.inf 都包含一个 "服务提供程序" 部分。</span><span class="sxs-lookup"><span data-stu-id="cce6d-105">Mapisvc.inf includes one service provider section for each of the entries listed in the **Providers** entry in the preceding message services section.</span></span> <span data-ttu-id="cce6d-106">**服务**提供程序节类似于 "邮件服务" 部分, 这两种类型的节都包含以下格式的条目:</span><span class="sxs-lookup"><span data-stu-id="cce6d-106">**Service** provider sections are similar to message service sections in that both types of sections contain entries in this format:</span></span> 
  
<span data-ttu-id="cce6d-107">**属性标记**= 属性值</span><span class="sxs-lookup"><span data-stu-id="cce6d-107">**property tag** = property value</span></span> 
  
<span data-ttu-id="cce6d-108">但是, 服务提供程序部分和邮件服务节各不相同, 这种属性条目是服务提供商部分中的唯一条目类型。</span><span class="sxs-lookup"><span data-stu-id="cce6d-108">However, service provider sections and message service sections differ in that such property entries are the only type of entry included in service provider sections.</span></span> <span data-ttu-id="cce6d-109">服务提供商可能没有任何附加或链接的部分;所有服务提供程序信息必须包含在一节中。</span><span class="sxs-lookup"><span data-stu-id="cce6d-109">There can be no additional or linked sections for service providers; all service provider information must be contained within the one section.</span></span> 
  
<span data-ttu-id="cce6d-110">在 "邮件服务" 部分中设置的一些属性也是在服务提供商部分中设置的, 因为这些属性对这两个部分都有意义。</span><span class="sxs-lookup"><span data-stu-id="cce6d-110">Some of the properties set in message service sections are also set in service provider sections because these properties make sense for both.</span></span> <span data-ttu-id="cce6d-111">**PR_DISPLAY_NAME**属性是一个示例。</span><span class="sxs-lookup"><span data-stu-id="cce6d-111">The **PR_DISPLAY_NAME** property is an example.</span></span> <span data-ttu-id="cce6d-112">服务提供程序和邮件服务都有一个用于在配置用户界面中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="cce6d-112">Both service providers and message services have a name that is used for display in the configuration user interface.</span></span> <span data-ttu-id="cce6d-113">根据服务提供商的不同, 该名称可能是相同的, 也可能不相同。</span><span class="sxs-lookup"><span data-stu-id="cce6d-113">Depending on the service provider, that name may or may not be the same.</span></span> <span data-ttu-id="cce6d-114">其他属性特定于服务提供商。</span><span class="sxs-lookup"><span data-stu-id="cce6d-114">Other properties are specific to service providers.</span></span> 
  
<span data-ttu-id="cce6d-115">典型的服务提供程序部分包括以下各项, 它们都是必需的:</span><span class="sxs-lookup"><span data-stu-id="cce6d-115">Typical service provider sections include the following entries, all of which are required:</span></span>
  
<span data-ttu-id="cce6d-116">**PR_DISPLAY_NAME** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="cce6d-116">**PR_DISPLAY_NAME** =  _string_</span></span>
  
<span data-ttu-id="cce6d-117">**PR_PROVIDER_DISPLAY** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="cce6d-117">**PR_PROVIDER_DISPLAY** =  _string_</span></span>
  
<span data-ttu-id="cce6d-118">\*\*\*\* =  _DLL 文件的 PR_PROVIDER_DLL_NAME 名称_</span><span class="sxs-lookup"><span data-stu-id="cce6d-118">**PR_PROVIDER_DLL_NAME** =  _name of DLL file_</span></span>
  
<span data-ttu-id="cce6d-119">**PR_RESOURCE_TYPE** =  _long_</span><span class="sxs-lookup"><span data-stu-id="cce6d-119">**PR_RESOURCE_TYPE** =  _long_</span></span>
  
<span data-ttu-id="cce6d-120">**PR_RESOURCE_FLAGS** =  _位掩码_</span><span class="sxs-lookup"><span data-stu-id="cce6d-120">**PR_RESOURCE_FLAGS** =  _bitmask_</span></span>
  
<span data-ttu-id="cce6d-121">**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 条目类似于**PR_SERVICE_DLL_NAME**;它指示包含服务提供程序的 DLL 的文件名。</span><span class="sxs-lookup"><span data-stu-id="cce6d-121">The **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) entry is similar to **PR_SERVICE_DLL_NAME**; it indicates the filename for the DLL that contains the service provider.</span></span> <span data-ttu-id="cce6d-122">邮件服务代码可以与它的一个服务提供程序存储在同一个 dll 文件中或作为一个单独的 DLL 存在。</span><span class="sxs-lookup"><span data-stu-id="cce6d-122">Message service code may be stored with one of its service providers in the same DLL file or exist as a separate DLL.</span></span> <span data-ttu-id="cce6d-123">请注意, 在条目中不包含任何后缀, 无论目标平台是什么;如果需要, MAPI 将负责添加后缀。</span><span class="sxs-lookup"><span data-stu-id="cce6d-123">Note that no suffix is included in the entry regardless of the target platform; MAPI takes care of adding a suffix if necessary.</span></span> 
  
<span data-ttu-id="cce6d-124">**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 条目表示服务提供程序的类型;服务提供程序将其设置为适当的预定义常量。</span><span class="sxs-lookup"><span data-stu-id="cce6d-124">**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) entry represents the type of service provider; service providers set it to the appropriate predefined constant.</span></span> <span data-ttu-id="cce6d-125">有效值包括 MAPI_STORE_PROVIDER、MAPI_TRANSPORT_PROVIDER 和 MAPI_AB_PROVIDER。</span><span class="sxs-lookup"><span data-stu-id="cce6d-125">Valid values include MAPI_STORE_PROVIDER, MAPI_TRANSPORT_PROVIDER, and MAPI_AB_PROVIDER.</span></span>
  
<span data-ttu-id="cce6d-126">另一个适用于邮件服务和服务提供程序的属性项, **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 条目指示选项。</span><span class="sxs-lookup"><span data-stu-id="cce6d-126">Another property entry that applies to both message services and service providers, the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) entry indicates options.</span></span> <span data-ttu-id="cce6d-127">此属性项的设置可能会有所不同, 具体取决于服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="cce6d-127">The settings for this property entry can differ depending on the service provider.</span></span> <span data-ttu-id="cce6d-128">例如, 某些邮件存储提供程序可能会将**PR_RESOURCE_FLAGS**设置为 STATUS_NO_DEFAULT_STORE (如果它们永远不能作为默认邮件存储区运行)。</span><span class="sxs-lookup"><span data-stu-id="cce6d-128">For example, some message store providers might set **PR_RESOURCE_FLAGS** to STATUS_NO_DEFAULT_STORE if they can never operate as the default message store.</span></span> 
  
<span data-ttu-id="cce6d-129">下面是三个服务提供程序部分的示例。</span><span class="sxs-lookup"><span data-stu-id="cce6d-129">Three examples of service provider sections follow.</span></span> <span data-ttu-id="cce6d-130">**[AB 提供程序]** 一节是默认通讯簿服务的服务提供程序部分。</span><span class="sxs-lookup"><span data-stu-id="cce6d-130">The **[AB Provider]** section is the service provider section for the Default Address Book service.</span></span> <span data-ttu-id="cce6d-131">**[MsgService Prov1]** 和 **[MsgService Prov2]** 节属于我自己的服务;第一个是 "通讯簿提供程序" 部分, 第二个是 "邮件存储提供程序" 部分。</span><span class="sxs-lookup"><span data-stu-id="cce6d-131">The **[MsgService Prov1]** and **[MsgService Prov2]** sections belong to My Own Service; the first is an address-book provider section and the second is a message-store provider section.</span></span> 
  
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


