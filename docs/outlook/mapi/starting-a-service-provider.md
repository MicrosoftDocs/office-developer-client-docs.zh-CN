---
title: 启动的服务提供商
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c4b61cc3-d9fe-4616-a05c-d1e4096b5abd
description: 上次修改时间： 2015 年 12 月 7 日
ms.openlocfilehash: 99f47ee4fe990b0e77fcf868977b72d83bfdbac7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778874"
---
# <a name="starting-a-service-provider"></a><span data-ttu-id="76bfd-103">启动的服务提供商</span><span class="sxs-lookup"><span data-stu-id="76bfd-103">Starting a Service Provider</span></span>

 
  
<span data-ttu-id="76bfd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="76bfd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="76bfd-105">在某些点客户端的 MAPI，启动会话后将启动服务提供商。</span><span class="sxs-lookup"><span data-stu-id="76bfd-105">At some point after a client starts a session with MAPI, your service provider will be started.</span></span> <span data-ttu-id="76bfd-106">当客户端请求其服务已启动传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="76bfd-106">Transport providers are started when a client makes a request for their services.</span></span> <span data-ttu-id="76bfd-107">地址簿和消息存储提供程序已启动客户端的登录过程。</span><span class="sxs-lookup"><span data-stu-id="76bfd-107">Address book and message store providers are started during the client's logon process.</span></span>
  
<span data-ttu-id="76bfd-108">在客户端调用[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md)加载通讯簿提供程序的配置文件和[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)加载特定的邮件存储提供程序中包含的每个。</span><span class="sxs-lookup"><span data-stu-id="76bfd-108">A client calls [IMAPISession::OpenAddressBook](imapisession-openaddressbook.md) to load each of the address book providers included in the profile and [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) to load a specific message store provider.</span></span> <span data-ttu-id="76bfd-109">通讯簿提供程序的一部分的消息服务已启动之前的任何服务中的其他提供程序。</span><span class="sxs-lookup"><span data-stu-id="76bfd-109">Address book providers that are part of a message service are started before any of the other providers in the service.</span></span> 
  
<span data-ttu-id="76bfd-110">MAPI 启动每个服务提供商活动配置文件中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="76bfd-110">MAPI starts each service provider in the active profile by doing the following:</span></span>
  
- <span data-ttu-id="76bfd-111">配置文件中查找其 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="76bfd-111">Locating the name of its DLL in the profile.</span></span> <span data-ttu-id="76bfd-112">您所需的 Mapisvc.inf 配置文件，以确保它显示在配置文件中注册的提供程序 DLL 名称。</span><span class="sxs-lookup"><span data-stu-id="76bfd-112">You are required to register the name of your provider DLL in the Mapisvc.inf configuration file to ensure that it appears in the profile.</span></span> <span data-ttu-id="76bfd-113">服务提供商添加到配置文件，分别或作为消息服务的一部分时, 的所有 **[服务提供商]** 部分从 Mapisvc.inf 适用于您的提供商的复制到配置文件。</span><span class="sxs-lookup"><span data-stu-id="76bfd-113">When your service provider is added to a profile, either individually or as part of a message service, all of the **[Service Provider]** sections from Mapisvc.inf that apply to your provider are copied into the profile.</span></span> <span data-ttu-id="76bfd-114">有关 Mapisvc.inf 结构的详细信息，请参阅[的 MapiSvc.inf 文件格式](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="76bfd-114">For more information about the structure of Mapisvc.inf, see [File Format of MapiSvc.inf](file-format-of-mapisvc-inf.md).</span></span>
    
- <span data-ttu-id="76bfd-115">调用 Windows API 函数**LoadLibrary**加载 DLL。</span><span class="sxs-lookup"><span data-stu-id="76bfd-115">Calling the Windows API function **LoadLibrary** to load the DLL.</span></span> <span data-ttu-id="76bfd-116">由于 MAPI 调用**LoadLibrary**一种每次它使用 （无论是否它已加载） 服务提供程序 DLL 或只在首次，服务提供商必须进行假设将加载的次数。</span><span class="sxs-lookup"><span data-stu-id="76bfd-116">Because MAPI calls **LoadLibrary** either every time it uses a service provider DLL (regardless of whether it has already been loaded) or only the first time, your service provider must not make assumptions about the number of times that it will be loaded.</span></span> <span data-ttu-id="76bfd-117">**LoadLibrary**每次调用，MAPI 调用 Windows API 函数**句**时不再需要 DLL 的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="76bfd-117">For every call to **LoadLibrary**, MAPI makes a call to the Windows API function **FreeLibrary** when a service provider DLL is no longer needed.</span></span> 
    
- <span data-ttu-id="76bfd-118">为提供程序调用入口点函数。</span><span class="sxs-lookup"><span data-stu-id="76bfd-118">Calling the entry point function for the provider.</span></span> <span data-ttu-id="76bfd-119">MAPI 呼叫提供商的入口点函数启动登录过程。</span><span class="sxs-lookup"><span data-stu-id="76bfd-119">MAPI calls your provider's entry point function to initiate the logon process.</span></span> <span data-ttu-id="76bfd-120">入口点函数确保您使用的服务提供程序接口 (SPI) 正在使用 MAPI 的版本与之兼容的版本。</span><span class="sxs-lookup"><span data-stu-id="76bfd-120">Entry point functions ensure that you are using a version of the service provider interface (SPI) that is compatible with the version being used by MAPI.</span></span> <span data-ttu-id="76bfd-121">这些函数还返回到新创建提供商对象的指针。</span><span class="sxs-lookup"><span data-stu-id="76bfd-121">These functions also return pointers to newly created provider objects.</span></span> <span data-ttu-id="76bfd-122">有关创建一个条目的详细信息指向函数提供程序，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="76bfd-122">For more information about creating an entry point function for your provider, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="76bfd-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76bfd-123">See also</span></span>



[<span data-ttu-id="76bfd-124">MAPI 服务提供商</span><span class="sxs-lookup"><span data-stu-id="76bfd-124">MAPI Service Providers</span></span>](mapi-service-providers.md)

