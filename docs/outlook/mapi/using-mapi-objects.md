---
title: 使用 MAPI 对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e342c1bd-8bee-4b02-a93f-e3941f4716c1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d732efe5276f4756f43b4aca46e1c33d6f103844
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329673"
---
# <a name="using-mapi-objects"></a><span data-ttu-id="147c2-103">使用 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="147c2-103">Using MAPI objects</span></span>

<span data-ttu-id="147c2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="147c2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="147c2-105">客户端和服务提供程序通过调用其接口实现中的方法来使用 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="147c2-105">Clients and service providers use MAPI objects by calling the methods in their interface implementations.</span></span> <span data-ttu-id="147c2-106">这是 MAPI 对象可以使用的唯一方法;由 MAPI 接口外部的对象实现的方法不可公开访问。</span><span class="sxs-lookup"><span data-stu-id="147c2-106">This is the only way that MAPI objects can be used; methods that are implemented by an object outside of a MAPI interface are not publicly accessible.</span></span> <span data-ttu-id="147c2-107">由于对象的所有接口都是通过继承相关的, 因此对象的用户可以在基接口或继承的接口之一中调用方法, 就好像它们属于同一接口一样。</span><span class="sxs-lookup"><span data-stu-id="147c2-107">Because all of an object's interfaces are related through inheritance, an object's user can call methods in either the base interface or one of the inherited interfaces as if they belong to the same interface.</span></span> 
  
<span data-ttu-id="147c2-108">当对象的用户想要调用某个方法, 并且该对象实现了多个与继承相关的接口时, 用户不需要知道该方法属于哪个接口。</span><span class="sxs-lookup"><span data-stu-id="147c2-108">When an object's user wants to make a call to a method and that object implements several interfaces related through inheritance, the user need not know to which interface the method belongs.</span></span> <span data-ttu-id="147c2-109">用户可以通过指向对象的单个指针调用任何接口上的任何方法。</span><span class="sxs-lookup"><span data-stu-id="147c2-109">The user can call any of the methods on any of the interfaces with a single pointer to the object.</span></span> <span data-ttu-id="147c2-110">例如, 下图显示了客户端应用程序如何使用 folder 对象。</span><span class="sxs-lookup"><span data-stu-id="147c2-110">For example, the following illustration shows how a client application uses a folder object.</span></span> <span data-ttu-id="147c2-111">Folder 对象实现[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)接口, 该接口直接从[iunknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)继承通过[IMAPIProp: iunknown](imapipropiunknown.md)和[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="147c2-111">Folder objects implement the [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) interface, which inherits from [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) indirectly through [IMAPIProp : IUnknown](imapipropiunknown.md) and [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md).</span></span> <span data-ttu-id="147c2-112">客户端可以调用**IMAPIProp**方法之一 (如[IMAPIProp:: GetProps](imapiprop-getprops.md)) 和[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)方法之一, 如[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md), 以相同的方式使用相同的对象指针。</span><span class="sxs-lookup"><span data-stu-id="147c2-112">A client can call one of the **IMAPIProp** methods, such as [IMAPIProp::GetProps](imapiprop-getprops.md), and one of the [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) methods, such as [IMAPIFolder::CreateMessage](imapifolder-createmessage.md), in the same way with the same object pointer.</span></span> <span data-ttu-id="147c2-113">由于这些呼叫属于不同的接口, 客户端不知道也不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="147c2-113">A client is not aware of or affected by the fact that these calls belong to different interfaces.</span></span>
  
<span data-ttu-id="147c2-114">**客户端对文件夹对象的使用**</span><span class="sxs-lookup"><span data-stu-id="147c2-114">**Client use of a folder object**</span></span>
  
<span data-ttu-id="147c2-115">![文件夹对象的客户端使用](media/amapi_40.gif "文件夹对象的客户端使用")</span><span class="sxs-lookup"><span data-stu-id="147c2-115">![Client use of a folder object](media/amapi_40.gif "Client use of a folder object")</span></span>
  
<span data-ttu-id="147c2-116">这些调用将根据以 c 或 c + + 编写调用的客户端是否以不同的方式转换为代码。</span><span class="sxs-lookup"><span data-stu-id="147c2-116">These calls translate into code differently depending on whether the client making the calls is written in C or C++.</span></span> <span data-ttu-id="147c2-117">在对方法进行任何调用之前, 必须先检索指向接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="147c2-117">Before any call to a method can be made, a pointer to the interface implementation must be retrieved.</span></span> <span data-ttu-id="147c2-118">可以通过以下方式获取接口指针:</span><span class="sxs-lookup"><span data-stu-id="147c2-118">Interface pointers can be obtained in the following ways:</span></span>
  
- <span data-ttu-id="147c2-119">调用不同对象上的方法。</span><span class="sxs-lookup"><span data-stu-id="147c2-119">Calling a method on a different object.</span></span>
    
- <span data-ttu-id="147c2-120">调用 API 函数。</span><span class="sxs-lookup"><span data-stu-id="147c2-120">Calling an API function.</span></span>
    
- <span data-ttu-id="147c2-121">对目标对象调用[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="147c2-121">Calling the [IUnknown::QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) method on the target object.</span></span> 
    
<span data-ttu-id="147c2-122">MAPI 提供了几种方法和 API 函数, 可返回指向接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="147c2-122">MAPI provides several methods and API functions that return pointers to interface implementations.</span></span> <span data-ttu-id="147c2-123">例如, 客户端可以调用[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)方法来检索指向 table 对象的指针, 该对象通过[IMAPITable: IUnknown](imapitableiunknown.md)接口提供对邮件存储提供程序信息的访问。</span><span class="sxs-lookup"><span data-stu-id="147c2-123">For example, clients can call the [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) method to retrieve a pointer to a table object that provides access to message store provider information through the [IMAPITable : IUnknown](imapitableiunknown.md) interface.</span></span> <span data-ttu-id="147c2-124">服务提供程序可以调用 API 函数[CreateTable](createtable.md)以检索指向表数据对象的指针。</span><span class="sxs-lookup"><span data-stu-id="147c2-124">Service providers can call the API function [CreateTable](createtable.md) to retrieve a pointer to a table data object.</span></span> <span data-ttu-id="147c2-125">如果没有可用的函数或方法, 并且客户端或服务提供程序已具有指向对象的指针, 则可以调用对象的**QueryInterface**方法来检索指向对象的另一个接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="147c2-125">When there is no function or method available and clients or service providers already have a pointer to an object, they can call the object's **QueryInterface** method to retrieve a pointer to another of the object's interface implementations.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="147c2-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="147c2-126">See also</span></span>

- [<span data-ttu-id="147c2-127">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="147c2-127">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

