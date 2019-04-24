---
title: 注册服务提供程序唯一标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 964fceb4-8a1c-46c1-98e1-a325c9259f8b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9f4acbb06f85a88a6c057da263ae95e09f72e0bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328397"
---
# <a name="registering-service-provider-unique-identifiers"></a><span data-ttu-id="24893-103">注册服务提供程序唯一标识符</span><span class="sxs-lookup"><span data-stu-id="24893-103">Registering Service Provider Unique Identifiers</span></span>

  
  
<span data-ttu-id="24893-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24893-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24893-105">通讯簿、邮件存储和传输提供程序使用唯一标识符 (称为 " [MAPIUID](mapiuid.md) ") 来注册各种类型的服务对象。</span><span class="sxs-lookup"><span data-stu-id="24893-105">Address book, message store, and transport providers use a unique identifier known as a [MAPIUID](mapiuid.md) to register to service objects of various types.</span></span> <span data-ttu-id="24893-106">**MAPIUID**是一个包含 GUID 的16字节标识符。</span><span class="sxs-lookup"><span data-stu-id="24893-106">A **MAPIUID** is a 16-byte identifier that contains a GUID.</span></span> <span data-ttu-id="24893-107">您可以使用以下过程创建**MAPIUID** :</span><span class="sxs-lookup"><span data-stu-id="24893-107">You can create a **MAPIUID** by using the following procedure:</span></span> 
  
1. <span data-ttu-id="24893-108">定义一个常量。</span><span class="sxs-lookup"><span data-stu-id="24893-108">Define a constant.</span></span>
    
2. <span data-ttu-id="24893-109">调用 Visual Studio*创建 GUID*\* 工具。</span><span class="sxs-lookup"><span data-stu-id="24893-109">Invoke the Visual Studio*Create GUID*\* tool.</span></span> 
    
<span data-ttu-id="24893-110">例如, 通讯簿提供程序可能在头文件中包含以下常量以定义**MAPIUID**:</span><span class="sxs-lookup"><span data-stu-id="24893-110">For example, an address book provider might include the following constant in a header file to define a **MAPIUID**:</span></span>
  
 `#define AB_UID_PROVIDER { 0Xe3, 0x3c, 0x67, 0xa0, \ 0xc8, 0x1f, 0x11, 0xce, \ 0xb2, 0xe4, 0x0, 0xaa, \ 0x0, 0x51, 0xe, 0x3b }`
  
 <span data-ttu-id="24893-111">**如果提供商是通讯簿或邮件存储提供程序, 则注册 MAPIUID**</span><span class="sxs-lookup"><span data-stu-id="24893-111">**To register a MAPIUID if your provider is an address book or message store provider**</span></span>
  
1. <span data-ttu-id="24893-112">调用[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)。</span><span class="sxs-lookup"><span data-stu-id="24893-112">Call [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md).</span></span>
    
2. <span data-ttu-id="24893-113">为您实例化的每个登录对象注册**MAPIUID** , 并在您创建的每个条目标识符的**ab**成员的前16个字节中包含此**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="24893-113">Register a **MAPIUID** for each logon object that you instantiate and include this **MAPIUID** in the first 16 bytes of the **ab** member of every entry identifier that you create.</span></span> <span data-ttu-id="24893-114">MAPI 使用**MAPIUID**结构将对象与服务提供程序相关联。</span><span class="sxs-lookup"><span data-stu-id="24893-114">MAPI uses **MAPIUID** structures to associate objects with service providers.</span></span> <span data-ttu-id="24893-115">当客户端调用[IMAPISession:: OpenEntry](imapisession-openentry.md)方法打开一个对象时, MAPI 会检查条目标识符的**MAPIUID**部分, 使其与注册的**MAPIUID**相匹配, 以确定哪个登录对象应接收打开的申请.</span><span class="sxs-lookup"><span data-stu-id="24893-115">When a client calls the [IMAPISession::OpenEntry](imapisession-openentry.md) method to open an object, MAPI examines the **MAPIUID** portion of the entry identifier, matching it against the registered **MAPIUID**, to determine which logon object should receive the open request.</span></span>
    
