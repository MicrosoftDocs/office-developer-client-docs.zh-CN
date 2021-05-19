---
title: 关闭服务提供商
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e518830b-0aaa-4ce4-a85a-07e4f00750a9
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 4e25dad1e04927e10af38cdfbf8f30c9bd04234b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339205"
---
# <a name="shutting-down-a-service-provider"></a><span data-ttu-id="b7b09-103">关闭服务提供商</span><span class="sxs-lookup"><span data-stu-id="b7b09-103">Shutting Down a Service Provider</span></span>

 
  
<span data-ttu-id="b7b09-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b7b09-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b7b09-105">当客户端调用 [IMAPISession：：Logoff](imapisession-logoff.md) 方法结束会话并关闭所有活动服务提供商时，MAPI 反过来会调用以下方法：</span><span class="sxs-lookup"><span data-stu-id="b7b09-105">When a client calls the [IMAPISession::Logoff](imapisession-logoff.md) method to end the session and shut down all active service providers, MAPI in turn calls the following methods:</span></span> 
  
- <span data-ttu-id="b7b09-106">[通讯簿提供程序的 IABLogon：：Logoff。](iablogon-logoff.md)</span><span class="sxs-lookup"><span data-stu-id="b7b09-106">[IABLogon::Logoff](iablogon-logoff.md) for address book providers.</span></span> 
    
- <span data-ttu-id="b7b09-107">[消息存储提供程序的 IMSLogon：：Logoff。](imslogon-logoff.md)</span><span class="sxs-lookup"><span data-stu-id="b7b09-107">[IMSLogon::Logoff](imslogon-logoff.md) for message store providers.</span></span> 
    
- <span data-ttu-id="b7b09-108">[传输提供程序的 IXPLogon：：TransportLogoff。](ixplogon-transportlogoff.md)</span><span class="sxs-lookup"><span data-stu-id="b7b09-108">[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) for transport providers.</span></span> 
    
<span data-ttu-id="b7b09-109">这些方法具有类似的实现。</span><span class="sxs-lookup"><span data-stu-id="b7b09-109">These methods have similar implementations.</span></span> <span data-ttu-id="b7b09-110">注销方法执行的主要任务如下：</span><span class="sxs-lookup"><span data-stu-id="b7b09-110">The main tasks that a logoff method performs are as follows:</span></span>
  
- <span data-ttu-id="b7b09-111">释放所有打开的对象，包括子对象和状态对象。</span><span class="sxs-lookup"><span data-stu-id="b7b09-111">Releasing all open objects, including subobjects and status objects.</span></span>
    
- <span data-ttu-id="b7b09-112">调用支持对象的 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法来缩小其引用计数。</span><span class="sxs-lookup"><span data-stu-id="b7b09-112">Calling the support object's [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method to decrement its reference count.</span></span> 
    
