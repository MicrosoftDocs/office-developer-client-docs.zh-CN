---
title: MAPI 服务提供商
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6511e1b5-697e-4ed1-80af-aa8ca56fd045
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1f931382e790da13e7d4a746e286d9dc176b7b6b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571904"
---
# <a name="mapi-service-providers"></a><span data-ttu-id="ab0b4-103">MAPI 服务提供商</span><span class="sxs-lookup"><span data-stu-id="ab0b4-103">MAPI Service Providers</span></span>

  
  
<span data-ttu-id="ab0b4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ab0b4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ab0b4-105">有三种常见类型的服务提供商：</span><span class="sxs-lookup"><span data-stu-id="ab0b4-105">There are three common types of service providers:</span></span>
  
- <span data-ttu-id="ab0b4-106">通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-106">Address book providers.</span></span>
    
- <span data-ttu-id="ab0b4-107">消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-107">Message store providers.</span></span>
    
- <span data-ttu-id="ab0b4-108">传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-108">Transport providers.</span></span>
    
<span data-ttu-id="ab0b4-109">地址簿和消息存储提供程序具有许多相似之处。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-109">Address book and message store providers have many similarities.</span></span> <span data-ttu-id="ab0b4-110">他们与他们用于构建其对象的项标识符的 MAPI 注册的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-110">They register a unique identifier with MAPI that they use for constructing entry identifiers for their objects.</span></span> <span data-ttu-id="ab0b4-111">它们提供对象和属性的客户端可以访问和操作层次的结构。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-111">They provide a hierarchy of objects and properties that clients can access and manipulate.</span></span> <span data-ttu-id="ab0b4-112">对于其容器对象，它们支持的层次结构表和内容表。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-112">For their container objects, they support a hierarchy table and a contents table.</span></span> <span data-ttu-id="ab0b4-113">以便可以在会话过程中发生的更改的通知客户端，它们支持了对这些表和 （可选） 在单个对象的事件通知。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-113">They support event notification on these tables and optionally on individual objects so that clients can be informed of changes that occur during the session.</span></span> <span data-ttu-id="ab0b4-114">操作长时，它们可以显示进度指示器，告知用户操作的状态。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-114">When operations become lengthy, they can display a progress indicator to inform the user of the operation's status.</span></span> <span data-ttu-id="ab0b4-115">客户端可以使用与通信地址簿和消息存储提供程序任一间接到 MAPI [IAddrBook: IMAPIProp](iaddrbookimapiprop.md)和[IMAPISession: IUnknown](imapisessioniunknown.md)接口或直接通过使用中的服务提供程序接口之一下表。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-115">Clients can communicate with address book and message store providers either indirectly through MAPI by using the [IAddrBook : IMAPIProp](iaddrbookimapiprop.md) and [IMAPISession : IUnknown](imapisessioniunknown.md) interfaces or directly by using one of the service provider interfaces in the following table.</span></span> 
  
