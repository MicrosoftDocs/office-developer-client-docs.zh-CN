---
title: Outlook MAPI 引用概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
api_type:
- COM
ms.assetid: 4c126d0c-d7c0-45c0-801c-c9f1e44c9db6
description: 上次修改时间：2013 年 2 月 1 日
localization_priority: Priority
ms.openlocfilehash: dc743824cf96800c32d4b4006ae86fbff0bd48a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348494"
---
# <a name="outlook-mapi-reference-overview"></a><span data-ttu-id="56cb7-103">Outlook MAPI 引用概述</span><span class="sxs-lookup"><span data-stu-id="56cb7-103">Outlook MAPI Reference Overview</span></span>

<span data-ttu-id="56cb7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56cb7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56cb7-105">本主题概述了 Outlook 2013 MAPI 引用文档的相关信息。</span><span class="sxs-lookup"><span data-stu-id="56cb7-105">This topic provides overview information about the Outlook 2013 MAPI Reference documentation.</span></span>
  
## <a name="about-this-documentation"></a><span data-ttu-id="56cb7-106">关于本文档</span><span class="sxs-lookup"><span data-stu-id="56cb7-106">About this documentation</span></span>

<span data-ttu-id="56cb7-107">本文档适用于 Microsoft Outlook 2013 中消息传送 API (MAPI) 的实现。</span><span class="sxs-lookup"><span data-stu-id="56cb7-107">This documentation applies to the implementation of the Messaging API (MAPI) in Microsoft Outlook 2013.</span></span> 
  
<span data-ttu-id="56cb7-108">在 Microsoft Office Outlook 2007 之前，MAPI 程序员引用是 Microsoft Exchange 文档的一部分。</span><span class="sxs-lookup"><span data-stu-id="56cb7-108">Previous to Microsoft Office Outlook 2007, the MAPI Programmer's Reference was part of the Microsoft Exchange documentation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56cb7-109">自 Microsoft Exchange Server 2007 起，Exchange 已不再强调 MAPI 的使用，因此对 Exchange 实现的支持有限。</span><span class="sxs-lookup"><span data-stu-id="56cb7-109">Because Exchange has deemphasized the use of MAPI since Microsoft Exchange Server 2007, support for the Exchange implementation is limited.</span></span> 
  
<span data-ttu-id="56cb7-110">MAPI 的 Outlook 实现不同于 Microsoft Exchange 实现。</span><span class="sxs-lookup"><span data-stu-id="56cb7-110">The Outlook implementation of MAPI differs from the Microsoft Exchange implementation.</span></span> <span data-ttu-id="56cb7-111">Outlook 实现适用于在客户端计算机上运行，并强调低延迟。</span><span class="sxs-lookup"><span data-stu-id="56cb7-111">The Outlook implementation is optimized for running on client computers and emphasizes low latency.</span></span> <span data-ttu-id="56cb7-112">Exchange 实现适用于重视高可用性和较好的多线程处理能力的服务器。</span><span class="sxs-lookup"><span data-stu-id="56cb7-112">The Exchange implementation is intended for servers where high availability and better multithreading are important.</span></span>
  
