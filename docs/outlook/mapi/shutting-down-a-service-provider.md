---
title: 关闭服务提供程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e518830b-0aaa-4ce4-a85a-07e4f00750a9
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: 71706fc970170f74aa5555da29d904c08c0422f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778788"
---
# <a name="shutting-down-a-service-provider"></a><span data-ttu-id="31b0f-103">关闭服务提供程序</span><span class="sxs-lookup"><span data-stu-id="31b0f-103">Shutting Down a Service Provider</span></span>

 
  
<span data-ttu-id="31b0f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="31b0f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="31b0f-105">当客户端调用[IMAPISession::Logoff](imapisession-logoff.md)方法来结束会话并关闭所有活动服务提供商时，MAPI 轮流调用以下方法：</span><span class="sxs-lookup"><span data-stu-id="31b0f-105">When a client calls the [IMAPISession::Logoff](imapisession-logoff.md) method to end the session and shut down all active service providers, MAPI in turn calls the following methods:</span></span> 
  
- <span data-ttu-id="31b0f-106">[IABLogon::Logoff](iablogon-logoff.md)地址簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="31b0f-106">[IABLogon::Logoff](iablogon-logoff.md) for address book providers.</span></span> 
    
- <span data-ttu-id="31b0f-107">[IMSLogon::Logoff](imslogon-logoff.md)消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="31b0f-107">[IMSLogon::Logoff](imslogon-logoff.md) for message store providers.</span></span> 
    
- <span data-ttu-id="31b0f-108">[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md)传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="31b0f-108">[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) for transport providers.</span></span> 
    
<span data-ttu-id="31b0f-109">这些方法具有类似的实现。</span><span class="sxs-lookup"><span data-stu-id="31b0f-109">These methods have similar implementations.</span></span> <span data-ttu-id="31b0f-110">Logoff 方法执行的主要任务如下所示：</span><span class="sxs-lookup"><span data-stu-id="31b0f-110">The main tasks that a logoff method performs are as follows:</span></span>
  
- <span data-ttu-id="31b0f-111">释放所有打开的对象，包括子对象和状态对象。</span><span class="sxs-lookup"><span data-stu-id="31b0f-111">Releasing all open objects, including subobjects and status objects.</span></span>
    