|<span data-ttu-id="ab0b4-116">**通讯簿提供程序接口**</span><span class="sxs-lookup"><span data-stu-id="ab0b4-116">**Address book provider interfaces**</span></span>|<span data-ttu-id="ab0b4-117">**消息存储提供程序接口**</span><span class="sxs-lookup"><span data-stu-id="ab0b4-117">**Message store provider interfaces**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ab0b4-118">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="ab0b4-118">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md) <br/> |[<span data-ttu-id="ab0b4-119">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ab0b4-119">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md) <br/> |
|[<span data-ttu-id="ab0b4-120">IDistList : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="ab0b4-120">IDistList : IMAPIContainer</span></span>](idistlistimapicontainer.md) <br/> |[<span data-ttu-id="ab0b4-121">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="ab0b4-121">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md) <br/> |
|[<span data-ttu-id="ab0b4-122">IMailUser : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ab0b4-122">IMailUser : IMAPIProp</span></span>](imailuserimapiprop.md) <br/> |[<span data-ttu-id="ab0b4-123">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ab0b4-123">IMessage : IMAPIProp</span></span>](imessageimapiprop.md) <br/> |
| <br/> |[<span data-ttu-id="ab0b4-124">IAttach : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ab0b4-124">IAttach : IMAPIProp</span></span>](iattachimapiprop.md) <br/> |
   
<span data-ttu-id="ab0b4-125">传输提供程序与他们通信与 MAPI 和客户端的方式的地址簿和消息存储提供程序不同。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-125">Transport providers differ from address book and message store providers in the way they communicate with MAPI and with clients.</span></span> <span data-ttu-id="ab0b4-126">传输提供程序通常等待 MAPI 提示他们的信息，而不是交流。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-126">Transport providers typically wait for MAPI to prompt them for information rather than initiate communication.</span></span> <span data-ttu-id="ab0b4-127">与其他提供程序，不同传输提供程序不支持的各种对象和通常由客户端访问的表。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-127">Unlike the other providers, transport providers do not support a variety of objects and tables that are commonly accessed by clients.</span></span> <span data-ttu-id="ab0b4-128">但是，它们支持一个状态对象中，在执行所有服务提供程序，并在状态表中发布其属性。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-128">However, they do support a status object, as do all service providers, and publish its properties in the status table.</span></span> <span data-ttu-id="ab0b4-129">传输提供程序通讯簿和消息存储提供程序调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法以注册用于构建它们的项标识符的唯一标识符，而呼叫[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法假定责任特定邮件的传递注册唯一标识符，以及地址类型。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-129">Whereas address book and message store providers call the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method to register unique identifiers for constructing their entry identifiers, transport providers call the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method to register unique identifiers, as well as address types for assuming responsibility for the delivery of particular messages.</span></span> 
  
<span data-ttu-id="ab0b4-130">服务提供商应具有三个标头文件： 一个公共头文件和两个内部文件。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-130">Your service provider should have three header files: one public header file and two internal files.</span></span> <span data-ttu-id="ab0b4-131">配置和记录属性以及它们的值，请使用公共头文件。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-131">Use the public header file for configuration and for documenting properties and their values.</span></span> <span data-ttu-id="ab0b4-132">内部标头文件中包含的所有必要公共 MAPI 标题;此头文件应包含在所有服务提供程序源文件。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-132">Include in one of the internal header files all the necessary public MAPI headers; this header file should be included in all of your service provider source files.</span></span> <span data-ttu-id="ab0b4-133">使用其他内部文件定义资源标识符。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-133">Use the other internal file to define resource identifiers.</span></span>
  
<span data-ttu-id="ab0b4-134">通讯簿、 消息存储和传输提供程序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="ab0b4-134">Address book, message store, and transport providers perform the following tasks:</span></span>
  
- <span data-ttu-id="ab0b4-135">提供入口点函数。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-135">Supply an entry point function.</span></span> 
    
- <span data-ttu-id="ab0b4-136">提供一个提供程序和登录对象，以处理登录和初始化。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-136">Supply a provider and logon object to handle logon and initialization.</span></span> 
    
- <span data-ttu-id="ab0b4-137">如果提供程序属于邮件服务，提供邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-137">If the provider belongs to a message service, supply a message service entry point function.</span></span> 
    
- <span data-ttu-id="ab0b4-138">通过实现属性表中支持的配置。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-138">Support configuration by implementing a property sheet.</span></span>
    
- <span data-ttu-id="ab0b4-139">实现状态对象和支持状态表。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-139">Implement a status object and support the status table.</span></span> 
    
- <span data-ttu-id="ab0b4-140">关闭的句柄。</span><span class="sxs-lookup"><span data-stu-id="ab0b4-140">Handle shut down.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ab0b4-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab0b4-141">See also</span></span>



[<span data-ttu-id="ab0b4-142">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="ab0b4-142">MAPI Concepts</span></span>](mapi-concepts.md)