<span data-ttu-id="56cb7-113">本文档适用于在最终用户系统上运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="56cb7-113">Use this documentation for applications running on end-user systems.</span></span> <span data-ttu-id="56cb7-114">对于服务器应用程序，请使用 MAPI 的 Exchange 实现（如果适用），或使用当前的 Exchange API，例如 Exchange Web 服务。</span><span class="sxs-lookup"><span data-stu-id="56cb7-114">For server applications, use the Exchange implementation of MAPI if appropriate, or use current Exchange APIs such as Exchange Web Services.</span></span> <span data-ttu-id="56cb7-115">有关 Exchange Web 服务的详细信息，请参阅 [Exchange Web 服务参考](https://msdn.microsoft.com/library/bb204119.aspx)。</span><span class="sxs-lookup"><span data-stu-id="56cb7-115">For more information on Exchange Web Services, see the [Exchange Web Services Reference](https://msdn.microsoft.com/library/bb204119.aspx).</span></span>
  
<span data-ttu-id="56cb7-116">可以编写同时适用于 MAPI 的 Outlook 或 Exchange 实现的应用程序。</span><span class="sxs-lookup"><span data-stu-id="56cb7-116">It may be possible to write applications that work with either the Outlook or Exchange implementations of MAPI.</span></span> <span data-ttu-id="56cb7-117">例如，MFCMAPI 在任意一个平台上均运行良好。</span><span class="sxs-lookup"><span data-stu-id="56cb7-117">For example, MFCMAPI works well on either platform.</span></span> <span data-ttu-id="56cb7-118">这些实现有许多通用的功能，但也有一些显著和微妙的区别。</span><span class="sxs-lookup"><span data-stu-id="56cb7-118">The implementations have many common features, but there are differences both obvious and subtle.</span></span> <span data-ttu-id="56cb7-119">若旨在让应用程序适用于所有环境，则必须同时在这两个平台上仔细进行测试。</span><span class="sxs-lookup"><span data-stu-id="56cb7-119">You will have to test carefully on both platforms if you intend for your application to work in all environments.</span></span> <span data-ttu-id="56cb7-120">此测试需要两个系统，因为不支持同时在同一个操作系统安装上运行两个实现。</span><span class="sxs-lookup"><span data-stu-id="56cb7-120">This testing will require two systems because running both implementations on the same operating system installation is not supported.</span></span>
  
<span data-ttu-id="56cb7-121">请注意，MAPI 适用于对 MAPI 存储中数据的低级别访问，或用于生成传输、消息存储或通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="56cb7-121">Be aware that MAPI is appropriate for low-level access to data in a MAPI store or for building a transport, message store, or address book provider.</span></span> <span data-ttu-id="56cb7-122">由于 MAPI 绕过了 Outlook 的业务逻辑，因此在评估用于生成解决方案的 API 时，还应考虑 Outlook 对象模型的使用。</span><span class="sxs-lookup"><span data-stu-id="56cb7-122">Because MAPI bypasses Outlook's business logic, you should also consider the use of the Outlook object model when you evaluate APIs for building your solution.</span></span> <span data-ttu-id="56cb7-123">Outlook 对象模型的确封装 Outlook 业务逻辑，但不适合多线程代码、同步提供程序或 Windows 服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="56cb7-123">The Outlook object model does encapsulate Outlook business logic but is not suitable for multithreaded code, sync providers, or Windows Service applications.</span></span>
  
<span data-ttu-id="56cb7-124">有关此版本的新增功能的相关信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="56cb7-124">For information about what is new in this edition, see the following topics:</span></span>
  
- [<span data-ttu-id="56cb7-125">此版本的新增功能</span><span class="sxs-lookup"><span data-stu-id="56cb7-125">What's New in This Edition</span></span>](what-s-new-in-this-edition.md)
    
- [<span data-ttu-id="56cb7-126">此版本弃用的 API 元素</span><span class="sxs-lookup"><span data-stu-id="56cb7-126">API Elements Deprecated in This Edition</span></span>](api-elements-deprecated-in-this-edition.md)
    
<span data-ttu-id="56cb7-127">若刚开始开发 Outlook 的 MAPI 应用程序，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="56cb7-127">If you are new to developing MAPI applications for Outlook, see the following topics:</span></span>
  
- [<span data-ttu-id="56cb7-128">选择用于开发 Outlook 2013 解决方案的 API 或技术</span><span class="sxs-lookup"><span data-stu-id="56cb7-128">Selecting an API or technology for developing solutions for Outlook 2013</span></span>](https://msdn.microsoft.com/library/jj900714.aspx)
    
- [<span data-ttu-id="56cb7-129">常用头文件</span><span class="sxs-lookup"><span data-stu-id="56cb7-129">Commonly Used Header Files</span></span>](commonly-used-header-files.md)
    
- [<span data-ttu-id="56cb7-130">常用属性</span><span class="sxs-lookup"><span data-stu-id="56cb7-130">Commonly Used Properties</span></span>](commonly-used-properties.md)
    
- [<span data-ttu-id="56cb7-131">常用对象</span><span class="sxs-lookup"><span data-stu-id="56cb7-131">Commonly Used Objects</span></span>](commonly-used-objects.md)
    
<span data-ttu-id="56cb7-132">此参考的其他部分分为下列三种信息类型：</span><span class="sxs-lookup"><span data-stu-id="56cb7-132">The rest of this reference is categorized into the following three types of information:</span></span>
  
- <span data-ttu-id="56cb7-133">[MAPI 示例](mapi-samples.md) - 将你转到许多代码示例，这些示例将演示如何使用各种 API 元素，以及如何实现简单的 MAPI 提供程序并创建 Outlook 项目。</span><span class="sxs-lookup"><span data-stu-id="56cb7-133">[MAPI Samples](mapi-samples.md) - Directs you to many code samples that show the use of various API elements and how to implement basic MAPI providers and create Outlook items.</span></span> 
    
- <span data-ttu-id="56cb7-134">[MAPI 概念](mapi-concepts.md) - 说明 MAPI 的概念和体系结构。</span><span class="sxs-lookup"><span data-stu-id="56cb7-134">[MAPI Concepts](mapi-concepts.md) - Explains the concepts and architecture of MAPI.</span></span> 
    
- <span data-ttu-id="56cb7-135">[MAPI 参考](mapi-reference.md) - 详细介绍 MAPI 的功能、界面、结构和属性。</span><span class="sxs-lookup"><span data-stu-id="56cb7-135">[MAPI Reference](mapi-reference.md) - Provides detailed information about the functions, interfaces, structures, and properties in MAPI.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="56cb7-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56cb7-136">See also</span></span>

- [<span data-ttu-id="56cb7-137">Outlook MAPI 引用入门</span><span class="sxs-lookup"><span data-stu-id="56cb7-137">Getting Started with the Outlook MAPI Reference</span></span>](getting-started-with-the-outlook-mapi-reference.md)
- [<span data-ttu-id="56cb7-138">MAPI 示例</span><span class="sxs-lookup"><span data-stu-id="56cb7-138">MAPI Samples</span></span>](mapi-samples.md)
- [<span data-ttu-id="56cb7-139">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="56cb7-139">MAPI Concepts</span></span>](mapi-concepts.md)