- <span data-ttu-id="31b0f-112">调用支持对象的[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法，以减少引用计数。</span><span class="sxs-lookup"><span data-stu-id="31b0f-112">Calling the support object's [IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method to decrement its reference count.</span></span> 
    
- <span data-ttu-id="31b0f-113">删除所有提供商的注册[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="31b0f-113">Removing all of your provider's registered [MAPIUID](mapiuid.md) structures.</span></span> 
    
- <span data-ttu-id="31b0f-114">在状态表中删除提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="31b0f-114">Removing your provider's row in the status table.</span></span>
    
- <span data-ttu-id="31b0f-115">执行与清理资源，如以下任何任务：</span><span class="sxs-lookup"><span data-stu-id="31b0f-115">Performing any tasks that relate to cleaning up resources, such as the following:</span></span>
    
  - <span data-ttu-id="31b0f-116">终止与远程服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="31b0f-116">Terminating a connection with a remote server.</span></span>
    
  - <span data-ttu-id="31b0f-117">递减引用计数登录对象。</span><span class="sxs-lookup"><span data-stu-id="31b0f-117">Decrementing the reference count on the logon object.</span></span>
    
  - <span data-ttu-id="31b0f-118">从您的提供程序存储的登录对象的列表中删除登录对象。</span><span class="sxs-lookup"><span data-stu-id="31b0f-118">Removing the logon object from the list of logon objects that your provider stores.</span></span>
    
  - <span data-ttu-id="31b0f-119">在调试模式下，发出跟踪以查找已泄露内存的对象。</span><span class="sxs-lookup"><span data-stu-id="31b0f-119">In debug mode, issuing traces to locate objects that have leaked memory.</span></span>
    
<span data-ttu-id="31b0f-120">注销方法返回时，MAPI 调用下列：</span><span class="sxs-lookup"><span data-stu-id="31b0f-120">When your logoff method returns, MAPI calls the following:</span></span>
  
- <span data-ttu-id="31b0f-121">登录对象的**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="31b0f-121">Your logon object's **IUnknown::Release** method.</span></span> 
    
- <span data-ttu-id="31b0f-122">提供程序对象的**Shutdown**方法执行任何最终清理任务。</span><span class="sxs-lookup"><span data-stu-id="31b0f-122">Your provider object's **Shutdown** method to perform any final cleanup tasks.</span></span> <span data-ttu-id="31b0f-123">根据您的提供程序的类型，调用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="31b0f-123">Depending on the type of your provider, one of the following methods is called:</span></span> 
    
  - <span data-ttu-id="31b0f-124">[IABProvider::Shutdown](iabprovider-shutdown.md)地址簿提供程序</span><span class="sxs-lookup"><span data-stu-id="31b0f-124">[IABProvider::Shutdown](iabprovider-shutdown.md) for address book providers</span></span> 
    
  - <span data-ttu-id="31b0f-125">[IMSProvider::Shutdown](imsprovider-shutdown.md)消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="31b0f-125">[IMSProvider::Shutdown](imsprovider-shutdown.md) for message store providers</span></span> 
    
  - <span data-ttu-id="31b0f-126">[IXPProvider::Shutdown](ixpprovider-shutdown.md)传输提供程序</span><span class="sxs-lookup"><span data-stu-id="31b0f-126">[IXPProvider::Shutdown](ixpprovider-shutdown.md) for transport providers</span></span> 
    
- <span data-ttu-id="31b0f-127">提供程序对象的**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="31b0f-127">Your provider object's **IUnknown::Release** method.</span></span> 
    
<span data-ttu-id="31b0f-128">如果您的提供商的消息存储，客户端调用[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)还将启动关机过程。</span><span class="sxs-lookup"><span data-stu-id="31b0f-128">If your provider is a message store, a client call to [IMsgStore::StoreLogoff](imsgstore-storelogoff.md) will also initiate the shutdown process.</span></span> <span data-ttu-id="31b0f-129">**StoreLogoff**关闭一个特定消息存储提供程序，并不影响会话。</span><span class="sxs-lookup"><span data-stu-id="31b0f-129">**StoreLogoff** shuts down one particular message store provider and has no effect on the session.</span></span> <span data-ttu-id="31b0f-130">仅消息存储提供程序可以使用此方法; 关闭没有明确的方式可以关闭特定地址簿或传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="31b0f-130">Only a message store provider can be shut down with this method; there is no explicit way to shut down a particular address book or transport provider.</span></span> <span data-ttu-id="31b0f-131">有关如何响应**StoreLogoff**呼叫，请参阅[关机的情况下消息存储提供程序](shutting-down-a-message-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="31b0f-131">For information about how to respond to a **StoreLogoff** call, see [Shutting Down a Message Store Provider](shutting-down-a-message-store-provider.md).</span></span>
  
<span data-ttu-id="31b0f-132">MAPI 呼叫 Win32 API 函数**句**，最后一个活动的客户端具有调用[MAPIUninitialize](mapiuninitialize.md)后进行的呼叫时，将卸载提供程序的 DLL。</span><span class="sxs-lookup"><span data-stu-id="31b0f-132">Your provider's DLL will be unloaded when MAPI calls the Win32 API function **FreeLibrary**, a call that is made after the last active client has called [MAPIUninitialize](mapiuninitialize.md).</span></span> <span data-ttu-id="31b0f-133">此时，由服务提供商将完成关机的情况下。</span><span class="sxs-lookup"><span data-stu-id="31b0f-133">By this time, your service provider will have finished shutting down.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="31b0f-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31b0f-134">See also</span></span>



[<span data-ttu-id="31b0f-135">MAPI 服务提供商</span><span class="sxs-lookup"><span data-stu-id="31b0f-135">MAPI Service Providers</span></span>](mapi-service-providers.md)

