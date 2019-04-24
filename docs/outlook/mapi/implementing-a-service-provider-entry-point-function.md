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
# <a name="implementing-a-service-provider-entry-point-function"></a><span data-ttu-id="8157b-103">实现服务提供程序入口点函数</span><span class="sxs-lookup"><span data-stu-id="8157b-103">Implementing a Service Provider Entry Point Function</span></span>

  
  
<span data-ttu-id="8157b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8157b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8157b-105">每个服务提供程序 DLL 都有一个入口点函数, MAPI 调用它来加载它。</span><span class="sxs-lookup"><span data-stu-id="8157b-105">Every service provider DLL has an entry point function that MAPI calls to load it.</span></span> <span data-ttu-id="8157b-106">请注意, 此入口点函数与[DllMain](https://msdn.microsoft.com/library/ms682583.aspx)(Win32 DLL 入口点函数) 不同。</span><span class="sxs-lookup"><span data-stu-id="8157b-106">Be aware that this entry point function is not the same as [DllMain](https://msdn.microsoft.com/library/ms682583.aspx), the Win32 DLL entry point function.</span></span>
  
<span data-ttu-id="8157b-107">根据提供程序的类型, 提供程序入口点函数符合不同的原型。</span><span class="sxs-lookup"><span data-stu-id="8157b-107">Depending on the type of your provider, your provider entry point function conforms to a different prototype.</span></span> <span data-ttu-id="8157b-108">MAPI 为服务提供程序定义了不同的入口点函数原型。</span><span class="sxs-lookup"><span data-stu-id="8157b-108">MAPI defines different entry point function prototypes for service providers.</span></span>
  
|<span data-ttu-id="8157b-109">**Provider**</span><span class="sxs-lookup"><span data-stu-id="8157b-109">**Provider**</span></span>|<span data-ttu-id="8157b-110">**入口点函数原型**</span><span class="sxs-lookup"><span data-stu-id="8157b-110">**Entry point function prototype**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8157b-111">邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="8157b-111">Message store providers</span></span>  <br/> |[<span data-ttu-id="8157b-112">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="8157b-112">MSProviderInit</span></span>](msproviderinit.md) <br/> |
|<span data-ttu-id="8157b-113">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="8157b-113">Transport providers</span></span>  <br/> |[<span data-ttu-id="8157b-114">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="8157b-114">XPProviderInit</span></span>](xpproviderinit.md) <br/> |
|<span data-ttu-id="8157b-115">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="8157b-115">Address book providers</span></span>  <br/> |[<span data-ttu-id="8157b-116">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="8157b-116">ABProviderInit</span></span>](abproviderinit.md) <br/> |
   
<span data-ttu-id="8157b-117">对于所有服务提供程序类型, 这些原型中的许多功能都是相同的。</span><span class="sxs-lookup"><span data-stu-id="8157b-117">Much of the functionality in these prototypes is the same for all service provider types.</span></span> 
  
<span data-ttu-id="8157b-118">通讯簿、邮件存储和传输提供程序在其入口点函数中执行以下两个主要任务:</span><span class="sxs-lookup"><span data-stu-id="8157b-118">Address book, message store, and transport providers perform the following two main tasks in their entry point functions:</span></span>
  
1. <span data-ttu-id="8157b-119">检查服务提供程序接口 (SPI) 的版本, 确保 MAPI 使用的版本与您的服务提供商使用的版本兼容。</span><span class="sxs-lookup"><span data-stu-id="8157b-119">Check the version of the service provider interface (SPI) to be sure that MAPI is using a version that is compatible with the version that your service provider is using.</span></span> <span data-ttu-id="8157b-120">使用包含 MAPI SPI 版本的_lpulMAPIVer_参数以及包含 SPI 版本的_lpulProviderVer_参数, 以执行检查。</span><span class="sxs-lookup"><span data-stu-id="8157b-120">Use the  _lpulMAPIVer_ parameter, which contains the MAPI SPI version, and the  _lpulProviderVer_ parameter, which contains your SPI version, to perform the check.</span></span> <span data-ttu-id="8157b-121">这些参数是由三部分组成的32位无符号整数:</span><span class="sxs-lookup"><span data-stu-id="8157b-121">These parameters are 32-bit unsigned integers composed of three parts:</span></span> 
    
  - <span data-ttu-id="8157b-122">24到31位代表主要版本。</span><span class="sxs-lookup"><span data-stu-id="8157b-122">Bits 24 through 31 represent the major version.</span></span>
    
  - <span data-ttu-id="8157b-123">16到23位代表次要版本。</span><span class="sxs-lookup"><span data-stu-id="8157b-123">Bits 16 through 23 represent the minor version.</span></span>
    
  - <span data-ttu-id="8157b-124">0到15位表示更新标识符。</span><span class="sxs-lookup"><span data-stu-id="8157b-124">Bits 0 through 15 represent the update identifier.</span></span> <span data-ttu-id="8157b-125">尽管主要版本号很少更改, 但每当 MAPI 发布且 SPI 发生更改时, 次要版本号都会发生变化。</span><span class="sxs-lookup"><span data-stu-id="8157b-125">Although the major version number rarely changes, the minor version number changes whenever MAPI is released and the SPI has changed.</span></span> <span data-ttu-id="8157b-126">更新标识符是 Microsoft 内部内部版本;它用于跟踪在开发过程中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8157b-126">The update identifier is the Microsoft internal build version; it is used to track changes during the development process.</span></span> <span data-ttu-id="8157b-127">MAPI 定义在 Mapispi 头文件中记录的 CURRENT_SPI_VERSION 常量, 以指示目前的 SPI 版本。</span><span class="sxs-lookup"><span data-stu-id="8157b-127">MAPI defines the CURRENT_SPI_VERSION constant, documented in the Mapispi.h header file, to indicate the present SPI version.</span></span> <span data-ttu-id="8157b-128">如果您使用的 SPI 版本比 MAPI 使用的版本新, 则您的检查会失败, 并出现错误 MAPI_E_VERSION。</span><span class="sxs-lookup"><span data-stu-id="8157b-128">Fail your check with the error MAPI_E_VERSION if you are using a version of the SPI that is newer than the version that MAPI is using.</span></span>
    
2. <span data-ttu-id="8157b-129">创建提供程序对象的实例。</span><span class="sxs-lookup"><span data-stu-id="8157b-129">Create an instance of a provider object.</span></span> <span data-ttu-id="8157b-130">由于您的提供程序可以多次启动和初始化, 因此在每次发生此情况时应创建一个新实例。</span><span class="sxs-lookup"><span data-stu-id="8157b-130">Because your provider can be started and initialized multiple times, you should create a new instance each time this occurs.</span></span> <span data-ttu-id="8157b-131">当提供程序出现在多个配置文件中时, 它们会在同时由一个或多个客户端使用, 或者当它们在一个配置文件中多次出现时多次启动。</span><span class="sxs-lookup"><span data-stu-id="8157b-131">Providers are started multiple times when they appear in multiple profiles that are in use simultaneously by one or more clients, or when they appear multiple times in a single profile.</span></span> <span data-ttu-id="8157b-132">正如提供程序的类型不同, 入口点函数原型的不同之处在于提供程序对象的类型。</span><span class="sxs-lookup"><span data-stu-id="8157b-132">Just as the entry point function prototype differs depending on the type of your provider, so does the type of provider object.</span></span> 
    
    <span data-ttu-id="8157b-133">如果要编写通讯簿提供程序, 请实施[IABProvider: IUnknown](iabprovideriunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="8157b-133">If you are writing an address book provider, implement [IABProvider : IUnknown](iabprovideriunknown.md).</span></span> <span data-ttu-id="8157b-134">如果要编写邮件存储区提供程序, 请实现[IMSProvider: IUnknown](imsprovideriunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="8157b-134">If you are writing a message store provider, implement [IMSProvider : IUnknown](imsprovideriunknown.md).</span></span> <span data-ttu-id="8157b-135">有关详细信息, 请参阅[加载邮件存储提供程序](loading-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="8157b-135">For more information, see [Loading Message Store Providers](loading-message-store-providers.md).</span></span>
    
    <span data-ttu-id="8157b-136">如果要编写传输提供程序, 请实施[IXPProvider: IUnknown](ixpprovideriunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="8157b-136">If you are writing a transport provider, implement [IXPProvider : IUnknown](ixpprovideriunknown.md).</span></span> <span data-ttu-id="8157b-137">有关详细信息, 请参阅[初始化传输提供程序](initializing-the-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="8157b-137">For more information, see [Initializing the Transport Provider](initializing-the-transport-provider.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8157b-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8157b-138">See also</span></span>



[<span data-ttu-id="8157b-139">启动服务提供程序</span><span class="sxs-lookup"><span data-stu-id="8157b-139">Starting a Service Provider</span></span>](starting-a-service-provider.md)