- <span data-ttu-id="b7b09-113">删除所有提供商注册的 [MAPIUID](mapiuid.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="b7b09-113">Removing all of your provider's registered [MAPIUID](mapiuid.md) structures.</span></span> 
    
- <span data-ttu-id="b7b09-114">删除状态表中的提供程序行。</span><span class="sxs-lookup"><span data-stu-id="b7b09-114">Removing your provider's row in the status table.</span></span>
    
- <span data-ttu-id="b7b09-115">执行与清理资源相关的任何任务，例如：</span><span class="sxs-lookup"><span data-stu-id="b7b09-115">Performing any tasks that relate to cleaning up resources, such as the following:</span></span>
    
  - <span data-ttu-id="b7b09-116">终止与远程服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="b7b09-116">Terminating a connection with a remote server.</span></span>
    
  - <span data-ttu-id="b7b09-117">缩小登录对象的引用计数。</span><span class="sxs-lookup"><span data-stu-id="b7b09-117">Decrementing the reference count on the logon object.</span></span>
    
  - <span data-ttu-id="b7b09-118">从提供程序存储的登录对象列表中删除登录对象。</span><span class="sxs-lookup"><span data-stu-id="b7b09-118">Removing the logon object from the list of logon objects that your provider stores.</span></span>
    
  - <span data-ttu-id="b7b09-119">在调试模式下，发出跟踪以查找已泄漏内存的对象。</span><span class="sxs-lookup"><span data-stu-id="b7b09-119">In debug mode, issuing traces to locate objects that have leaked memory.</span></span>
    
<span data-ttu-id="b7b09-120">当 logoff 方法返回时，MAPI 将调用以下内容：</span><span class="sxs-lookup"><span data-stu-id="b7b09-120">When your logoff method returns, MAPI calls the following:</span></span>
  
- <span data-ttu-id="b7b09-121">您的登录对象的 **IUnknown：：Release** 方法。</span><span class="sxs-lookup"><span data-stu-id="b7b09-121">Your logon object's **IUnknown::Release** method.</span></span> 
    
- <span data-ttu-id="b7b09-122">提供程序对象的 **Shutdown** 方法，用于执行任何最终清理任务。</span><span class="sxs-lookup"><span data-stu-id="b7b09-122">Your provider object's **Shutdown** method to perform any final cleanup tasks.</span></span> <span data-ttu-id="b7b09-123">根据提供程序的类型，调用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="b7b09-123">Depending on the type of your provider, one of the following methods is called:</span></span> 
    
  - <span data-ttu-id="b7b09-124">[用于通讯簿提供程序的 IABProvider：：Shutdown](iabprovider-shutdown.md)</span><span class="sxs-lookup"><span data-stu-id="b7b09-124">[IABProvider::Shutdown](iabprovider-shutdown.md) for address book providers</span></span> 
    
  - <span data-ttu-id="b7b09-125">[IMSProvider：：关闭](imsprovider-shutdown.md) 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="b7b09-125">[IMSProvider::Shutdown](imsprovider-shutdown.md) for message store providers</span></span> 
    
  - <span data-ttu-id="b7b09-126">[适用于传输提供程序的 IXPProvider：：Shutdown](ixpprovider-shutdown.md)</span><span class="sxs-lookup"><span data-stu-id="b7b09-126">[IXPProvider::Shutdown](ixpprovider-shutdown.md) for transport providers</span></span> 
    
- <span data-ttu-id="b7b09-127">提供程序对象的 **IUnknown：：Release** 方法。</span><span class="sxs-lookup"><span data-stu-id="b7b09-127">Your provider object's **IUnknown::Release** method.</span></span> 
    
<span data-ttu-id="b7b09-128">如果您的提供程序是邮件存储，则客户端对 [IMsgStore：：StoreLogoff](imsgstore-storelogoff.md) 的调用也将启动关闭过程。</span><span class="sxs-lookup"><span data-stu-id="b7b09-128">If your provider is a message store, a client call to [IMsgStore::StoreLogoff](imsgstore-storelogoff.md) will also initiate the shutdown process.</span></span> <span data-ttu-id="b7b09-129">**StoreLogoff** 关闭一个特定的邮件存储提供程序，并且对会话没有影响。</span><span class="sxs-lookup"><span data-stu-id="b7b09-129">**StoreLogoff** shuts down one particular message store provider and has no effect on the session.</span></span> <span data-ttu-id="b7b09-130">使用此方法只能关闭邮件存储提供程序;没有明确的方法可以关闭特定的通讯簿或传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="b7b09-130">Only a message store provider can be shut down with this method; there is no explicit way to shut down a particular address book or transport provider.</span></span> <span data-ttu-id="b7b09-131">若要了解如何响应 **StoreLogoff** 调用，请参阅 [关闭邮件存储提供程序](shutting-down-a-message-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b09-131">For information about how to respond to a **StoreLogoff** call, see [Shutting Down a Message Store Provider](shutting-down-a-message-store-provider.md).</span></span>
  
<span data-ttu-id="b7b09-132">当 MAPI 调用 Win32 API 函数 **FreeLibrary** 时，将卸载提供程序的 DLL，这是在上一个活动客户端调用 [MAPIUninitialize](mapiuninitialize.md)之后进行调用。</span><span class="sxs-lookup"><span data-stu-id="b7b09-132">Your provider's DLL will be unloaded when MAPI calls the Win32 API function **FreeLibrary**, a call that is made after the last active client has called [MAPIUninitialize](mapiuninitialize.md).</span></span> <span data-ttu-id="b7b09-133">此时，您的服务提供商将已完成关闭。</span><span class="sxs-lookup"><span data-stu-id="b7b09-133">By this time, your service provider will have finished shutting down.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b7b09-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7b09-134">See also</span></span>



[<span data-ttu-id="b7b09-135">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="b7b09-135">MAPI Service Providers</span></span>](mapi-service-providers.md)

