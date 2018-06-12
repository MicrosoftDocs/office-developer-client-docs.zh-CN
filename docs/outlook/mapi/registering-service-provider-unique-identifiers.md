---
title: 注册服务提供程序的唯一标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 964fceb4-8a1c-46c1-98e1-a325c9259f8b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 80d2e4fd353f0746349563fd911e0af09a658b35
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778606"
---
# <a name="registering-service-provider-unique-identifiers"></a><span data-ttu-id="bbbaa-103">注册服务提供程序的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="bbbaa-103">Registering Service Provider Unique Identifiers</span></span>

  
  
<span data-ttu-id="bbbaa-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bbbaa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bbbaa-105">通讯簿、 消息存储和传输提供程序使用的唯一标识符称为[MAPIUID](mapiuid.md)注册到服务的各种类型的对象。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-105">Address book, message store, and transport providers use a unique identifier known as a [MAPIUID](mapiuid.md) to register to service objects of various types.</span></span> <span data-ttu-id="bbbaa-106">**MAPIUID**是包含 GUID 的 16 字节标识符。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-106">A **MAPIUID** is a 16-byte identifier that contains a GUID.</span></span> <span data-ttu-id="bbbaa-107">您可以使用以下过程创建**MAPIUID** :</span><span class="sxs-lookup"><span data-stu-id="bbbaa-107">You can create a **MAPIUID** by using the following procedure:</span></span> 
  
1. <span data-ttu-id="bbbaa-108">定义常数。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-108">Define a constant.</span></span>
    
2. <span data-ttu-id="bbbaa-109">调用 Visual Studio*创建 GUID*\* 工具。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-109">Invoke the Visual Studio*Create GUID*\* tool.</span></span> 
    
<span data-ttu-id="bbbaa-110">例如，通讯簿提供程序可能在定义**MAPIUID**头文件中包含下列常量：</span><span class="sxs-lookup"><span data-stu-id="bbbaa-110">For example, an address book provider might include the following constant in a header file to define a **MAPIUID**:</span></span>
  
 `#define AB_UID_PROVIDER { 0Xe3, 0x3c, 0x67, 0xa0, \ 0xc8, 0x1f, 0x11, 0xce, \ 0xb2, 0xe4, 0x0, 0xaa, \ 0x0, 0x51, 0xe, 0x3b }`
  
 <span data-ttu-id="bbbaa-111">**如果您的提供商的地址簿或消息存储提供程序，注册 MAPIUID**</span><span class="sxs-lookup"><span data-stu-id="bbbaa-111">**To register a MAPIUID if your provider is an address book or message store provider**</span></span>
  
1. <span data-ttu-id="bbbaa-112">调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-112">Call [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md).</span></span>
    
2. <span data-ttu-id="bbbaa-113">注册的每次登录**MAPIUID**对象的实例化和创建每个条目标识符的**ab**成员的第一个 16 字节中包括此**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-113">Register a **MAPIUID** for each logon object that you instantiate and include this **MAPIUID** in the first 16 bytes of the **ab** member of every entry identifier that you create.</span></span> <span data-ttu-id="bbbaa-114">MAPI 使用**MAPIUID**结构将对象与服务提供程序相关联。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-114">MAPI uses **MAPIUID** structures to associate objects with service providers.</span></span> <span data-ttu-id="bbbaa-115">当[IMAPISession::OpenEntry](imapisession-openentry.md)方法打开一个对象，MAPI 检查的项标识符的**MAPIUID**部分客户端呼叫时，将其与注册**MAPIUID**，以确定哪些登录对象匹配应收到打开请求。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-115">When a client calls the [IMAPISession::OpenEntry](imapisession-openentry.md) method to open an object, MAPI examines the **MAPIUID** portion of the entry identifier, matching it against the registered **MAPIUID**, to determine which logon object should receive the open request.</span></span>
    
