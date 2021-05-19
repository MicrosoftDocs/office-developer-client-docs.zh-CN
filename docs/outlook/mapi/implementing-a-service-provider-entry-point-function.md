---
title: 实现服务提供程序入口点函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 83ff54c4-86ce-4529-ae45-260dfb763b30
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 14dd11f873493e32b83dbd1960cac8ff8ef8e436
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332989"
---
# <a name="implementing-a-service-provider-entry-point-function"></a><span data-ttu-id="3d4c2-103">实现服务提供程序入口点函数</span><span class="sxs-lookup"><span data-stu-id="3d4c2-103">Implementing a Service Provider Entry Point Function</span></span>

  
  
<span data-ttu-id="3d4c2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3d4c2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3d4c2-105">每个服务提供程序 DLL 都有一个入口点函数，MAPI 会调用该函数来加载它。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-105">Every service provider DLL has an entry point function that MAPI calls to load it.</span></span> <span data-ttu-id="3d4c2-106">请注意，此入口点函数与 Win32 DLL 入口点函数 [DllMain](https://msdn.microsoft.com/library/ms682583.aspx)不同。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-106">Be aware that this entry point function is not the same as [DllMain](https://msdn.microsoft.com/library/ms682583.aspx), the Win32 DLL entry point function.</span></span>
  
<span data-ttu-id="3d4c2-107">根据提供程序的类型，提供程序入口点函数符合不同的原型。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-107">Depending on the type of your provider, your provider entry point function conforms to a different prototype.</span></span> <span data-ttu-id="3d4c2-108">MAPI 为服务提供商定义不同的入口点函数原型。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-108">MAPI defines different entry point function prototypes for service providers.</span></span>
  
|<span data-ttu-id="3d4c2-109">**Provider**</span><span class="sxs-lookup"><span data-stu-id="3d4c2-109">**Provider**</span></span>|<span data-ttu-id="3d4c2-110">**入口点函数原型**</span><span class="sxs-lookup"><span data-stu-id="3d4c2-110">**Entry point function prototype**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3d4c2-111">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="3d4c2-111">Message store providers</span></span>  <br/> |[<span data-ttu-id="3d4c2-112">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="3d4c2-112">MSProviderInit</span></span>](msproviderinit.md) <br/> |
|<span data-ttu-id="3d4c2-113">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="3d4c2-113">Transport providers</span></span>  <br/> |[<span data-ttu-id="3d4c2-114">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="3d4c2-114">XPProviderInit</span></span>](xpproviderinit.md) <br/> |
|<span data-ttu-id="3d4c2-115">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="3d4c2-115">Address book providers</span></span>  <br/> |[<span data-ttu-id="3d4c2-116">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="3d4c2-116">ABProviderInit</span></span>](abproviderinit.md) <br/> |
   
<span data-ttu-id="3d4c2-117">这些原型中的许多功能对于所有服务提供程序类型都是相同的。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-117">Much of the functionality in these prototypes is the same for all service provider types.</span></span> 
  
<span data-ttu-id="3d4c2-118">通讯簿、邮件存储和传输提供程序在入口点功能中执行以下两个主要任务：</span><span class="sxs-lookup"><span data-stu-id="3d4c2-118">Address book, message store, and transport providers perform the following two main tasks in their entry point functions:</span></span>
  
1. <span data-ttu-id="3d4c2-119">检查 SPI (接口) 以确保 MAPI 使用的版本与服务提供商使用的版本兼容。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-119">Check the version of the service provider interface (SPI) to be sure that MAPI is using a version that is compatible with the version that your service provider is using.</span></span> <span data-ttu-id="3d4c2-120">使用包含 MAPI SPI 版本的  _lpulMAPIVer_ 参数和包含 SPI 版本的  _lpulProviderVer_ 参数执行检查。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-120">Use the  _lpulMAPIVer_ parameter, which contains the MAPI SPI version, and the  _lpulProviderVer_ parameter, which contains your SPI version, to perform the check.</span></span> <span data-ttu-id="3d4c2-121">这些参数是 32 位无符号整数，由三部分组成：</span><span class="sxs-lookup"><span data-stu-id="3d4c2-121">These parameters are 32-bit unsigned integers composed of three parts:</span></span> 
    
  - <span data-ttu-id="3d4c2-122">位 24 至 31 表示主要版本。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-122">Bits 24 through 31 represent the major version.</span></span>
    
  - <span data-ttu-id="3d4c2-123">位 16 至 23 表示次要版本。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-123">Bits 16 through 23 represent the minor version.</span></span>
    
  - <span data-ttu-id="3d4c2-124">位 0 到 15 表示更新标识符。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-124">Bits 0 through 15 represent the update identifier.</span></span> <span data-ttu-id="3d4c2-125">尽管主要版本号很少更改，但次要版本号会随着 MAPI 的发布和 SPI 的更改而发生更改。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-125">Although the major version number rarely changes, the minor version number changes whenever MAPI is released and the SPI has changed.</span></span> <span data-ttu-id="3d4c2-126">更新标识符是 Microsoft 内部版本;它用于在开发过程中跟踪更改。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-126">The update identifier is the Microsoft internal build version; it is used to track changes during the development process.</span></span> <span data-ttu-id="3d4c2-127">MAPI 定义CURRENT_SPI_VERSION Mapispi.h 头文件中记录的版本常量，以指示当前的 SPI 版本。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-127">MAPI defines the CURRENT_SPI_VERSION constant, documented in the Mapispi.h header file, to indicate the present SPI version.</span></span> <span data-ttu-id="3d4c2-128">如果使用的 SPI MAPI_E_VERSION比 MAPI 使用的版本更新，请对错误检查失败。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-128">Fail your check with the error MAPI_E_VERSION if you are using a version of the SPI that is newer than the version that MAPI is using.</span></span>
    
2. <span data-ttu-id="3d4c2-129">创建提供程序对象的实例。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-129">Create an instance of a provider object.</span></span> <span data-ttu-id="3d4c2-130">由于提供程序可以多次启动和初始化，因此您应每次出现此情况时创建新实例。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-130">Because your provider can be started and initialized multiple times, you should create a new instance each time this occurs.</span></span> <span data-ttu-id="3d4c2-131">提供程序出现在由一个或多个客户端同时使用的多个配置文件中时，或者当提供程序在单个配置文件中多次出现时，提供程序将启动多次。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-131">Providers are started multiple times when they appear in multiple profiles that are in use simultaneously by one or more clients, or when they appear multiple times in a single profile.</span></span> <span data-ttu-id="3d4c2-132">正如入口点函数原型因提供程序的类型而异一样，提供程序对象的类型也不同。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-132">Just as the entry point function prototype differs depending on the type of your provider, so does the type of provider object.</span></span> 
    
    <span data-ttu-id="3d4c2-133">如果要编写通讯簿提供程序，请实现 [IABProvider ： IUnknown](iabprovideriunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-133">If you are writing an address book provider, implement [IABProvider : IUnknown](iabprovideriunknown.md).</span></span> <span data-ttu-id="3d4c2-134">如果要编写消息存储提供程序，请实现 [IMSProvider ： IUnknown](imsprovideriunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-134">If you are writing a message store provider, implement [IMSProvider : IUnknown](imsprovideriunknown.md).</span></span> <span data-ttu-id="3d4c2-135">有关详细信息，请参阅 [加载邮件存储提供程序](loading-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-135">For more information, see [Loading Message Store Providers](loading-message-store-providers.md).</span></span>
    
    <span data-ttu-id="3d4c2-136">如果要编写传输提供程序，请实现 [IXPProvider ： IUnknown](ixpprovideriunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-136">If you are writing a transport provider, implement [IXPProvider : IUnknown](ixpprovideriunknown.md).</span></span> <span data-ttu-id="3d4c2-137">有关详细信息，请参阅 [初始化传输提供程序](initializing-the-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="3d4c2-137">For more information, see [Initializing the Transport Provider](initializing-the-transport-provider.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3d4c2-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d4c2-138">See also</span></span>



[<span data-ttu-id="3d4c2-139">启动服务提供程序</span><span class="sxs-lookup"><span data-stu-id="3d4c2-139">Starting a Service Provider</span></span>](starting-a-service-provider.md)

