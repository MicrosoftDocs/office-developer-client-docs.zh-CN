---
title: MapiSvc.inf 服务提供程序部分
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
# <a name="mapisvcinf-service-provider-sections"></a><span data-ttu-id="e5282-103">MapiSvc.inf 服务提供程序部分</span><span class="sxs-lookup"><span data-stu-id="e5282-103">MapiSvc.inf Service Provider Sections</span></span>

<span data-ttu-id="e5282-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e5282-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e5282-105">Mapisvc.inf 包含一个针对前面邮件服务部分"提供程序"条目中列出的每个条目的服务提供商部分。</span><span class="sxs-lookup"><span data-stu-id="e5282-105">Mapisvc.inf includes one service provider section for each of the entries listed in the **Providers** entry in the preceding message services section.</span></span> <span data-ttu-id="e5282-106">**服务** 提供程序部分类似于邮件服务节，两种类型的节均包含以下格式的条目：</span><span class="sxs-lookup"><span data-stu-id="e5282-106">**Service** provider sections are similar to message service sections in that both types of sections contain entries in this format:</span></span> 
  
<span data-ttu-id="e5282-107">**property tag** = 属性值</span><span class="sxs-lookup"><span data-stu-id="e5282-107">**property tag** = property value</span></span> 
  
<span data-ttu-id="e5282-108">但是，服务提供程序节和邮件服务部分的不同是，此类属性条目是服务提供程序节中包含的唯一类型的条目。</span><span class="sxs-lookup"><span data-stu-id="e5282-108">However, service provider sections and message service sections differ in that such property entries are the only type of entry included in service provider sections.</span></span> <span data-ttu-id="e5282-109">服务提供程序不能有其他或链接的分区;所有服务提供程序信息必须包含在一个部分中。</span><span class="sxs-lookup"><span data-stu-id="e5282-109">There can be no additional or linked sections for service providers; all service provider information must be contained within the one section.</span></span> 
  
<span data-ttu-id="e5282-110">邮件服务部分中设置的一些属性也在服务提供程序部分中设置，因为这些属性对两者都有意义。</span><span class="sxs-lookup"><span data-stu-id="e5282-110">Some of the properties set in message service sections are also set in service provider sections because these properties make sense for both.</span></span> <span data-ttu-id="e5282-111">PR_DISPLAY_NAME **是** 一个示例。</span><span class="sxs-lookup"><span data-stu-id="e5282-111">The **PR_DISPLAY_NAME** property is an example.</span></span> <span data-ttu-id="e5282-112">服务提供程序和邮件服务的名称均用于在配置用户界面中显示。</span><span class="sxs-lookup"><span data-stu-id="e5282-112">Both service providers and message services have a name that is used for display in the configuration user interface.</span></span> <span data-ttu-id="e5282-113">根据服务提供商的不同，该名称可能相同，也可能不同。</span><span class="sxs-lookup"><span data-stu-id="e5282-113">Depending on the service provider, that name may or may not be the same.</span></span> <span data-ttu-id="e5282-114">其他属性特定于服务提供商。</span><span class="sxs-lookup"><span data-stu-id="e5282-114">Other properties are specific to service providers.</span></span> 
  
<span data-ttu-id="e5282-115">典型的服务提供程序部分包括以下条目，所有这些条目都是必需的：</span><span class="sxs-lookup"><span data-stu-id="e5282-115">Typical service provider sections include the following entries, all of which are required:</span></span>
  
<span data-ttu-id="e5282-116">**PR_DISPLAY_NAME**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="e5282-116">**PR_DISPLAY_NAME** =  _string_</span></span>
  
<span data-ttu-id="e5282-117">**PR_PROVIDER_DISPLAY**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="e5282-117">**PR_PROVIDER_DISPLAY** =  _string_</span></span>
  
<span data-ttu-id="e5282-118">**PR_PROVIDER_DLL_NAME**  =  _DLL 文件的名称_</span><span class="sxs-lookup"><span data-stu-id="e5282-118">**PR_PROVIDER_DLL_NAME** =  _name of DLL file_</span></span>
  
<span data-ttu-id="e5282-119">**PR_RESOURCE_TYPE**  =  _long_</span><span class="sxs-lookup"><span data-stu-id="e5282-119">**PR_RESOURCE_TYPE** =  _long_</span></span>
  
