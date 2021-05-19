---
title: MAPI 服务提供程序
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6511e1b5-697e-4ed1-80af-aa8ca56fd045
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bb40891376ac511869ba157b675e53ee236b24ca
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409536"
---
# <a name="mapi-service-providers"></a><span data-ttu-id="fb0a7-103">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="fb0a7-103">MAPI Service Providers</span></span>

  
  
<span data-ttu-id="fb0a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb0a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fb0a7-105">有三种常见类型的服务提供程序：</span><span class="sxs-lookup"><span data-stu-id="fb0a7-105">There are three common types of service providers:</span></span>
  
- <span data-ttu-id="fb0a7-106">通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-106">Address book providers.</span></span>
    
- <span data-ttu-id="fb0a7-107">邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-107">Message store providers.</span></span>
    
- <span data-ttu-id="fb0a7-108">传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-108">Transport providers.</span></span>
    
<span data-ttu-id="fb0a7-109">通讯簿和邮件存储提供程序有很多相似之处。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-109">Address book and message store providers have many similarities.</span></span> <span data-ttu-id="fb0a7-110">它们使用 MAPI 注册一个唯一标识符，用于构造其对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-110">They register a unique identifier with MAPI that they use for constructing entry identifiers for their objects.</span></span> <span data-ttu-id="fb0a7-111">它们提供客户端可以访问和操作的对象和属性的层次结构。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-111">They provide a hierarchy of objects and properties that clients can access and manipulate.</span></span> <span data-ttu-id="fb0a7-112">对于容器对象，它们支持层次结构表和内容表。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-112">For their container objects, they support a hierarchy table and a contents table.</span></span> <span data-ttu-id="fb0a7-113">它们支持在这些表上以及各个对象上（可选）的事件通知，以便客户端可以收到会话期间发生的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-113">They support event notification on these tables and optionally on individual objects so that clients can be informed of changes that occur during the session.</span></span> <span data-ttu-id="fb0a7-114">当操作变得很长时，它们可以显示进度指示器，以通知用户操作的状态。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-114">When operations become lengthy, they can display a progress indicator to inform the user of the operation's status.</span></span> <span data-ttu-id="fb0a7-115">客户端可以使用 [IAddrBook ： IMAPIProp](iaddrbookimapiprop.md) 和 [IMAPISession ： IUnknown](imapisessioniunknown.md) 接口间接通过 MAPI 与通讯簿和邮件存储提供程序进行通信，或者直接使用下表中的一个服务提供程序接口进行通信。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-115">Clients can communicate with address book and message store providers either indirectly through MAPI by using the [IAddrBook : IMAPIProp](iaddrbookimapiprop.md) and [IMAPISession : IUnknown](imapisessioniunknown.md) interfaces or directly by using one of the service provider interfaces in the following table.</span></span> 
  
