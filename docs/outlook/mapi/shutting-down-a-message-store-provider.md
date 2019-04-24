---
title: 关闭邮件存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e38219db-f867-4c1d-9973-0e025779e8b6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8e4712572eaff465bb23b55eccc3670f637c0f9c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339198"
---
# <a name="shutting-down-a-message-store-provider"></a><span data-ttu-id="ab0ae-103">关闭邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="ab0ae-103">Shutting Down a Message Store Provider</span></span>

  
  
<span data-ttu-id="ab0ae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ab0ae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ab0ae-105">如果提供程序是邮件存储提供程序, 则可以通过下列方式之一将其关闭:</span><span class="sxs-lookup"><span data-stu-id="ab0ae-105">If your provider is a message store provider, it can be shut down in one of the following ways:</span></span>
  
- <span data-ttu-id="ab0ae-106">当客户端或 MAPI 后台处理程序调用[IMsgStore:: StoreLogoff](imsgstore-storelogoff.md)时。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-106">When a client or the MAPI spooler calls [IMsgStore::StoreLogoff](imsgstore-storelogoff.md).</span></span> <span data-ttu-id="ab0ae-107">使用**StoreLogoff**关闭邮件存储提供程序会导致以有序且可控的方式进行关闭。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-107">Shutting down a message store provider with **StoreLogoff** causes the shutdown to occur in an orderly and controlled manner.</span></span> 
    
- <span data-ttu-id="ab0ae-108">当客户端调用[IMAPISession:: 注销](imapisession-logoff.md)时。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-108">When a client calls [IMAPISession::Logoff](imapisession-logoff.md).</span></span> 
    
<span data-ttu-id="ab0ae-109">您的**IMsgStore:: StoreLogoff**的实现应首先调用[IMAPISupport:: StoreLogoffTransports](imapisupport-storelogofftransports.md) , 以通知 MAPI 它正在关闭, 表明应注销任何相关的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-109">Your implementation of **IMsgStore::StoreLogoff** should begin by calling [IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md) to inform MAPI that it is being shut down, indicating that any related transport providers should be logged off.</span></span> <span data-ttu-id="ab0ae-110">当**IMsgStore:: StoreLogoff**返回时, 其调用方将调用您的邮件存储区的[IUnknown:: Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-110">When **IMsgStore::StoreLogoff** returns, its caller invokes your message store's [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method.</span></span> <span data-ttu-id="ab0ae-111">通过调用支持对象的**IUnknown:: Release**方法实现此**Release**方法。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-111">Implement this **Release** method by calling the support object's **IUnknown::Release** method.</span></span> 
  
<span data-ttu-id="ab0ae-112">MAPI 在其 IUnknown 实施中执行以下任务 **:: Release** for message 书店:</span><span class="sxs-lookup"><span data-stu-id="ab0ae-112">MAPI performs the following tasks in its implementation of **IUnknown::Release** for message stores:</span></span> 
  
1. <span data-ttu-id="ab0ae-113">删除由邮件存储区提供程序注册的所有[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-113">Removes all of the [MAPIUID](mapiuid.md) structures registered by the message store provider.</span></span> 
    
2. <span data-ttu-id="ab0ae-114">从状态表中删除邮件存储提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-114">Removes the message store provider's row from the status table.</span></span>
    
3. <span data-ttu-id="ab0ae-115">调用[IMSLogon:: 注销](imslogon-logoff.md)以释放所有打开的对象、子对象和状态对象。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-115">Calls [IMSLogon::Logoff](imslogon-logoff.md) to release all open objects, subobjects, and status objects.</span></span> 
    
4. <span data-ttu-id="ab0ae-116">调用[IUnknown:: release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)以释放邮件存储区提供程序的登录对象。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-116">Calls [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) to release the message store provider's logon object.</span></span> 
    
<span data-ttu-id="ab0ae-117">某些客户端可能会省略对**IMsgStore:: StoreLogoff**的调用, 从而启动对邮件存储提供程序的调用, 并对邮件存储区的**IUnknown:: Release**方法进行关闭。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-117">Some clients might omit the call to **IMsgStore::StoreLogoff**, initiating the shutdown of your message store provider with the call to the message store's **IUnknown::Release** method.</span></span> <span data-ttu-id="ab0ae-118">在这些情况下, 在不调用**StoreLogoff**的情况下会发生关机, 且控制程度较低。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-118">A shutdown under these circumstances without the call to **StoreLogoff** is less orderly and controlled.</span></span> <span data-ttu-id="ab0ae-119">编写消息存储库的**Release**方法以处理这种可能性, 并跟踪是否发生了对**IMAPISupport:: StoreLogoffTransports**的调用。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-119">Write your message store's **Release** method to handle this possibility and keep track of whether or not a call to **IMAPISupport::StoreLogoffTransports** has occurred.</span></span> <span data-ttu-id="ab0ae-120">在关闭过程中, 必须调用一次**StoreLogoffTransports** 。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-120">**StoreLogoffTransports** must be called once during the shutdown process.</span></span> <span data-ttu-id="ab0ae-121">如果在您的**Release**方法中检测到尚未调用**StoreLogoffTransports** , 请使用 LOGOFF_ABORT 标志对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="ab0ae-121">If you detect in your **Release** method that **StoreLogoffTransports** has not yet been called, invoke it with the LOGOFF_ABORT flag.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ab0ae-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab0ae-122">See also</span></span>



[<span data-ttu-id="ab0ae-123">关闭服务提供程序</span><span class="sxs-lookup"><span data-stu-id="ab0ae-123">Shutting Down a Service Provider</span></span>](shutting-down-a-service-provider.md)

