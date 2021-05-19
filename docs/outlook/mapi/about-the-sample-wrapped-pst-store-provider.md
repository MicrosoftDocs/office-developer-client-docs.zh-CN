---
title: 关于包装的 PST 存储提供程序示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 953391ce-31a2-3271-365a-284cf5e15d82
description: 上次修改时间：2012 年 7 月 3 日
ms.openlocfilehash: 779dd96c4f07c0c5eee60ae046cd17db98eebfd9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432721"
---
# <a name="about-the-sample-wrapped-pst-store-provider"></a><span data-ttu-id="291e5-103">关于包装的 PST 存储提供程序示例</span><span class="sxs-lookup"><span data-stu-id="291e5-103">About the Sample Wrapped PST Store Provider</span></span>

 
  
<span data-ttu-id="291e5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="291e5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
## <a name="overview-of-message-store-providers"></a><span data-ttu-id="291e5-105">邮件存储提供程序概述</span><span class="sxs-lookup"><span data-stu-id="291e5-105">Overview of Message Store Providers</span></span>

<span data-ttu-id="291e5-106">邮件存储提供程序为客户端应用程序的用户处理邮件和其他信息的存储和检索。</span><span class="sxs-lookup"><span data-stu-id="291e5-106">Message store providers handle the storage and retrieval of messages and other information for the users of client applications.</span></span> <span data-ttu-id="291e5-107">邮件信息使用称为邮件存储的分层系统进行组织。</span><span class="sxs-lookup"><span data-stu-id="291e5-107">The message information is organized by using a hierarchical system known as a message store.</span></span> <span data-ttu-id="291e5-108">邮件存储在多个级别实现，其中容器称为文件夹，用于保存不同类型的邮件。</span><span class="sxs-lookup"><span data-stu-id="291e5-108">The message store is implemented in multiple levels, with containers called folders that hold messages of different types.</span></span> <span data-ttu-id="291e5-109">对邮件存储中的级别数没有限制;文件夹可以包含许多子文件夹。</span><span class="sxs-lookup"><span data-stu-id="291e5-109">There is no limit to the number of levels in a message store; folders can contain many subfolders.</span></span>
  
<span data-ttu-id="291e5-110">邮件存储数据可通过多种方式使用。</span><span class="sxs-lookup"><span data-stu-id="291e5-110">Message store data can be used in a variety of ways.</span></span> <span data-ttu-id="291e5-111">除了典型的电子邮件用法之外，文件夹还可以用作公共讨论论坛、参考文档存储库或公告板信息的容器。</span><span class="sxs-lookup"><span data-stu-id="291e5-111">In addition to the typical email usage, folders can be used as a forum for public discussion, as a repository for reference documents, or as a container for bulletin board information.</span></span> <span data-ttu-id="291e5-112">一个邮件存储可以保存许多类型的信息，一些是可修改的，有些则不能。</span><span class="sxs-lookup"><span data-stu-id="291e5-112">A single message store can hold many types of information, some modifiable and some not.</span></span> <span data-ttu-id="291e5-113">多个客户端可以安装同一个邮件存储，从而方便且快速共享数据。</span><span class="sxs-lookup"><span data-stu-id="291e5-113">Multiple clients can install the same message store, making it easy and fast to share data.</span></span>
  
<span data-ttu-id="291e5-114">邮件存储文件夹允许你对邮件进行排序和筛选，并自定义用户界面中的视图 (UI) 显示。</span><span class="sxs-lookup"><span data-stu-id="291e5-114">Message store folders allow you to sort and filter messages and to customize the view in a user interface (UI) display.</span></span> <span data-ttu-id="291e5-115">筛选邮件的链接位于名为"搜索结果文件夹"的特殊文件夹中。</span><span class="sxs-lookup"><span data-stu-id="291e5-115">Links to filtered messages are held in special folders called search-results folders.</span></span> <span data-ttu-id="291e5-116">客户端应用程序的用户输入筛选条件，MAPI 作为限制引用，并且条件应用于存储在一个或多个文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="291e5-116">The user of a client application enters filtering criteria, which MAPI refers to as a restriction, and the criteria is applied to the messages stored in one or more folders.</span></span> <span data-ttu-id="291e5-117">例如，用户可能只希望查看那些处理特定主题的邮件（到达日期比上周最近）。</span><span class="sxs-lookup"><span data-stu-id="291e5-117">For example, a user might want to view only those messages dealing with a particular subject with arrival dates that are more recent than last week.</span></span> <span data-ttu-id="291e5-118">对匹配条件的邮件的引用列在搜索结果文件夹中，真实邮件仍保留在常规文件夹中。</span><span class="sxs-lookup"><span data-stu-id="291e5-118">References to the messages that match the criteria are listed in the search-results folder and the real messages remain in their regular folders.</span></span>
  
<span data-ttu-id="291e5-119">消息是从一个用户或应用程序传输到另一个用户或应用程序的数据的单位。</span><span class="sxs-lookup"><span data-stu-id="291e5-119">Messages are the units of data transferred from one user or application to another user or application.</span></span> <span data-ttu-id="291e5-120">每封邮件都包含一些用于传输的邮件文本和邮件信封信息。</span><span class="sxs-lookup"><span data-stu-id="291e5-120">Every message contains some message text and message envelope information that is used for transmission.</span></span> <span data-ttu-id="291e5-121">某些邮件包括一个或多个附件，或者与文件、其他邮件或 OLE 对象形式的邮件相关且与邮件一起传输的其他数据。</span><span class="sxs-lookup"><span data-stu-id="291e5-121">Some messages include one or more attachments, or additional data related to and transported with a message in the form of a file, another message, or an OLE object.</span></span>
  
