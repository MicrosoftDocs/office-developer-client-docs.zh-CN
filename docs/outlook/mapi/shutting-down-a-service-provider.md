---
title: 关闭服务提供程序
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
# <a name="shutting-down-a-service-provider"></a><span data-ttu-id="5c34b-103">关闭服务提供程序</span><span class="sxs-lookup"><span data-stu-id="5c34b-103">Shutting Down a Service Provider</span></span>

 
  
<span data-ttu-id="5c34b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5c34b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5c34b-105">当客户端调用[IMAPISession:: 注销](imapisession-logoff.md)方法以结束会话并关闭所有活动服务提供程序时, MAPI 将调用以下方法:</span><span class="sxs-lookup"><span data-stu-id="5c34b-105">When a client calls the [IMAPISession::Logoff](imapisession-logoff.md) method to end the session and shut down all active service providers, MAPI in turn calls the following methods:</span></span> 
  
- <span data-ttu-id="5c34b-106">[IABLogon::](iablogon-logoff.md)通讯簿提供程序的注销。</span><span class="sxs-lookup"><span data-stu-id="5c34b-106">[IABLogon::Logoff](iablogon-logoff.md) for address book providers.</span></span> 
    
- <span data-ttu-id="5c34b-107">[IMSLogon::](imslogon-logoff.md)邮件存储提供程序的注销。</span><span class="sxs-lookup"><span data-stu-id="5c34b-107">[IMSLogon::Logoff](imslogon-logoff.md) for message store providers.</span></span> 
    
- <span data-ttu-id="5c34b-108">[IXPLogon:: TransportLogoff](ixplogon-transportlogoff.md)的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="5c34b-108">[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) for transport providers.</span></span> 
    
<span data-ttu-id="5c34b-109">这些方法具有类似的实现。</span><span class="sxs-lookup"><span data-stu-id="5c34b-109">These methods have similar implementations.</span></span> <span data-ttu-id="5c34b-110">注销方法执行的主要任务如下所示:</span><span class="sxs-lookup"><span data-stu-id="5c34b-110">The main tasks that a logoff method performs are as follows:</span></span>
  
- <span data-ttu-id="5c34b-111">释放所有打开的对象, 包括子对象和状态对象。</span><span class="sxs-lookup"><span data-stu-id="5c34b-111">Releasing all open objects, including subobjects and status objects.</span></span>
    
