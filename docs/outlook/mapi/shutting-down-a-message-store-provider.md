---
title: 关机的情况下消息存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e38219db-f867-4c1d-9973-0e025779e8b6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b5c9874ca465bb0ebed62f218d1512feb1a2f9ea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778786"
---
# <a name="shutting-down-a-message-store-provider"></a><span data-ttu-id="3d343-103">关机的情况下消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="3d343-103">Shutting Down a Message Store Provider</span></span>

  
  
<span data-ttu-id="3d343-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3d343-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3d343-105">如果您的提供商消息存储提供程序，它可以关闭通过以下方式之一：</span><span class="sxs-lookup"><span data-stu-id="3d343-105">If your provider is a message store provider, it can be shut down in one of the following ways:</span></span>
  
- <span data-ttu-id="3d343-106">当客户端或 MAPI 后台处理程序调用[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)。</span><span class="sxs-lookup"><span data-stu-id="3d343-106">When a client or the MAPI spooler calls [IMsgStore::StoreLogoff](imsgstore-storelogoff.md).</span></span> <span data-ttu-id="3d343-107">关机的情况下**StoreLogoff**的消息存储提供程序使关闭发生有序、 控制更严格的方式。</span><span class="sxs-lookup"><span data-stu-id="3d343-107">Shutting down a message store provider with **StoreLogoff** causes the shutdown to occur in an orderly and controlled manner.</span></span> 
    
- <span data-ttu-id="3d343-108">当客户端调用[IMAPISession::Logoff](imapisession-logoff.md)。</span><span class="sxs-lookup"><span data-stu-id="3d343-108">When a client calls [IMAPISession::Logoff](imapisession-logoff.md).</span></span> 
    
<span data-ttu-id="3d343-109">**IMsgStore::StoreLogoff**的实现应首先调用[IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md) ，告知 MAPI，它将被关闭，指示应记录的任何相关的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="3d343-109">Your implementation of **IMsgStore::StoreLogoff** should begin by calling [IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md) to inform MAPI that it is being shut down, indicating that any related transport providers should be logged off.</span></span> <span data-ttu-id="3d343-110">**IMsgStore::StoreLogoff**返回时，其呼叫者将调用您的消息存储[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="3d343-110">When **IMsgStore::StoreLogoff** returns, its caller invokes your message store's [IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method.</span></span> <span data-ttu-id="3d343-111">通过调用支持对象的**IUnknown::Release**方法实现此**发行版**方法。</span><span class="sxs-lookup"><span data-stu-id="3d343-111">Implement this **Release** method by calling the support object's **IUnknown::Release** method.</span></span> 
  
<span data-ttu-id="3d343-112">MAPI 的消息存储**IUnknown::Release**其实现中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="3d343-112">MAPI performs the following tasks in its implementation of **IUnknown::Release** for message stores:</span></span> 
  
1. <span data-ttu-id="3d343-113">删除所有注册的消息存储提供程序的[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="3d343-113">Removes all of the [MAPIUID](mapiuid.md) structures registered by the message store provider.</span></span> 
    
2. <span data-ttu-id="3d343-114">从状态表中删除的消息存储提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="3d343-114">Removes the message store provider's row from the status table.</span></span>
    
3. <span data-ttu-id="3d343-115">调用[IMSLogon::Logoff](imslogon-logoff.md)释放所有打开的对象、 子对象和状态对象。</span><span class="sxs-lookup"><span data-stu-id="3d343-115">Calls [IMSLogon::Logoff](imslogon-logoff.md) to release all open objects, subobjects, and status objects.</span></span> 
    
4. <span data-ttu-id="3d343-116">调用[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)释放消息存储提供程序的登录对象。</span><span class="sxs-lookup"><span data-stu-id="3d343-116">Calls [IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) to release the message store provider's logon object.</span></span> 
    
<span data-ttu-id="3d343-117">某些客户端可能会省略**IMsgStore::StoreLogoff**，启动关闭消息存储提供程序的消息存储**IUnknown::Release**方法调用的调用。</span><span class="sxs-lookup"><span data-stu-id="3d343-117">Some clients might omit the call to **IMsgStore::StoreLogoff**, initiating the shutdown of your message store provider with the call to the message store's **IUnknown::Release** method.</span></span> <span data-ttu-id="3d343-118">在这些情况下不**StoreLogoff**调用的情况下关闭是较低序和控制。</span><span class="sxs-lookup"><span data-stu-id="3d343-118">A shutdown under these circumstances without the call to **StoreLogoff** is less orderly and controlled.</span></span> <span data-ttu-id="3d343-119">编写消息存储库**版本**方法，以处理这种可能性和跟踪发生**IMAPISupport::StoreLogoffTransports**调用。</span><span class="sxs-lookup"><span data-stu-id="3d343-119">Write your message store's **Release** method to handle this possibility and keep track of whether or not a call to **IMAPISupport::StoreLogoffTransports** has occurred.</span></span> <span data-ttu-id="3d343-120">必须关闭过程中一次调用**StoreLogoffTransports** 。</span><span class="sxs-lookup"><span data-stu-id="3d343-120">**StoreLogoffTransports** must be called once during the shutdown process.</span></span> <span data-ttu-id="3d343-121">如果在您的**发布**方法中检测**StoreLogoffTransports**尚未调用，调用了 LOGOFF_ABORT 标记。</span><span class="sxs-lookup"><span data-stu-id="3d343-121">If you detect in your **Release** method that **StoreLogoffTransports** has not yet been called, invoke it with the LOGOFF_ABORT flag.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3d343-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d343-122">See also</span></span>



[<span data-ttu-id="3d343-123">关闭服务提供商</span><span class="sxs-lookup"><span data-stu-id="3d343-123">Shutting Down a Service Provider</span></span>](shutting-down-a-service-provider.md)