## <a name="the-sample-wrapped-pst-store-provider"></a><span data-ttu-id="291e5-122">包装的 PST 存储提供程序示例</span><span class="sxs-lookup"><span data-stu-id="291e5-122">The Sample Wrapped PST Store Provider</span></span>

<span data-ttu-id="291e5-123">复制 API 允许您将项目从后端数据存储库复制到 Outlook PST 存储。</span><span class="sxs-lookup"><span data-stu-id="291e5-123">The Replication API allows you to replicate items from a back-end data repository into an Outlook PST store.</span></span> <span data-ttu-id="291e5-124">使用复制 API 将数据复制到专用 PST 存储并跟踪同步状态。</span><span class="sxs-lookup"><span data-stu-id="291e5-124">You use the Replication API to replicate the data into a dedicated PST store and keep track of the synchronization state.</span></span> <span data-ttu-id="291e5-125">此方法不要求引入自定义 MAPI 存储提供程序，该提供程序编写和维护比较复杂。</span><span class="sxs-lookup"><span data-stu-id="291e5-125">This approach does not require you to introduce a custom MAPI store provider, which is complex to write and maintain.</span></span> <span data-ttu-id="291e5-126">但是，PST 存储提供程序确实需要包装，以使用复制 API。</span><span class="sxs-lookup"><span data-stu-id="291e5-126">However, the PST store provider does need to be wrapped to work with the Replication API.</span></span>
  
<span data-ttu-id="291e5-127">包装的 PST 存储提供程序示例使用 PST (PST) 文件作为存储数据的后端。</span><span class="sxs-lookup"><span data-stu-id="291e5-127">The Sample Wrapped PST Store Provider uses the Personal Folders file (PST) provider as the back end for storing data.</span></span> <span data-ttu-id="291e5-128">包装的 PST 存储提供程序应该与复制 API 结合使用。</span><span class="sxs-lookup"><span data-stu-id="291e5-128">The wrapped PST store provider should be used in conjunction with the Replication API.</span></span> <span data-ttu-id="291e5-129">有关详细信息，请参阅[关于复制 API。](about-the-replication-api.md)</span><span class="sxs-lookup"><span data-stu-id="291e5-129">For more information, see [About the Replication API](about-the-replication-api.md).</span></span> <span data-ttu-id="291e5-130">示例包装 PST 存储提供程序中的大多数函数都直接将参数传递给基础 PST 提供程序。</span><span class="sxs-lookup"><span data-stu-id="291e5-130">Most of the functions in the Sample Wrapped PST Store Provider pass their arguments directly to the underlying PST provider.</span></span> <span data-ttu-id="291e5-131">某些函数需要特殊实现，以下主题对此进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="291e5-131">Certain functions require special implementation and are described in the following topics.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="291e5-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="291e5-132">In this section</span></span>

- [<span data-ttu-id="291e5-133">安装包装的 PST 存储提供程序示例</span><span class="sxs-lookup"><span data-stu-id="291e5-133">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="291e5-134">介绍如何下载和安装包装示例 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="291e5-134">Explains how to download and install the Sample Wrapped PST Store Provider.</span></span>
    
- [<span data-ttu-id="291e5-135">初始化包装的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="291e5-135">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="291e5-136">实现包装的 PST 存储提供程序的第一步是初始化和配置封装的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="291e5-136">The first step in implementing a wrapped PST store provider is to initialize and configure the wrapped PST store provider.</span></span>
    
- [<span data-ttu-id="291e5-137">登录到包装的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="291e5-137">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="291e5-138">初始化包装的 PST 存储提供程序后，必须实现函数，以便 MAPI 和 MAPI 后台处理程序可以登录到包装的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="291e5-138">After a wrapped PST store provider is initialized, you must implement functions so that MAPI and the MAPI spooler can log on to the wrapped PST store provider.</span></span>
    
- [<span data-ttu-id="291e5-139">使用包装的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="291e5-139">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="291e5-140">若要使用包装的 PST 存储提供程序，必须包装 **[IMAPISupport：：IUnknown](imapisupportiunknown.md)** 接口来实现常见的封装 PST 存储提供程序任务。</span><span class="sxs-lookup"><span data-stu-id="291e5-140">To use a wrapped PST store provider you must wrap the **[IMAPISupport::IUnknown](imapisupportiunknown.md)** interface to implement common wrapped PST store provider tasks.</span></span> 
    
- [<span data-ttu-id="291e5-141">关闭包装的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="291e5-141">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="291e5-142">使用包装的 PST 存储提供程序完成后，必须正确关闭包装的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="291e5-142">After you finish using a wrapped PST store provider, you must properly shut down the wrapped PST store provider.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="291e5-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="291e5-143">See also</span></span>



[<span data-ttu-id="291e5-144">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="291e5-144">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="291e5-145">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="291e5-145">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

