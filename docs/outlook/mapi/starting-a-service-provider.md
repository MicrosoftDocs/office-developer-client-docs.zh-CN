---
title: 启动服务提供程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c4b61cc3-d9fe-4616-a05c-d1e4096b5abd
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: f67976681ef0283c86e1c09c49e531572668ff50
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439553"
---
# <a name="starting-a-service-provider"></a><span data-ttu-id="80bc9-103">启动服务提供程序</span><span class="sxs-lookup"><span data-stu-id="80bc9-103">Starting a Service Provider</span></span>

 
  
<span data-ttu-id="80bc9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="80bc9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="80bc9-105">在客户端启动与 MAPI 的会话之后, 在某个时间点将启动服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="80bc9-105">At some point after a client starts a session with MAPI, your service provider will be started.</span></span> <span data-ttu-id="80bc9-106">当客户端请求服务时, 将启动传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="80bc9-106">Transport providers are started when a client makes a request for their services.</span></span> <span data-ttu-id="80bc9-107">通讯簿和邮件存储提供程序在客户端登录过程中启动。</span><span class="sxs-lookup"><span data-stu-id="80bc9-107">Address book and message store providers are started during the client's logon process.</span></span>
  
<span data-ttu-id="80bc9-108">客户端调用[IMAPISession:: OpenAddressBook](imapisession-openaddressbook.md)以加载配置文件中包含的每个通讯簿提供程序, 并使用[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)加载特定的邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="80bc9-108">A client calls [IMAPISession::OpenAddressBook](imapisession-openaddressbook.md) to load each of the address book providers included in the profile and [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) to load a specific message store provider.</span></span> <span data-ttu-id="80bc9-109">作为邮件服务一部分的通讯簿提供程序在服务中的任何其他提供程序之前启动。</span><span class="sxs-lookup"><span data-stu-id="80bc9-109">Address book providers that are part of a message service are started before any of the other providers in the service.</span></span> 
  
<span data-ttu-id="80bc9-110">MAPI 通过执行以下操作来启动活动配置文件中的每个服务提供程序:</span><span class="sxs-lookup"><span data-stu-id="80bc9-110">MAPI starts each service provider in the active profile by doing the following:</span></span>
  
- <span data-ttu-id="80bc9-111">在配置文件中查找其 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="80bc9-111">Locating the name of its DLL in the profile.</span></span> <span data-ttu-id="80bc9-112">您需要在 mapisvc.inf 配置文件中注册提供程序 DLL 的名称, 以确保它出现在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="80bc9-112">You are required to register the name of your provider DLL in the Mapisvc.inf configuration file to ensure that it appears in the profile.</span></span> <span data-ttu-id="80bc9-113">将服务提供程序添加到配置文件时 (单独或作为邮件服务的一部分), 所有 **[服务提供程序]** 从适用于您的提供程序的 mapisvc.inf 部分将复制到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="80bc9-113">When your service provider is added to a profile, either individually or as part of a message service, all of the **[Service Provider]** sections from Mapisvc.inf that apply to your provider are copied into the profile.</span></span> <span data-ttu-id="80bc9-114">有关 mapisvc.inf 结构的详细信息, 请参阅[mapisvc.inf 的文件格式](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="80bc9-114">For more information about the structure of Mapisvc.inf, see [File Format of MapiSvc.inf](file-format-of-mapisvc-inf.md).</span></span>
    
- <span data-ttu-id="80bc9-115">调用 Windows API 函数**LoadLibrary**以加载 DLL。</span><span class="sxs-lookup"><span data-stu-id="80bc9-115">Calling the Windows API function **LoadLibrary** to load the DLL.</span></span> <span data-ttu-id="80bc9-116">由于 MAPI 会在每次使用服务提供程序 DLL 时 (无论是否已加载) 或仅在首次使用服务提供程序 DLL 时调用**LoadLibrary** , 因此服务提供程序不一定会对其加载次数做出假设。</span><span class="sxs-lookup"><span data-stu-id="80bc9-116">Because MAPI calls **LoadLibrary** either every time it uses a service provider DLL (regardless of whether it has already been loaded) or only the first time, your service provider must not make assumptions about the number of times that it will be loaded.</span></span> <span data-ttu-id="80bc9-117">对于每个**LoadLibrary**调用, MAPI 会在不再需要服务提供程序 DLL 时调用 Windows API 函数**FreeLibrary** 。</span><span class="sxs-lookup"><span data-stu-id="80bc9-117">For every call to **LoadLibrary**, MAPI makes a call to the Windows API function **FreeLibrary** when a service provider DLL is no longer needed.</span></span> 
    
- <span data-ttu-id="80bc9-118">调用提供程序的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="80bc9-118">Calling the entry point function for the provider.</span></span> <span data-ttu-id="80bc9-119">MAPI 调用提供程序的入口点函数来启动登录过程。</span><span class="sxs-lookup"><span data-stu-id="80bc9-119">MAPI calls your provider's entry point function to initiate the logon process.</span></span> <span data-ttu-id="80bc9-120">入口点函数确保您使用的服务提供程序接口 (SPI) 版本与 MAPI 所使用的版本兼容。</span><span class="sxs-lookup"><span data-stu-id="80bc9-120">Entry point functions ensure that you are using a version of the service provider interface (SPI) that is compatible with the version being used by MAPI.</span></span> <span data-ttu-id="80bc9-121">这些函数还返回指向新创建的提供程序对象的指针。</span><span class="sxs-lookup"><span data-stu-id="80bc9-121">These functions also return pointers to newly created provider objects.</span></span> <span data-ttu-id="80bc9-122">有关为提供程序创建入口点函数的详细信息, 请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="80bc9-122">For more information about creating an entry point function for your provider, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="80bc9-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80bc9-123">See also</span></span>



[<span data-ttu-id="80bc9-124">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="80bc9-124">MAPI Service Providers</span></span>](mapi-service-providers.md)