3. <span data-ttu-id="bbbaa-116">MAPI 呼叫**IXPLogon::AddressTypes**方法时，如果您的提供商，传输注册一个或多个**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-116">If your provider is a transport, register one or more **MAPIUID** structures when MAPI calls your **IXPLogon::AddressTypes** method.</span></span> <span data-ttu-id="bbbaa-117">MAPI 使用由传输提供程序注册的**MAPIUID**结构分配用于邮件传递的责任。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-117">MAPI uses the **MAPIUID** structures registered by transport providers to assign responsibility for message delivery.</span></span> 
    
<span data-ttu-id="bbbaa-118">尽管服务提供商通常注册单个**MAPIUID**，您可以注册多个**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-118">Although service providers typically register a single **MAPIUID**, you can register multiple **MAPIUID** structures.</span></span> <span data-ttu-id="bbbaa-119">如果您的通讯簿或消息存储提供程序支持多个登录对象，可能是通过允许用户向其配置文件添加多个提供程序的实例，您可能希望实现的每个登录对象不同**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-119">If your address book or message store provider supports multiple logon objects, perhaps by permitting a user to add more than one instance of your provider to their profile, you might want to implement a different **MAPIUID** for each logon object.</span></span> <span data-ttu-id="bbbaa-120">有几个其他原因，以支持多个**MAPIUID**:</span><span class="sxs-lookup"><span data-stu-id="bbbaa-120">There are a few other reasons to support more than one **MAPIUID**:</span></span>
  
- <span data-ttu-id="bbbaa-121">您必须支持多个提供程序的版本和条目标识符必须表示的适当版本。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-121">You must support more than one version of your provider and the entry identifiers must represent the appropriate version.</span></span> <span data-ttu-id="bbbaa-122">分配每个版本不同**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-122">Assign a different **MAPIUID** for each version.</span></span> 
    
- <span data-ttu-id="bbbaa-123">您想要区分支持的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-123">You want to distinguish between the types of objects you support.</span></span> <span data-ttu-id="bbbaa-124">例如，通讯簿提供程序可能想要注册一个**MAPIUID**用于其消息的用户对象的项标识符和不同的**MAPIUID**用于通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-124">For example, an address book provider might want to register one **MAPIUID** to use in the entry identifiers of its messaging user objects and a different **MAPIUID** to use for distribution lists.</span></span> 
    
<span data-ttu-id="bbbaa-125">当存在多个同时处于活动状态的登录对象时，就应该具有为每个唯一**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-125">When there are multiple logon objects that are concurrently active, it makes sense to have unique **MAPIUID** structures for each one.</span></span> <span data-ttu-id="bbbaa-126">这可增加与 MAPI 与匹配条目标识符与服务提供商并保存某些工作的准确性。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-126">This increases the accuracy with which MAPI matches entry identifiers to service providers and saves some work.</span></span> <span data-ttu-id="bbbaa-127">当每个登录对象具有自己的唯一标识符时，MAPI 都无法保证任何请求路由到登录对象可以处理由该对象。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-127">When every logon object has its own unique identifier, MAPI can guarantee that any request it routes to a logon object can be handled by that object.</span></span> <span data-ttu-id="bbbaa-128">登录对象共享**MAPIUID**结构，MAPI 将请求路由到由**MAPIUID**的第一个登录对象。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-128">When logon objects share **MAPIUID** structures, MAPI routes the request to the first logon object that is identified by the **MAPIUID**.</span></span> <span data-ttu-id="bbbaa-129">如果您的登录对象之一收到它无法处理，因为它无法处理的项标识符的请求，请将返回错误之前传递到下一步登录对象的请求。</span><span class="sxs-lookup"><span data-stu-id="bbbaa-129">If one of your logon objects receives a request that it cannot process because it does not handle the entry identifier, pass the request on to your next logon object before returning an error.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbbaa-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbbaa-130">See also</span></span>



[<span data-ttu-id="bbbaa-131">实现服务提供程序的登录名</span><span class="sxs-lookup"><span data-stu-id="bbbaa-131">Implementing Service Provider Logon</span></span>](implementing-service-provider-logon.md)

