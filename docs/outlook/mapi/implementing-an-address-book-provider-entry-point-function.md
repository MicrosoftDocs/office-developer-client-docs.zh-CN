---
title: 实现通讯簿提供程序入口点函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9375b351-1c84-4728-bcdf-e3e7a44820ed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 00b3b30101ee1efb984cf45afb35b0b085d545ac
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409711"
---
# <a name="implementing-an-address-book-provider-entry-point-function"></a><span data-ttu-id="6383f-103">实现通讯簿提供程序入口点函数</span><span class="sxs-lookup"><span data-stu-id="6383f-103">Implementing an Address Book Provider Entry Point Function</span></span>

  
  
<span data-ttu-id="6383f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6383f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6383f-105">当客户端应用程序调用 [MAPILogonEx](mapilogonex.md) 以使用包含通讯簿提供程序的配置文件开始会话时，MAPI 将加载您的提供程序以及属于该配置文件的所有其他项。</span><span class="sxs-lookup"><span data-stu-id="6383f-105">When a client application calls [MAPILogonEx](mapilogonex.md) to begin a session using a profile that contains your address book provider, MAPI loads your provider and all others that are part of the profile.</span></span> <span data-ttu-id="6383f-106">MAPI 通过查看配置文件来了解提供程序的入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="6383f-106">MAPI learns of the name of your provider's entry point function by looking in the profile.</span></span> <span data-ttu-id="6383f-107">请记住，此函数与 DLL 入口点函数不同;请参阅 Win32 文档中 **的 DllMain** 文档。</span><span class="sxs-lookup"><span data-stu-id="6383f-107">Remember that this function is not the same as a DLL entry point function; see the documentation for **DllMain** in the Win32 documentation.</span></span> 
  
<span data-ttu-id="6383f-108">有几个条目必须出现在 mapisvc.inf 配置文件中，其中包括每个通讯簿提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="6383f-108">There are several entries, some of which must appear in the mapisvc.inf configuration file, that are included in the profile section of every address book provider.</span></span> <span data-ttu-id="6383f-109">下表列出了这些配置文件节条目以及 mapisvc.inf 文件是否必须包含它们。</span><span class="sxs-lookup"><span data-stu-id="6383f-109">The following table lists these profile section entries and whether or not the mapisvc.inf file must include them.</span></span>
  
|<span data-ttu-id="6383f-110">**配置文件节条目**</span><span class="sxs-lookup"><span data-stu-id="6383f-110">**Profile section entry**</span></span>|<span data-ttu-id="6383f-111">**mapisvc.inf 要求**</span><span class="sxs-lookup"><span data-stu-id="6383f-111">**mapisvc.inf requirement**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6383f-112">PR_DISPLAY_NAME= _string_</span><span class="sxs-lookup"><span data-stu-id="6383f-112">PR_DISPLAY_NAME= _string_</span></span> <br/> |<span data-ttu-id="6383f-113">可选</span><span class="sxs-lookup"><span data-stu-id="6383f-113">Optional</span></span>  <br/> |
|<span data-ttu-id="6383f-114">PR_PROVIDER_DISPLAY= _string_</span><span class="sxs-lookup"><span data-stu-id="6383f-114">PR_PROVIDER_DISPLAY= _string_</span></span> <br/> |<span data-ttu-id="6383f-115">必需</span><span class="sxs-lookup"><span data-stu-id="6383f-115">Required</span></span>  <br/> |
|<span data-ttu-id="6383f-116">PR_PROVIDER_DLL_NAME= _DLL 文件名_</span><span class="sxs-lookup"><span data-stu-id="6383f-116">PR_PROVIDER_DLL_NAME= _DLL filename_</span></span> <br/> |<span data-ttu-id="6383f-117">必需</span><span class="sxs-lookup"><span data-stu-id="6383f-117">Required</span></span>  <br/> |
|<span data-ttu-id="6383f-118">PR_RESOURCE_TYPE= _long_</span><span class="sxs-lookup"><span data-stu-id="6383f-118">PR_RESOURCE_TYPE= _long_</span></span> <br/> |<span data-ttu-id="6383f-119">必需</span><span class="sxs-lookup"><span data-stu-id="6383f-119">Required</span></span>  <br/> |
|<span data-ttu-id="6383f-120">PR_RESOURCE_FLAGS= _位掩码_</span><span class="sxs-lookup"><span data-stu-id="6383f-120">PR_RESOURCE_FLAGS= _bitmask_</span></span> <br/> |<span data-ttu-id="6383f-121">可选</span><span class="sxs-lookup"><span data-stu-id="6383f-121">Optional</span></span>  <br/> |
   
<span data-ttu-id="6383f-122">通讯簿提供程序可以通过调用配置文件节的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法，或者通过修改 MAPISVC.INF 间接将此信息直接放入配置文件中。</span><span class="sxs-lookup"><span data-stu-id="6383f-122">Your address book provider can place this information into a profile directly by calling its profile section's [IMAPIProp::SetProps](imapiprop-setprops.md) method or indirectly by modifying MAPISVC.INF.</span></span> <span data-ttu-id="6383f-123">配置文件是使用 MAPISVC 中相关信息构建的。所选服务提供商或邮件服务的 INF。</span><span class="sxs-lookup"><span data-stu-id="6383f-123">Profiles are built using the relevant information in MAPISVC.INF for the selected service providers or message services.</span></span> <span data-ttu-id="6383f-124">有关 MAPISVC 组织和内容的信息。INF，请参阅 [MapiSvc.inf 的文件格式](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="6383f-124">For more information about the organization and contents of MAPISVC.INF, see [File Format of MapiSvc.inf](file-format-of-mapisvc-inf.md).</span></span>
  
<span data-ttu-id="6383f-125">通讯簿提供程序的 DLL 入口点函数的名称必须为 [ABProviderInit，](abproviderinit.md) 并且必须符合 **ABProviderInit** 原型。</span><span class="sxs-lookup"><span data-stu-id="6383f-125">The name of your address book provider's DLL entry point function must be [ABProviderInit](abproviderinit.md) and it must conform to the **ABProviderInit** prototype.</span></span> <span data-ttu-id="6383f-126">在提供程序的 DLL 入口点函数中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6383f-126">Perform the following tasks in your provider's DLL entry point function:</span></span> 
  
- <span data-ttu-id="6383f-127">检查 SPI (的服务提供商接口) 以确保 MAPI 使用的版本与通讯簿提供程序使用的版本兼容。</span><span class="sxs-lookup"><span data-stu-id="6383f-127">Check the version of the service provider interface (SPI) to make sure MAPI is using a version that is compatible with the version that your address book provider is using.</span></span>
    
- <span data-ttu-id="6383f-128">实例化通讯簿提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="6383f-128">Instantiate an address book provider object.</span></span>
    
<span data-ttu-id="6383f-129">请勿在此函数中调用 **MAPIInitialize** 或 **MAPIUninitialize。**</span><span class="sxs-lookup"><span data-stu-id="6383f-129">Do not call either **MAPIInitialize** or **MAPIUninitialize** in this function.</span></span> 
  
<span data-ttu-id="6383f-130">DLL 入口点函数实例化提供程序对象，并返回指向该对象的指针 MAPI。</span><span class="sxs-lookup"><span data-stu-id="6383f-130">The DLL entry point function instantiates a provider object and returns to MAPI a pointer to that object.</span></span> 
  

