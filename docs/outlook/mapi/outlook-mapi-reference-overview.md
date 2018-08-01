---
title: Outlook MAPI 引用概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4c126d0c-d7c0-45c0-801c-c9f1e44c9db6
description: 上次修改时间： 2013 年 2 月 1 日
ms.openlocfilehash: c0d7faaa957167977606cd93800a085d62b214f5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776569"
---
# <a name="outlook-mapi-reference-overview"></a><span data-ttu-id="cf8db-103">Outlook MAPI 引用概述</span><span class="sxs-lookup"><span data-stu-id="cf8db-103">Outlook MAPI Reference Overview</span></span>

<span data-ttu-id="cf8db-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cf8db-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cf8db-105">本主题提供有关 Outlook 2013 MAPI 参考文档的概述信息。</span><span class="sxs-lookup"><span data-stu-id="cf8db-105">This topic provides overview information about the Outlook 2013 MAPI Reference documentation.</span></span>
  
## <a name="about-this-documentation"></a><span data-ttu-id="cf8db-106">关于本文档</span><span class="sxs-lookup"><span data-stu-id="cf8db-106">About this documentation</span></span>

<span data-ttu-id="cf8db-107">本文档适用于实现的消息处理 API (MAPI) Microsoft Outlook 2013 中。</span><span class="sxs-lookup"><span data-stu-id="cf8db-107">This documentation applies to the implementation of the Messaging API (MAPI) in Microsoft Outlook 2013.</span></span> 
  
<span data-ttu-id="cf8db-108">Microsoft Office Outlook 2007，之前 MAPI 程序员参考是 Microsoft Exchange 文档的一部分。</span><span class="sxs-lookup"><span data-stu-id="cf8db-108">Previous to Microsoft Office Outlook 2007, the MAPI Programmer's Reference was part of the Microsoft Exchange documentation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf8db-109">由于 Exchange 具有 Microsoft Exchange Server 2007 以来 deemphasized 使用 MAPI，支持的 Exchange 实施是有限。</span><span class="sxs-lookup"><span data-stu-id="cf8db-109">Because Exchange has deemphasized the use of MAPI since Microsoft Exchange Server 2007, support for the Exchange implementation is limited.</span></span> 
  
<span data-ttu-id="cf8db-110">与 Microsoft Exchange 实现不同的 MAPI Outlook 实现。</span><span class="sxs-lookup"><span data-stu-id="cf8db-110">The Outlook implementation of MAPI differs from the Microsoft Exchange implementation.</span></span> <span data-ttu-id="cf8db-111">Outlook 实现专为客户端计算机上运行并强调低延迟。</span><span class="sxs-lookup"><span data-stu-id="cf8db-111">The Outlook implementation is optimized for running on client computers and emphasizes low latency.</span></span> <span data-ttu-id="cf8db-112">Exchange 实施供服务器其中高可用性和更多线程重要。</span><span class="sxs-lookup"><span data-stu-id="cf8db-112">The Exchange implementation is intended for servers where high availability and better multithreading are important.</span></span>
  
