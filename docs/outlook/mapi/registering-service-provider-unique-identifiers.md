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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410173"
---
# <a name="registering-service-provider-unique-identifiers"></a><span data-ttu-id="a3a51-103">注册服务提供程序唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a3a51-103">Registering Service Provider Unique Identifiers</span></span>

  
  
<span data-ttu-id="a3a51-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a3a51-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a3a51-105">通讯簿、邮件存储和传输提供程序使用称为 [MAPIUID](mapiuid.md) 的唯一标识符注册到各种类型的服务对象。</span><span class="sxs-lookup"><span data-stu-id="a3a51-105">Address book, message store, and transport providers use a unique identifier known as a [MAPIUID](mapiuid.md) to register to service objects of various types.</span></span> <span data-ttu-id="a3a51-106">**MAPIUID** 是包含 GUID 的 16 字节标识符。</span><span class="sxs-lookup"><span data-stu-id="a3a51-106">A **MAPIUID** is a 16-byte identifier that contains a GUID.</span></span> <span data-ttu-id="a3a51-107">可以使用以下 **过程创建 MAPIUID：**</span><span class="sxs-lookup"><span data-stu-id="a3a51-107">You can create a **MAPIUID** by using the following procedure:</span></span> 
  
1. <span data-ttu-id="a3a51-108">定义一个常量。</span><span class="sxs-lookup"><span data-stu-id="a3a51-108">Define a constant.</span></span>
    
2. <span data-ttu-id="a3a51-109">调用Visual Studio *GUID*\* 工具。</span><span class="sxs-lookup"><span data-stu-id="a3a51-109">Invoke the Visual Studio *Create GUID*\* tool.</span></span> 
    
<span data-ttu-id="a3a51-110">例如，通讯簿提供程序可能将以下常量包括在头文件中以定义 **MAPIUID**：</span><span class="sxs-lookup"><span data-stu-id="a3a51-110">For example, an address book provider might include the following constant in a header file to define a **MAPIUID**:</span></span>
  
 `#define AB_UID_PROVIDER { 0Xe3, 0x3c, 0x67, 0xa0, \ 0xc8, 0x1f, 0x11, 0xce, \ 0xb2, 0xe4, 0x0, 0xaa, \ 0x0, 0x51, 0xe, 0x3b }`
  
 <span data-ttu-id="a3a51-111">**如果提供程序是通讯簿或邮件存储提供程序，则注册 MAPIUID**</span><span class="sxs-lookup"><span data-stu-id="a3a51-111">**To register a MAPIUID if your provider is an address book or message store provider**</span></span>
  
1. <span data-ttu-id="a3a51-112">调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md)。</span><span class="sxs-lookup"><span data-stu-id="a3a51-112">Call [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md).</span></span>
    
2. <span data-ttu-id="a3a51-113">为实例化的每个登录对象注册 **MAPIUID，** 并在此创建的每个条目标识符的 **ab** 成员前 16 个字节中包括此 **MAPIUID。**</span><span class="sxs-lookup"><span data-stu-id="a3a51-113">Register a **MAPIUID** for each logon object that you instantiate and include this **MAPIUID** in the first 16 bytes of the **ab** member of every entry identifier that you create.</span></span> <span data-ttu-id="a3a51-114">MAPI 使用 **MAPIUID** 结构将对象与服务提供商关联。</span><span class="sxs-lookup"><span data-stu-id="a3a51-114">MAPI uses **MAPIUID** structures to associate objects with service providers.</span></span> <span data-ttu-id="a3a51-115">当客户端调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 方法打开对象时，MAPI 将检查条目标识符的 **MAPIUID** 部分，并针对注册的 **MAPIUID** 进行匹配，以确定哪个登录对象应接收打开的请求。</span><span class="sxs-lookup"><span data-stu-id="a3a51-115">When a client calls the [IMAPISession::OpenEntry](imapisession-openentry.md) method to open an object, MAPI examines the **MAPIUID** portion of the entry identifier, matching it against the registered **MAPIUID**, to determine which logon object should receive the open request.</span></span>
    
3. <span data-ttu-id="a3a51-116">如果提供程序是传输提供程序，请在 MAPI 调用 **IXPLogon：：AddressTypes** 方法时注册一个或多个 **MAPIUID** 结构。</span><span class="sxs-lookup"><span data-stu-id="a3a51-116">If your provider is a transport, register one or more **MAPIUID** structures when MAPI calls your **IXPLogon::AddressTypes** method.</span></span> <span data-ttu-id="a3a51-117">MAPI 使用由传输提供程序注册的 **MAPIUID** 结构来分配邮件传递的责任。</span><span class="sxs-lookup"><span data-stu-id="a3a51-117">MAPI uses the **MAPIUID** structures registered by transport providers to assign responsibility for message delivery.</span></span> 
    
