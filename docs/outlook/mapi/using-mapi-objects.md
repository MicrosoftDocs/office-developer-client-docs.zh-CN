---
title: 使用 MAPI 对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e342c1bd-8bee-4b02-a93f-e3941f4716c1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2b66b450318c802e773c2f2c47e4a39500c582d6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592766"
---
# <a name="using-mapi-objects"></a><span data-ttu-id="ce80b-103">使用 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="ce80b-103">Using MAPI objects</span></span>

<span data-ttu-id="ce80b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ce80b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ce80b-105">客户端和服务提供商使用 MAPI 对象通过在其接口实现中调用的方法。</span><span class="sxs-lookup"><span data-stu-id="ce80b-105">Clients and service providers use MAPI objects by calling the methods in their interface implementations.</span></span> <span data-ttu-id="ce80b-106">这是唯一的方法，可以使用 MAPI 对象;实现由外部 MAPI 界面对象的方法不公开访问。</span><span class="sxs-lookup"><span data-stu-id="ce80b-106">This is the only way that MAPI objects can be used; methods that are implemented by an object outside of a MAPI interface are not publicly accessible.</span></span> <span data-ttu-id="ce80b-107">通过继承相关的所有对象的接口，因为对象的用户可以调用基接口或继承的接口之一中的方法，就好像它们属于同一接口。</span><span class="sxs-lookup"><span data-stu-id="ce80b-107">Because all of an object's interfaces are related through inheritance, an object's user can call methods in either the base interface or one of the inherited interfaces as if they belong to the same interface.</span></span> 
  
<span data-ttu-id="ce80b-108">时对象的用户想要对方法的调用，该对象通过继承相关的几个接口实现，用户不需要知道所属的方法的接口。</span><span class="sxs-lookup"><span data-stu-id="ce80b-108">When an object's user wants to make a call to a method and that object implements several interfaces related through inheritance, the user need not know to which interface the method belongs.</span></span> <span data-ttu-id="ce80b-109">用户可以调用任何方法对任何具有指向对象的单个接口。</span><span class="sxs-lookup"><span data-stu-id="ce80b-109">The user can call any of the methods on any of the interfaces with a single pointer to the object.</span></span> <span data-ttu-id="ce80b-110">例如下, 图显示了客户端应用程序如何使用 folder 对象。</span><span class="sxs-lookup"><span data-stu-id="ce80b-110">For example, the following illustration shows how a client application uses a folder object.</span></span> <span data-ttu-id="ce80b-111">文件夹对象实现[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)接口，从[IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)间接到继承[IMAPIProp: IUnknown](imapipropiunknown.md)和[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="ce80b-111">Folder objects implement the [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) interface, which inherits from [IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) indirectly through [IMAPIProp : IUnknown](imapipropiunknown.md) and [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md).</span></span> <span data-ttu-id="ce80b-112">客户端可以调用**IMAPIProp**方法，如[IMAPIProp::GetProps](imapiprop-getprops.md)，之一和之一[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)方法，例如[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)，具有相同的对象指针相同的方式。</span><span class="sxs-lookup"><span data-stu-id="ce80b-112">A client can call one of the **IMAPIProp** methods, such as [IMAPIProp::GetProps](imapiprop-getprops.md), and one of the [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) methods, such as [IMAPIFolder::CreateMessage](imapifolder-createmessage.md), in the same way with the same object pointer.</span></span> <span data-ttu-id="ce80b-113">客户端不识别或受影响的这一事实这些呼叫属于不同的接口。</span><span class="sxs-lookup"><span data-stu-id="ce80b-113">A client is not aware of or affected by the fact that these calls belong to different interfaces.</span></span>
  
<span data-ttu-id="ce80b-114">**客户端对文件夹对象的使用**</span><span class="sxs-lookup"><span data-stu-id="ce80b-114">**Client use of a folder object**</span></span>
  
<span data-ttu-id="ce80b-115">![客户端使用的一个 folder 对象](media/amapi_40.gif "客户端使用的一个 folder 对象")</span><span class="sxs-lookup"><span data-stu-id="ce80b-115">![Client use of a folder object](media/amapi_40.gif "Client use of a folder object")</span></span>
  
<span data-ttu-id="ce80b-116">这些呼叫将转换不同根据是否发出呼叫的客户端写入 C 或 c + + 中的代码。</span><span class="sxs-lookup"><span data-stu-id="ce80b-116">These calls translate into code differently depending on whether the client making the calls is written in C or C++.</span></span> <span data-ttu-id="ce80b-117">在进行任何方法调用前，必须检索对该接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="ce80b-117">Before any call to a method can be made, a pointer to the interface implementation must be retrieved.</span></span> <span data-ttu-id="ce80b-118">接口指针可以获得以下方式：</span><span class="sxs-lookup"><span data-stu-id="ce80b-118">Interface pointers can be obtained in the following ways:</span></span>
  
- <span data-ttu-id="ce80b-119">在不同对象上调用方法。</span><span class="sxs-lookup"><span data-stu-id="ce80b-119">Calling a method on a different object.</span></span>
    
- <span data-ttu-id="ce80b-120">调用 API 函数。</span><span class="sxs-lookup"><span data-stu-id="ce80b-120">Calling an API function.</span></span>
    
- <span data-ttu-id="ce80b-121">在目标对象上调用[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="ce80b-121">Calling the [IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) method on the target object.</span></span> 
    
<span data-ttu-id="ce80b-122">MAPI 提供了一些方法和 API 函数将指针返回到接口实现。</span><span class="sxs-lookup"><span data-stu-id="ce80b-122">MAPI provides several methods and API functions that return pointers to interface implementations.</span></span> <span data-ttu-id="ce80b-123">例如，客户端可以调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)方法来检索向 table 对象的指针提供消息存储提供程序通过对信息的访问权[IMAPITable: IUnknown](imapitableiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="ce80b-123">For example, clients can call the [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) method to retrieve a pointer to a table object that provides access to message store provider information through the [IMAPITable : IUnknown](imapitableiunknown.md) interface.</span></span> <span data-ttu-id="ce80b-124">服务提供商可以调用 API 函数[CreateTable](createtable.md)检索指向表数据对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ce80b-124">Service providers can call the API function [CreateTable](createtable.md) to retrieve a pointer to a table data object.</span></span> <span data-ttu-id="ce80b-125">当没有任何函数或方法可用和客户端或服务提供程序已经具有指向对象的指针时，它们可以调用该对象的**QueryInterface**方法，以便检索指向另一个对象的接口实现。</span><span class="sxs-lookup"><span data-stu-id="ce80b-125">When there is no function or method available and clients or service providers already have a pointer to an object, they can call the object's **QueryInterface** method to retrieve a pointer to another of the object's interface implementations.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ce80b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce80b-126">See also</span></span>

- [<span data-ttu-id="ce80b-127">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="ce80b-127">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

