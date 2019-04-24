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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332800"
---
# <a name="implementing-an-address-book-provider-entry-point-function"></a><span data-ttu-id="b0a5c-103">实现通讯簿提供程序入口点函数</span><span class="sxs-lookup"><span data-stu-id="b0a5c-103">Implementing an Address Book Provider Entry Point Function</span></span>

  
  
<span data-ttu-id="b0a5c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b0a5c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b0a5c-105">当客户端应用程序调用[MAPILogonEx](mapilogonex.md)以使用包含通讯簿提供程序的配置文件开始会话时, MAPI 将加载您的提供程序以及作为该配置文件一部分的所有其他项。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-105">When a client application calls [MAPILogonEx](mapilogonex.md) to begin a session using a profile that contains your address book provider, MAPI loads your provider and all others that are part of the profile.</span></span> <span data-ttu-id="b0a5c-106">MAPI 通过查看配置文件了解提供程序的入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-106">MAPI learns of the name of your provider's entry point function by looking in the profile.</span></span> <span data-ttu-id="b0a5c-107">请注意, 此函数与 DLL 入口点函数不同;请参阅 Win32 文档中有关**DllMain**的文档。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-107">Remember that this function is not the same as a DLL entry point function; see the documentation for **DllMain** in the Win32 documentation.</span></span> 
  
<span data-ttu-id="b0a5c-108">有几个条目, 其中一些必须出现在 mapisvc.inf 配置文件中, 这些条目包含在每个通讯簿提供程序的 "配置文件" 部分中。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-108">There are several entries, some of which must appear in the mapisvc.inf configuration file, that are included in the profile section of every address book provider.</span></span> <span data-ttu-id="b0a5c-109">下表列出了这些配置文件节项, 以及 mapisvc.inf 文件是否必须包含它们。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-109">The following table lists these profile section entries and whether or not the mapisvc.inf file must include them.</span></span>
  
|<span data-ttu-id="b0a5c-110">**配置文件节项**</span><span class="sxs-lookup"><span data-stu-id="b0a5c-110">**Profile section entry**</span></span>|<span data-ttu-id="b0a5c-111">**mapisvc.inf 要求**</span><span class="sxs-lookup"><span data-stu-id="b0a5c-111">**mapisvc.inf requirement**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0a5c-112">PR_DISPLAY_NAME = _string_</span><span class="sxs-lookup"><span data-stu-id="b0a5c-112">PR_DISPLAY_NAME= _string_</span></span> <br/> |<span data-ttu-id="b0a5c-113">可选</span><span class="sxs-lookup"><span data-stu-id="b0a5c-113">Optional</span></span>  <br/> |
|<span data-ttu-id="b0a5c-114">PR_PROVIDER_DISPLAY = _string_</span><span class="sxs-lookup"><span data-stu-id="b0a5c-114">PR_PROVIDER_DISPLAY= _string_</span></span> <br/> |<span data-ttu-id="b0a5c-115">必需</span><span class="sxs-lookup"><span data-stu-id="b0a5c-115">Required</span></span>  <br/> |
|<span data-ttu-id="b0a5c-116">PR_PROVIDER_DLL_NAME = _DLL 文件名_</span><span class="sxs-lookup"><span data-stu-id="b0a5c-116">PR_PROVIDER_DLL_NAME= _DLL filename_</span></span> <br/> |<span data-ttu-id="b0a5c-117">必需</span><span class="sxs-lookup"><span data-stu-id="b0a5c-117">Required</span></span>  <br/> |
|<span data-ttu-id="b0a5c-118">PR_RESOURCE_TYPE = _long_</span><span class="sxs-lookup"><span data-stu-id="b0a5c-118">PR_RESOURCE_TYPE= _long_</span></span> <br/> |<span data-ttu-id="b0a5c-119">必需</span><span class="sxs-lookup"><span data-stu-id="b0a5c-119">Required</span></span>  <br/> |
|<span data-ttu-id="b0a5c-120">PR_RESOURCE_FLAGS =_位掩码_</span><span class="sxs-lookup"><span data-stu-id="b0a5c-120">PR_RESOURCE_FLAGS= _bitmask_</span></span> <br/> |<span data-ttu-id="b0a5c-121">可选</span><span class="sxs-lookup"><span data-stu-id="b0a5c-121">Optional</span></span>  <br/> |
   
<span data-ttu-id="b0a5c-122">您的通讯簿提供程序可以通过调用其 profile 节的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法或通过修改 mapisvc.inf 来间接将此信息放入配置文件中。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-122">Your address book provider can place this information into a profile directly by calling its profile section's [IMAPIProp::SetProps](imapiprop-setprops.md) method or indirectly by modifying MAPISVC.INF.</span></span> <span data-ttu-id="b0a5c-123">配置文件是使用 mapisvc.inf 中的相关信息生成的。所选服务提供商或邮件服务的 INF。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-123">Profiles are built using the relevant information in MAPISVC.INF for the selected service providers or message services.</span></span> <span data-ttu-id="b0a5c-124">有关 mapisvc.inf 的组织和内容的详细信息。inf, 请参阅[mapisvc.inf 的文件格式](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-124">For more information about the organization and contents of MAPISVC.INF, see [File Format of MapiSvc.inf](file-format-of-mapisvc-inf.md).</span></span>
  
<span data-ttu-id="b0a5c-125">您的通讯簿提供程序的 DLL 入口点函数的名称必须为[ABProviderInit](abproviderinit.md) , 并且必须符合**ABProviderInit**原型。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-125">The name of your address book provider's DLL entry point function must be [ABProviderInit](abproviderinit.md) and it must conform to the **ABProviderInit** prototype.</span></span> <span data-ttu-id="b0a5c-126">在提供程序的 DLL 入口点函数中执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="b0a5c-126">Perform the following tasks in your provider's DLL entry point function:</span></span> 
  
- <span data-ttu-id="b0a5c-127">检查服务提供程序接口 (SPI) 的版本, 确保 MAPI 使用的版本与您的通讯簿提供程序使用的版本兼容。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-127">Check the version of the service provider interface (SPI) to make sure MAPI is using a version that is compatible with the version that your address book provider is using.</span></span>
    
- <span data-ttu-id="b0a5c-128">实例化通讯簿提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-128">Instantiate an address book provider object.</span></span>
    
<span data-ttu-id="b0a5c-129">请勿在此函数中调用**MAPIInitialize**或**MAPIUninitialize** 。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-129">Do not call either **MAPIInitialize** or **MAPIUninitialize** in this function.</span></span> 
  
<span data-ttu-id="b0a5c-130">DLL 入口点函数实例化提供程序对象, 并返回到 MAPI 指向该对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b0a5c-130">The DLL entry point function instantiates a provider object and returns to MAPI a pointer to that object.</span></span> 
  