<span data-ttu-id="e5282-120">**PR_RESOURCE_FLAGS**  =  _位掩码_</span><span class="sxs-lookup"><span data-stu-id="e5282-120">**PR_RESOURCE_FLAGS** =  _bitmask_</span></span>
  
<span data-ttu-id="e5282-121">[PidTagProviderDllName PR_PROVIDER_DLL_NAME (PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 类似于 PR_SERVICE_DLL_NAME **;** 它指示包含服务提供商的 DLL 的文件名。</span><span class="sxs-lookup"><span data-stu-id="e5282-121">The **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) entry is similar to **PR_SERVICE_DLL_NAME**; it indicates the filename for the DLL that contains the service provider.</span></span> <span data-ttu-id="e5282-122">邮件服务代码可以与它的一个服务提供程序存储在同一 DLL 文件中，也可以作为单独的 DLL 存在。</span><span class="sxs-lookup"><span data-stu-id="e5282-122">Message service code may be stored with one of its service providers in the same DLL file or exist as a separate DLL.</span></span> <span data-ttu-id="e5282-123">请注意，无论目标平台如何，条目中均不包含后缀;MAPI 负责在必要时添加后缀。</span><span class="sxs-lookup"><span data-stu-id="e5282-123">Note that no suffix is included in the entry regardless of the target platform; MAPI takes care of adding a suffix if necessary.</span></span> 
  
<span data-ttu-id="e5282-124">**PR_RESOURCE_TYPE (** [PidTagResourceType](pidtagresourcetype-canonical-property.md)) 条目表示服务提供商的类型;服务提供程序会设置为适当的预定义常量。</span><span class="sxs-lookup"><span data-stu-id="e5282-124">**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) entry represents the type of service provider; service providers set it to the appropriate predefined constant.</span></span> <span data-ttu-id="e5282-125">有效值包括 MAPI_STORE_PROVIDER、MAPI_TRANSPORT_PROVIDER 和 MAPI_AB_PROVIDER。</span><span class="sxs-lookup"><span data-stu-id="e5282-125">Valid values include MAPI_STORE_PROVIDER, MAPI_TRANSPORT_PROVIDER, and MAPI_AB_PROVIDER.</span></span>
  
<span data-ttu-id="e5282-126">另一个同时适用于邮件服务和服务提供程序的属性项是[PidTagResourceFlags PR_RESOURCE_FLAGS (PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 指示选项。 </span><span class="sxs-lookup"><span data-stu-id="e5282-126">Another property entry that applies to both message services and service providers, the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) entry indicates options.</span></span> <span data-ttu-id="e5282-127">此属性项的设置可能因服务提供商而异。</span><span class="sxs-lookup"><span data-stu-id="e5282-127">The settings for this property entry can differ depending on the service provider.</span></span> <span data-ttu-id="e5282-128">例如，如果某些邮件存储PR_RESOURCE_FLAGS无法STATUS_NO_DEFAULT_STORE默认邮件存储，则这些提供程序可能会将邮件存储设置为默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="e5282-128">For example, some message store providers might set **PR_RESOURCE_FLAGS** to STATUS_NO_DEFAULT_STORE if they can never operate as the default message store.</span></span> 
  
<span data-ttu-id="e5282-129">以下是服务提供商各节的三个示例。</span><span class="sxs-lookup"><span data-stu-id="e5282-129">Three examples of service provider sections follow.</span></span> <span data-ttu-id="e5282-130">**[AB Provider]** 部分是默认通讯簿服务的服务提供商部分。</span><span class="sxs-lookup"><span data-stu-id="e5282-130">The **[AB Provider]** section is the service provider section for the Default Address Book service.</span></span> <span data-ttu-id="e5282-131">**[MsgService Prov1]** **和 [MsgService Prov2]** 部分属于"我的服务";第一个为通讯簿提供程序部分，第二个为邮件存储提供程序部分。</span><span class="sxs-lookup"><span data-stu-id="e5282-131">The **[MsgService Prov1]** and **[MsgService Prov2]** sections belong to My Own Service; the first is an address-book provider section and the second is a message-store provider section.</span></span> 
  
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