<span data-ttu-id="a3a51-118">虽然服务提供商通常注册一个 **MAPIUID，** 但您可以注册多个 **MAPIUID** 结构。</span><span class="sxs-lookup"><span data-stu-id="a3a51-118">Although service providers typically register a single **MAPIUID**, you can register multiple **MAPIUID** structures.</span></span> <span data-ttu-id="a3a51-119">如果通讯簿或邮件存储提供程序支持多个登录对象（可能允许用户将提供程序的多个实例添加到其配置文件中，则您可能希望针对每个登录对象实现不同的 **MAPIUID）。**</span><span class="sxs-lookup"><span data-stu-id="a3a51-119">If your address book or message store provider supports multiple logon objects, perhaps by permitting a user to add more than one instance of your provider to their profile, you might want to implement a different **MAPIUID** for each logon object.</span></span> <span data-ttu-id="a3a51-120">支持多个 **MAPIUID** 的其他一些原因如下：</span><span class="sxs-lookup"><span data-stu-id="a3a51-120">There are a few other reasons to support more than one **MAPIUID**:</span></span>
  
- <span data-ttu-id="a3a51-121">必须支持多个版本的提供程序，并且条目标识符必须表示相应的版本。</span><span class="sxs-lookup"><span data-stu-id="a3a51-121">You must support more than one version of your provider and the entry identifiers must represent the appropriate version.</span></span> <span data-ttu-id="a3a51-122">为每个版本分配不同的 **MAPIUID。**</span><span class="sxs-lookup"><span data-stu-id="a3a51-122">Assign a different **MAPIUID** for each version.</span></span> 
    
- <span data-ttu-id="a3a51-123">要区分支持的对象类型。</span><span class="sxs-lookup"><span data-stu-id="a3a51-123">You want to distinguish between the types of objects you support.</span></span> <span data-ttu-id="a3a51-124">例如，通讯簿提供程序可能想要注册一 **个 MAPIUID** 以用于其邮件用户对象的条目标识符和另一个 **MAPIUID** 以用于通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="a3a51-124">For example, an address book provider might want to register one **MAPIUID** to use in the entry identifiers of its messaging user objects and a different **MAPIUID** to use for distribution lists.</span></span> 
    
<span data-ttu-id="a3a51-125">当有多个同时处于活动状态的登录对象时，每个对象具有唯一 **的 MAPIUID** 结构是有意义的。</span><span class="sxs-lookup"><span data-stu-id="a3a51-125">When there are multiple logon objects that are concurrently active, it makes sense to have unique **MAPIUID** structures for each one.</span></span> <span data-ttu-id="a3a51-126">这将提高 MAPI 与服务提供程序的条目标识符匹配并节省一些工作的准确性。</span><span class="sxs-lookup"><span data-stu-id="a3a51-126">This increases the accuracy with which MAPI matches entry identifiers to service providers and saves some work.</span></span> <span data-ttu-id="a3a51-127">当每个登录对象都有其自己的唯一标识符时，MAPI 可以保证它路由到登录对象的任何请求都可以通过该对象进行处理。</span><span class="sxs-lookup"><span data-stu-id="a3a51-127">When every logon object has its own unique identifier, MAPI can guarantee that any request it routes to a logon object can be handled by that object.</span></span> <span data-ttu-id="a3a51-128">当登录对象共享 **MAPIUID 结构时，MAPI** 将请求路由到 **MAPIUID** 标识的第一个登录对象。</span><span class="sxs-lookup"><span data-stu-id="a3a51-128">When logon objects share **MAPIUID** structures, MAPI routes the request to the first logon object that is identified by the **MAPIUID**.</span></span> <span data-ttu-id="a3a51-129">如果其中一个登录对象收到由于不处理条目标识符而无法处理的请求，则先将请求传递到下一个登录对象，然后再返回错误。</span><span class="sxs-lookup"><span data-stu-id="a3a51-129">If one of your logon objects receives a request that it cannot process because it does not handle the entry identifier, pass the request on to your next logon object before returning an error.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3a51-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3a51-130">See also</span></span>



[<span data-ttu-id="a3a51-131">实现服务提供程序登录</span><span class="sxs-lookup"><span data-stu-id="a3a51-131">Implementing Service Provider Logon</span></span>](implementing-service-provider-logon.md)