<span data-ttu-id="cf8db-113">在最终用户系统上运行的应用程序使用本文档。</span><span class="sxs-lookup"><span data-stu-id="cf8db-113">Use this documentation for applications running on end-user systems.</span></span> <span data-ttu-id="cf8db-114">服务器应用程序，使用 MAPI 如果合适，Exchange 实现或使用如 Exchange Web 服务的当前 Exchange Api。</span><span class="sxs-lookup"><span data-stu-id="cf8db-114">For server applications, use the Exchange implementation of MAPI if appropriate, or use current Exchange APIs such as Exchange Web Services.</span></span> <span data-ttu-id="cf8db-115">Exchange Web 服务的详细信息，请参阅[Exchange Web 服务引用](http://msdn.microsoft.com/en-us/library/bb204119.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cf8db-115">For more information on Exchange Web Services, see the [Exchange Web Services Reference](http://msdn.microsoft.com/en-us/library/bb204119.aspx).</span></span>
  
<span data-ttu-id="cf8db-116">它可能可以编写使用 Outlook 或 Exchange 实现的 MAPI 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf8db-116">It may be possible to write applications that work with either the Outlook or Exchange implementations of MAPI.</span></span> <span data-ttu-id="cf8db-117">例如，MFCMAPI 也在任一平台上工作。</span><span class="sxs-lookup"><span data-stu-id="cf8db-117">For example, MFCMAPI works well on either platform.</span></span> <span data-ttu-id="cf8db-118">实现具有许多常见的功能，但有区别明显和不明显。</span><span class="sxs-lookup"><span data-stu-id="cf8db-118">The implementations have many common features, but there are differences both obvious and subtle.</span></span> <span data-ttu-id="cf8db-119">您将需要如果您希望您的应用程序，在所有的环境中工作，仔细测试这两个平台上。</span><span class="sxs-lookup"><span data-stu-id="cf8db-119">You will have to test carefully on both platforms if you intend for your application to work in all environments.</span></span> <span data-ttu-id="cf8db-120">此测试将需要两个系统，因为不支持运行于同一操作系统安装的两个实现。</span><span class="sxs-lookup"><span data-stu-id="cf8db-120">This testing will require two systems because running both implementations on the same operating system installation is not supported.</span></span>
  
<span data-ttu-id="cf8db-121">请注意，MAPI 适合低级别访问 MAPI 存储区中的数据或构建传输、 消息存储库或通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="cf8db-121">Be aware that MAPI is appropriate for low-level access to data in a MAPI store or for building a transport, message store, or address book provider.</span></span> <span data-ttu-id="cf8db-122">MAPI 绕过 Outlook 的业务逻辑，因为您还应考虑使用 Outlook 对象模型，用于生成您的解决方案评估 Api 时。</span><span class="sxs-lookup"><span data-stu-id="cf8db-122">Because MAPI bypasses Outlook's business logic, you should also consider the use of the Outlook object model when you evaluate APIs for building your solution.</span></span> <span data-ttu-id="cf8db-123">Outlook 对象模型执行封装 Outlook 业务逻辑，但不适用于多线程的代码、 同步提供程序或 Windows 服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf8db-123">The Outlook object model does encapsulate Outlook business logic but is not suitable for multithreaded code, sync providers, or Windows Service applications.</span></span>
  
<span data-ttu-id="cf8db-124">有关此版本中新增的信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="cf8db-124">For information about what is new in this edition, see the following topics:</span></span>
  
- [<span data-ttu-id="cf8db-125">此版本的新增功能</span><span class="sxs-lookup"><span data-stu-id="cf8db-125">What's New in This Edition</span></span>](what-s-new-in-this-edition.md)
    
- [<span data-ttu-id="cf8db-126">在此版本中弃用的 API 元素</span><span class="sxs-lookup"><span data-stu-id="cf8db-126">API Elements Deprecated in This Edition</span></span>](api-elements-deprecated-in-this-edition.md)
    
<span data-ttu-id="cf8db-127">如果您是新开发面向 Outlook 的 MAPI 应用程序，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="cf8db-127">If you are new to developing MAPI applications for Outlook, see the following topics:</span></span>
  
- [<span data-ttu-id="cf8db-128">选择的 API 或技术来开发解决方案的 Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="cf8db-128">Selecting an API or technology for developing solutions for Outlook 2013</span></span>](http://msdn.microsoft.com/en-us/library/jj900714.aspx)
    
- [<span data-ttu-id="cf8db-129">常用头文件</span><span class="sxs-lookup"><span data-stu-id="cf8db-129">Commonly Used Header Files</span></span>](commonly-used-header-files.md)
    
- [<span data-ttu-id="cf8db-130">常用属性</span><span class="sxs-lookup"><span data-stu-id="cf8db-130">Commonly Used Properties</span></span>](commonly-used-properties.md)
    
- [<span data-ttu-id="cf8db-131">常用对象</span><span class="sxs-lookup"><span data-stu-id="cf8db-131">Commonly Used Objects</span></span>](commonly-used-objects.md)
    
<span data-ttu-id="cf8db-132">此参考的其余部分分为以下三种类型的信息：</span><span class="sxs-lookup"><span data-stu-id="cf8db-132">The rest of this reference is categorized into the following three types of information:</span></span>
  
- <span data-ttu-id="cf8db-133">[MAPI 示例](mapi-samples.md)-将您定向到显示各种 API 元素以及如何实现基本 MAPI 提供程序和创建 Outlook 项目使用的多个代码示例。</span><span class="sxs-lookup"><span data-stu-id="cf8db-133">[MAPI Samples](mapi-samples.md) - Directs you to many code samples that show the use of various API elements and how to implement basic MAPI providers and create Outlook items.</span></span> 
    
- <span data-ttu-id="cf8db-134">[MAPI 概念](mapi-concepts.md)-介绍的概念和体系结构的 MAPI。</span><span class="sxs-lookup"><span data-stu-id="cf8db-134">[MAPI Concepts](mapi-concepts.md) - Explains the concepts and architecture of MAPI.</span></span> 
    
- <span data-ttu-id="cf8db-135">[MAPI 参考](mapi-reference.md)-提供有关函数、 接口、 结构和 MAPI 中的属性的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="cf8db-135">[MAPI Reference](mapi-reference.md) - Provides detailed information about the functions, interfaces, structures, and properties in MAPI.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="cf8db-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf8db-136">See also</span></span>

- [<span data-ttu-id="cf8db-137">Outlook MAPI 引用入门</span><span class="sxs-lookup"><span data-stu-id="cf8db-137">Getting Started with the Outlook MAPI Reference</span></span>](getting-started-with-the-outlook-mapi-reference.md)
- [<span data-ttu-id="cf8db-138">MAPI 示例（英文）</span><span class="sxs-lookup"><span data-stu-id="cf8db-138">MAPI Samples</span></span>](mapi-samples.md)
- [<span data-ttu-id="cf8db-139">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="cf8db-139">MAPI Concepts</span></span>](mapi-concepts.md)