- <span data-ttu-id="5c34b-112">调用支持对象的[IUnknown:: Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法以递减其引用计数。</span><span class="sxs-lookup"><span data-stu-id="5c34b-112">Calling the support object's [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method to decrement its reference count.</span></span> 
    
- <span data-ttu-id="5c34b-113">删除提供程序的所有已注册[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5c34b-113">Removing all of your provider's registered [MAPIUID](mapiuid.md) structures.</span></span> 
    
- <span data-ttu-id="5c34b-114">在状态表中删除提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="5c34b-114">Removing your provider's row in the status table.</span></span>
    
- <span data-ttu-id="5c34b-115">执行与清理资源相关的任何任务, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="5c34b-115">Performing any tasks that relate to cleaning up resources, such as the following:</span></span>
    
  - <span data-ttu-id="5c34b-116">终止与远程服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="5c34b-116">Terminating a connection with a remote server.</span></span>
    
  - <span data-ttu-id="5c34b-117">递减登录对象上的引用计数。</span><span class="sxs-lookup"><span data-stu-id="5c34b-117">Decrementing the reference count on the logon object.</span></span>
    
  - <span data-ttu-id="5c34b-118">从提供程序存储的登录对象列表中删除 "登录" 对象。</span><span class="sxs-lookup"><span data-stu-id="5c34b-118">Removing the logon object from the list of logon objects that your provider stores.</span></span>
    
  - <span data-ttu-id="5c34b-119">在调试模式下, 发出跟踪以查找具有泄漏内存的对象。</span><span class="sxs-lookup"><span data-stu-id="5c34b-119">In debug mode, issuing traces to locate objects that have leaked memory.</span></span>
    
<span data-ttu-id="5c34b-120">当您的注销方法返回时, MAPI 将调用以下内容:</span><span class="sxs-lookup"><span data-stu-id="5c34b-120">When your logoff method returns, MAPI calls the following:</span></span>
  
- <span data-ttu-id="5c34b-121">您的登录对象的**IUnknown:: Release**方法。</span><span class="sxs-lookup"><span data-stu-id="5c34b-121">Your logon object's **IUnknown::Release** method.</span></span> 
    
- <span data-ttu-id="5c34b-122">提供程序对象的**关闭**方法以执行任何最终清理任务。</span><span class="sxs-lookup"><span data-stu-id="5c34b-122">Your provider object's **Shutdown** method to perform any final cleanup tasks.</span></span> <span data-ttu-id="5c34b-123">根据您的提供程序的类型, 将调用以下方法之一:</span><span class="sxs-lookup"><span data-stu-id="5c34b-123">Depending on the type of your provider, one of the following methods is called:</span></span> 
    
  - <span data-ttu-id="5c34b-124">[IABProvider::](iabprovider-shutdown.md)针对通讯簿提供程序的关闭</span><span class="sxs-lookup"><span data-stu-id="5c34b-124">[IABProvider::Shutdown](iabprovider-shutdown.md) for address book providers</span></span> 
    
  - <span data-ttu-id="5c34b-125">[IMSProvider:: Shutdown](imsprovider-shutdown.md) for 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="5c34b-125">[IMSProvider::Shutdown](imsprovider-shutdown.md) for message store providers</span></span> 
    
  - <span data-ttu-id="5c34b-126">[IXPProvider::](ixpprovider-shutdown.md)针对传输提供程序的关闭</span><span class="sxs-lookup"><span data-stu-id="5c34b-126">[IXPProvider::Shutdown](ixpprovider-shutdown.md) for transport providers</span></span> 
    
- <span data-ttu-id="5c34b-127">提供程序对象的**IUnknown:: Release**方法。</span><span class="sxs-lookup"><span data-stu-id="5c34b-127">Your provider object's **IUnknown::Release** method.</span></span> 
    
<span data-ttu-id="5c34b-128">如果提供程序是邮件存储区, 则客户端对[IMsgStore:: StoreLogoff](imsgstore-storelogoff.md)的调用也将启动关闭过程。</span><span class="sxs-lookup"><span data-stu-id="5c34b-128">If your provider is a message store, a client call to [IMsgStore::StoreLogoff](imsgstore-storelogoff.md) will also initiate the shutdown process.</span></span> <span data-ttu-id="5c34b-129">**StoreLogoff**关闭一个特定的邮件存储提供程序, 并且不会对该会话产生影响。</span><span class="sxs-lookup"><span data-stu-id="5c34b-129">**StoreLogoff** shuts down one particular message store provider and has no effect on the session.</span></span> <span data-ttu-id="5c34b-130">使用此方法时, 仅可关闭邮件存储提供程序。没有显式关闭特定通讯簿或传输提供程序的方法。</span><span class="sxs-lookup"><span data-stu-id="5c34b-130">Only a message store provider can be shut down with this method; there is no explicit way to shut down a particular address book or transport provider.</span></span> <span data-ttu-id="5c34b-131">有关如何响应**StoreLogoff**呼叫的信息, 请参阅[关闭邮件存储提供程序](shutting-down-a-message-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="5c34b-131">For information about how to respond to a **StoreLogoff** call, see [Shutting Down a Message Store Provider](shutting-down-a-message-store-provider.md).</span></span>
  
<span data-ttu-id="5c34b-132">当 MAPI 调用 Win32 API 函数**FreeLibrary**时, 将卸载提供程序的 DLL (在最后一个活动客户端调用[MAPIUninitialize](mapiuninitialize.md)之后进行的调用)。</span><span class="sxs-lookup"><span data-stu-id="5c34b-132">Your provider's DLL will be unloaded when MAPI calls the Win32 API function **FreeLibrary**, a call that is made after the last active client has called [MAPIUninitialize](mapiuninitialize.md).</span></span> <span data-ttu-id="5c34b-133">这次, 服务提供商将完成关闭。</span><span class="sxs-lookup"><span data-stu-id="5c34b-133">By this time, your service provider will have finished shutting down.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5c34b-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c34b-134">See also</span></span>



[<span data-ttu-id="5c34b-135">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="5c34b-135">MAPI Service Providers</span></span>](mapi-service-providers.md)

