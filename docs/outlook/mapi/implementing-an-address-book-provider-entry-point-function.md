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
ms.openlocfilehash: b60a80bc0ede0c2800f6cfd98a98f498b93a1d8c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775793"
---
# <a name="implementing-an-address-book-provider-entry-point-function"></a><span data-ttu-id="f1bca-103">实现通讯簿提供程序入口点函数</span><span class="sxs-lookup"><span data-stu-id="f1bca-103">Implementing an Address Book Provider Entry Point Function</span></span>

  
  
<span data-ttu-id="f1bca-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f1bca-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f1bca-105">当客户端应用程序调用[MAPILogonEx](mapilogonex.md)开始使用包含通讯簿提供程序的配置文件的会话时，MAPI 加载您的提供商和所有其他人的配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="f1bca-105">When a client application calls [MAPILogonEx](mapilogonex.md) to begin a session using a profile that contains your address book provider, MAPI loads your provider and all others that are part of the profile.</span></span> <span data-ttu-id="f1bca-106">MAPI 提供程序的入口点函数的名称的学习通过查看配置文件中。</span><span class="sxs-lookup"><span data-stu-id="f1bca-106">MAPI learns of the name of your provider's entry point function by looking in the profile.</span></span> <span data-ttu-id="f1bca-107">请记住此函数不是 DLL 入口点函数; 相同请参阅**DllMain** Win32 文档中的文档。</span><span class="sxs-lookup"><span data-stu-id="f1bca-107">Remember that this function is not the same as a DLL entry point function; see the documentation for **DllMain** in the Win32 documentation.</span></span> 
  
<span data-ttu-id="f1bca-108">有的每个通讯簿提供程序配置文件部分中包含的多个条目，其中某些必须 mapisvc.inf 配置文件中出现。</span><span class="sxs-lookup"><span data-stu-id="f1bca-108">There are several entries, some of which must appear in the mapisvc.inf configuration file, that are included in the profile section of every address book provider.</span></span> <span data-ttu-id="f1bca-109">下表列出了这些模板部分条目和 mapisvc.inf 文件必须包括它们。</span><span class="sxs-lookup"><span data-stu-id="f1bca-109">The following table lists these profile section entries and whether or not the mapisvc.inf file must include them.</span></span>
  
|<span data-ttu-id="f1bca-110">**配置文件节项**</span><span class="sxs-lookup"><span data-stu-id="f1bca-110">**Profile section entry**</span></span>|<span data-ttu-id="f1bca-111">**mapisvc.inf 要求**</span><span class="sxs-lookup"><span data-stu-id="f1bca-111">**mapisvc.inf requirement**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f1bca-112">PR_DISPLAY_NAME =_字符串_</span><span class="sxs-lookup"><span data-stu-id="f1bca-112">PR_DISPLAY_NAME= _string_</span></span> <br/> |<span data-ttu-id="f1bca-113">可选</span><span class="sxs-lookup"><span data-stu-id="f1bca-113">Optional</span></span>  <br/> |
|<span data-ttu-id="f1bca-114">PR_PROVIDER_DISPLAY =_字符串_</span><span class="sxs-lookup"><span data-stu-id="f1bca-114">PR_PROVIDER_DISPLAY= _string_</span></span> <br/> |<span data-ttu-id="f1bca-115">必需</span><span class="sxs-lookup"><span data-stu-id="f1bca-115">Required</span></span>  <br/> |
|<span data-ttu-id="f1bca-116">PR_PROVIDER_DLL_NAME = _DLL 文件名_</span><span class="sxs-lookup"><span data-stu-id="f1bca-116">PR_PROVIDER_DLL_NAME= _DLL filename_</span></span> <br/> |<span data-ttu-id="f1bca-117">必需</span><span class="sxs-lookup"><span data-stu-id="f1bca-117">Required</span></span>  <br/> |
|<span data-ttu-id="f1bca-118">PR_RESOURCE_TYPE =_长_</span><span class="sxs-lookup"><span data-stu-id="f1bca-118">PR_RESOURCE_TYPE= _long_</span></span> <br/> |<span data-ttu-id="f1bca-119">必需</span><span class="sxs-lookup"><span data-stu-id="f1bca-119">Required</span></span>  <br/> |
|<span data-ttu-id="f1bca-120">PR_RESOURCE_FLAGS =_位掩码_</span><span class="sxs-lookup"><span data-stu-id="f1bca-120">PR_RESOURCE_FLAGS= _bitmask_</span></span> <br/> |<span data-ttu-id="f1bca-121">可选</span><span class="sxs-lookup"><span data-stu-id="f1bca-121">Optional</span></span>  <br/> |
   
<span data-ttu-id="f1bca-122">通过调用其配置文件部分[IMAPIProp::SetProps](imapiprop-setprops.md)方法来直接或间接通过修改 MAPISVC.INF，通讯簿提供程序可以发出此信息传入一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="f1bca-122">Your address book provider can place this information into a profile directly by calling its profile section's [IMAPIProp::SetProps](imapiprop-setprops.md) method or indirectly by modifying MAPISVC.INF.</span></span> <span data-ttu-id="f1bca-123">配置文件是构建使用 MAPISVC 中的相关信息。选定的服务提供程序或消息服务的 INF。</span><span class="sxs-lookup"><span data-stu-id="f1bca-123">Profiles are built using the relevant information in MAPISVC.INF for the selected service providers or message services.</span></span> <span data-ttu-id="f1bca-124">有关的组织和 MAPISVC 内容的详细信息。INF，请参阅[的 MapiSvc.inf 文件格式](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="f1bca-124">For more information about the organization and contents of MAPISVC.INF, see [File Format of MapiSvc.inf](file-format-of-mapisvc-inf.md).</span></span>
  
<span data-ttu-id="f1bca-125">通讯簿提供程序的 DLL 入口点函数的名称必须是[ABProviderInit](abproviderinit.md) ，并且它必须符合**ABProviderInit**原型。</span><span class="sxs-lookup"><span data-stu-id="f1bca-125">The name of your address book provider's DLL entry point function must be [ABProviderInit](abproviderinit.md) and it must conform to the **ABProviderInit** prototype.</span></span> <span data-ttu-id="f1bca-126">在您的提供商 DLL 入口点函数中，执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="f1bca-126">Perform the following tasks in your provider's DLL entry point function:</span></span> 
  
- <span data-ttu-id="f1bca-127">检查服务提供程序接口 (SPI) 以确保 MAPI 使用与使用通讯簿提供程序的版本兼容版本的版本。</span><span class="sxs-lookup"><span data-stu-id="f1bca-127">Check the version of the service provider interface (SPI) to make sure MAPI is using a version that is compatible with the version that your address book provider is using.</span></span>
    
- <span data-ttu-id="f1bca-128">实例化通讯簿提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="f1bca-128">Instantiate an address book provider object.</span></span>
    
<span data-ttu-id="f1bca-129">不要在此函数调用**MAPIInitialize**或**MAPIUninitialize** 。</span><span class="sxs-lookup"><span data-stu-id="f1bca-129">Do not call either **MAPIInitialize** or **MAPIUninitialize** in this function.</span></span> 
  
<span data-ttu-id="f1bca-130">DLL 入口点函数实例化提供商对象，并返回到 MAPI 指向该对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f1bca-130">The DLL entry point function instantiates a provider object and returns to MAPI a pointer to that object.</span></span> 
  