|<span data-ttu-id="fb0a7-116">**通讯簿提供程序接口**</span><span class="sxs-lookup"><span data-stu-id="fb0a7-116">**Address book provider interfaces**</span></span>|<span data-ttu-id="fb0a7-117">**邮件存储提供程序接口**</span><span class="sxs-lookup"><span data-stu-id="fb0a7-117">**Message store provider interfaces**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fb0a7-118">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="fb0a7-118">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md) <br/> |[<span data-ttu-id="fb0a7-119">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fb0a7-119">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md) <br/> |
|[<span data-ttu-id="fb0a7-120">IDistList : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="fb0a7-120">IDistList : IMAPIContainer</span></span>](idistlistimapicontainer.md) <br/> |[<span data-ttu-id="fb0a7-121">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="fb0a7-121">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md) <br/> |
|[<span data-ttu-id="fb0a7-122">IMailUser : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fb0a7-122">IMailUser : IMAPIProp</span></span>](imailuserimapiprop.md) <br/> |[<span data-ttu-id="fb0a7-123">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fb0a7-123">IMessage : IMAPIProp</span></span>](imessageimapiprop.md) <br/> |
| <br/> |[<span data-ttu-id="fb0a7-124">IAttach : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fb0a7-124">IAttach : IMAPIProp</span></span>](iattachimapiprop.md) <br/> |
   
<span data-ttu-id="fb0a7-125">传输提供程序与通讯簿和邮件存储提供程序在与 MAPI 和客户端通信的方式上有所不同。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-125">Transport providers differ from address book and message store providers in the way they communicate with MAPI and with clients.</span></span> <span data-ttu-id="fb0a7-126">传输提供程序通常等待 MAPI 提示他们输入信息，而不是启动通信。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-126">Transport providers typically wait for MAPI to prompt them for information rather than initiate communication.</span></span> <span data-ttu-id="fb0a7-127">与其他提供程序不同，传输提供程序不支持客户端通常访问的各种对象和表。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-127">Unlike the other providers, transport providers do not support a variety of objects and tables that are commonly accessed by clients.</span></span> <span data-ttu-id="fb0a7-128">但是，它们支持状态对象，就像所有服务提供程序一样，并且会将其属性发布到状态表中。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-128">However, they do support a status object, as do all service providers, and publish its properties in the status table.</span></span> <span data-ttu-id="fb0a7-129">通讯簿和邮件存储提供程序调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md) 方法来注册用于构造其条目标识符的唯一标识符，而传输提供程序调用 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) 方法来注册唯一标识符，以及负责传递特定邮件的地址类型。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-129">Whereas address book and message store providers call the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method to register unique identifiers for constructing their entry identifiers, transport providers call the [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method to register unique identifiers, as well as address types for assuming responsibility for the delivery of particular messages.</span></span> 
  
<span data-ttu-id="fb0a7-130">您的服务提供商应具有三个头文件：一个公共头文件和两个内部文件。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-130">Your service provider should have three header files: one public header file and two internal files.</span></span> <span data-ttu-id="fb0a7-131">使用公共头文件进行配置，并记录属性及其值。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-131">Use the public header file for configuration and for documenting properties and their values.</span></span> <span data-ttu-id="fb0a7-132">包括其中一个内部头文件中所有必要的公共 MAPI 标头;此头文件应包含在所有服务提供程序源文件中。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-132">Include in one of the internal header files all the necessary public MAPI headers; this header file should be included in all of your service provider source files.</span></span> <span data-ttu-id="fb0a7-133">使用另一个内部文件定义资源标识符。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-133">Use the other internal file to define resource identifiers.</span></span>
  
<span data-ttu-id="fb0a7-134">通讯簿、邮件存储和传输提供程序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="fb0a7-134">Address book, message store, and transport providers perform the following tasks:</span></span>
  
- <span data-ttu-id="fb0a7-135">提供入口点函数。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-135">Supply an entry point function.</span></span> 
    
- <span data-ttu-id="fb0a7-136">提供提供程序和登录对象以处理登录和初始化。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-136">Supply a provider and logon object to handle logon and initialization.</span></span> 
    
- <span data-ttu-id="fb0a7-137">如果提供程序属于邮件服务，则提供邮件服务入口点功能。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-137">If the provider belongs to a message service, supply a message service entry point function.</span></span> 
    
- <span data-ttu-id="fb0a7-138">通过实现一个解决方案来支持属性表。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-138">Support configuration by implementing a property sheet.</span></span>
    
- <span data-ttu-id="fb0a7-139">实现状态对象并支持状态表。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-139">Implement a status object and support the status table.</span></span> 
    
- <span data-ttu-id="fb0a7-140">处理关闭。</span><span class="sxs-lookup"><span data-stu-id="fb0a7-140">Handle shut down.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fb0a7-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb0a7-141">See also</span></span>



[<span data-ttu-id="fb0a7-142">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="fb0a7-142">MAPI Concepts</span></span>](mapi-concepts.md)