3. <span data-ttu-id="24893-116">如果您的提供商是传输, 则在 MAPI 调用您的**IXPLogon:: AddressTypes**方法时, 请注册一个或多个**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="24893-116">If your provider is a transport, register one or more **MAPIUID** structures when MAPI calls your **IXPLogon::AddressTypes** method.</span></span> <span data-ttu-id="24893-117">MAPI 使用由传输提供程序注册的**MAPIUID**结构来分配邮件传递的责任。</span><span class="sxs-lookup"><span data-stu-id="24893-117">MAPI uses the **MAPIUID** structures registered by transport providers to assign responsibility for message delivery.</span></span> 
    
<span data-ttu-id="24893-118">尽管服务提供商通常注册一个**MAPIUID**, 但您可以注册多个**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="24893-118">Although service providers typically register a single **MAPIUID**, you can register multiple **MAPIUID** structures.</span></span> <span data-ttu-id="24893-119">如果您的通讯簿或邮件存储提供程序支持多个登录对象 (可能是允许用户将提供程序的多个实例添加到其配置文件中), 则可能需要为每个登录对象实现一个不同的**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="24893-119">If your address book or message store provider supports multiple logon objects, perhaps by permitting a user to add more than one instance of your provider to their profile, you might want to implement a different **MAPIUID** for each logon object.</span></span> <span data-ttu-id="24893-120">支持多个**MAPIUID**的其他一些原因如下:</span><span class="sxs-lookup"><span data-stu-id="24893-120">There are a few other reasons to support more than one **MAPIUID**:</span></span>
  
- <span data-ttu-id="24893-121">您必须支持多个版本的提供程序, 条目标识符必须代表适当的版本。</span><span class="sxs-lookup"><span data-stu-id="24893-121">You must support more than one version of your provider and the entry identifiers must represent the appropriate version.</span></span> <span data-ttu-id="24893-122">为每个版本分配不同的**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="24893-122">Assign a different **MAPIUID** for each version.</span></span> 
    
- <span data-ttu-id="24893-123">您想区分所支持的对象类型。</span><span class="sxs-lookup"><span data-stu-id="24893-123">You want to distinguish between the types of objects you support.</span></span> <span data-ttu-id="24893-124">例如, 通讯簿提供商可能希望注册一个**MAPIUID**以在其邮件用户对象的条目标识符中使用, 并使用不同的**MAPIUID**来用于通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="24893-124">For example, an address book provider might want to register one **MAPIUID** to use in the entry identifiers of its messaging user objects and a different **MAPIUID** to use for distribution lists.</span></span> 
    
<span data-ttu-id="24893-125">当存在并发活动的多个登录对象时, 有必要为每个对象提供唯一的**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="24893-125">When there are multiple logon objects that are concurrently active, it makes sense to have unique **MAPIUID** structures for each one.</span></span> <span data-ttu-id="24893-126">这提高了 MAPI 将条目标识符与服务提供程序相匹配并保存一些工作的准确性。</span><span class="sxs-lookup"><span data-stu-id="24893-126">This increases the accuracy with which MAPI matches entry identifiers to service providers and saves some work.</span></span> <span data-ttu-id="24893-127">当每个登录对象都有其自己的唯一标识符时, MAPI 可以保证其路由到登录对象的任何请求都可以由该对象处理。</span><span class="sxs-lookup"><span data-stu-id="24893-127">When every logon object has its own unique identifier, MAPI can guarantee that any request it routes to a logon object can be handled by that object.</span></span> <span data-ttu-id="24893-128">当登录对象共享**MAPIUID**结构时, MAPI 会将请求路由到**MAPIUID**标识的第一个登录对象。</span><span class="sxs-lookup"><span data-stu-id="24893-128">When logon objects share **MAPIUID** structures, MAPI routes the request to the first logon object that is identified by the **MAPIUID**.</span></span> <span data-ttu-id="24893-129">如果你的某个登录对象收到由于未处理条目标识符而无法处理的请求, 请在返回错误之前将请求传递到下一个登录对象。</span><span class="sxs-lookup"><span data-stu-id="24893-129">If one of your logon objects receives a request that it cannot process because it does not handle the entry identifier, pass the request on to your next logon object before returning an error.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="24893-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24893-130">See also</span></span>



[<span data-ttu-id="24893-131">实现服务提供程序登录</span><span class="sxs-lookup"><span data-stu-id="24893-131">Implementing Service Provider Logon</span></span>](implementing-service-provider-logon.md)

