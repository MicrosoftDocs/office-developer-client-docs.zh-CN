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
# <a name="shutting-down-a-message-store-provider"></a><span data-ttu-id="a9d59-103">关闭邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="a9d59-103">Shutting Down a Message Store Provider</span></span>

  
  
<span data-ttu-id="a9d59-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a9d59-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a9d59-105">如果您的提供程序是邮件存储提供程序，则可以通过以下方法之一将其关闭：</span><span class="sxs-lookup"><span data-stu-id="a9d59-105">If your provider is a message store provider, it can be shut down in one of the following ways:</span></span>
  
- <span data-ttu-id="a9d59-106">当客户端或 MAPI 后台处理程序调用 [IMsgStore：：StoreLogoff 时](imsgstore-storelogoff.md)。</span><span class="sxs-lookup"><span data-stu-id="a9d59-106">When a client or the MAPI spooler calls [IMsgStore::StoreLogoff](imsgstore-storelogoff.md).</span></span> <span data-ttu-id="a9d59-107">使用 **StoreLogoff** 关闭邮件存储提供程序会导致以有序且受控的方式关闭。</span><span class="sxs-lookup"><span data-stu-id="a9d59-107">Shutting down a message store provider with **StoreLogoff** causes the shutdown to occur in an orderly and controlled manner.</span></span> 
    
- <span data-ttu-id="a9d59-108">当客户端调用 [IMAPISession：：Logoff 时](imapisession-logoff.md)。</span><span class="sxs-lookup"><span data-stu-id="a9d59-108">When a client calls [IMAPISession::Logoff](imapisession-logoff.md).</span></span> 
    
<span data-ttu-id="a9d59-109">**IMsgStore：：StoreLogoff** 的实现应首先调用 [IMAPISupport：：StoreLogoffTransports](imapisupport-storelogofftransports.md)以通知 MAPI 它正在关闭，指示应注销任何相关传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="a9d59-109">Your implementation of **IMsgStore::StoreLogoff** should begin by calling [IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md) to inform MAPI that it is being shut down, indicating that any related transport providers should be logged off.</span></span> <span data-ttu-id="a9d59-110">当 **IMsgStore：：StoreLogoff** 返回时，其调用方将调用邮件存储的 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="a9d59-110">When **IMsgStore::StoreLogoff** returns, its caller invokes your message store's [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method.</span></span> <span data-ttu-id="a9d59-111">通过调用 **支持** 对象的 **IUnknown：：Release** 方法实现此 Release 方法。</span><span class="sxs-lookup"><span data-stu-id="a9d59-111">Implement this **Release** method by calling the support object's **IUnknown::Release** method.</span></span> 
  
<span data-ttu-id="a9d59-112">MAPI 在邮件存储的 **IUnknown：：Release** 实现中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a9d59-112">MAPI performs the following tasks in its implementation of **IUnknown::Release** for message stores:</span></span> 
  
1. <span data-ttu-id="a9d59-113">删除邮件存储提供程序注册的所有 [MAPIUID](mapiuid.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="a9d59-113">Removes all of the [MAPIUID](mapiuid.md) structures registered by the message store provider.</span></span> 
    
2. <span data-ttu-id="a9d59-114">从状态表中删除邮件存储提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="a9d59-114">Removes the message store provider's row from the status table.</span></span>
    
3. <span data-ttu-id="a9d59-115">调用 [IMSLogon：：Logoff](imslogon-logoff.md) 以释放所有打开的对象、子对象和状态对象。</span><span class="sxs-lookup"><span data-stu-id="a9d59-115">Calls [IMSLogon::Logoff](imslogon-logoff.md) to release all open objects, subobjects, and status objects.</span></span> 
    
4. <span data-ttu-id="a9d59-116">调用 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 以释放邮件存储提供程序的登录对象。</span><span class="sxs-lookup"><span data-stu-id="a9d59-116">Calls [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) to release the message store provider's logon object.</span></span> 
    
<span data-ttu-id="a9d59-117">某些客户端可能会省略 **对 IMsgStore：：StoreLogoff** 的调用，通过调用邮件存储的 **IUnknown：：Release** 方法来启动邮件存储提供程序的关闭。</span><span class="sxs-lookup"><span data-stu-id="a9d59-117">Some clients might omit the call to **IMsgStore::StoreLogoff**, initiating the shutdown of your message store provider with the call to the message store's **IUnknown::Release** method.</span></span> <span data-ttu-id="a9d59-118">在这些情况下，如果不调用 **StoreLogoff，** 则关闭将不太有序和受控。</span><span class="sxs-lookup"><span data-stu-id="a9d59-118">A shutdown under these circumstances without the call to **StoreLogoff** is less orderly and controlled.</span></span> <span data-ttu-id="a9d59-119">编写邮件存储的 **Release** 方法以处理此可能性并跟踪是否已调用 **IMAPISupport：：StoreLogoffTransports。**</span><span class="sxs-lookup"><span data-stu-id="a9d59-119">Write your message store's **Release** method to handle this possibility and keep track of whether or not a call to **IMAPISupport::StoreLogoffTransports** has occurred.</span></span> <span data-ttu-id="a9d59-120">**必须在关闭过程中调用 StoreLogoffTransports** 一次。</span><span class="sxs-lookup"><span data-stu-id="a9d59-120">**StoreLogoffTransports** must be called once during the shutdown process.</span></span> <span data-ttu-id="a9d59-121">如果在 Release 方法中检测到尚未调用 **StoreLogoffTransports，** 则使用 LOGOFF_ABORT 调用它。</span><span class="sxs-lookup"><span data-stu-id="a9d59-121">If you detect in your **Release** method that **StoreLogoffTransports** has not yet been called, invoke it with the LOGOFF_ABORT flag.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a9d59-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9d59-122">See also</span></span>



[<span data-ttu-id="a9d59-123">关闭服务提供商</span><span class="sxs-lookup"><span data-stu-id="a9d59-123">Shutting Down a Service Provider</span></span>](shutting-down-a-service-provider.md)

