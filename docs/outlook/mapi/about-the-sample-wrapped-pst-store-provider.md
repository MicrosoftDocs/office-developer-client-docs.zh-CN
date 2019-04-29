---
title: 关于示例包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 953391ce-31a2-3271-365a-284cf5e15d82
description: 上次修改时间:03 月3日, 2012
ms.openlocfilehash: 779dd96c4f07c0c5eee60ae046cd17db98eebfd9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432721"
---
# <a name="about-the-sample-wrapped-pst-store-provider"></a><span data-ttu-id="292bb-103">关于示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="292bb-103">About the Sample Wrapped PST Store Provider</span></span>

 
  
<span data-ttu-id="292bb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="292bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
## <a name="overview-of-message-store-providers"></a><span data-ttu-id="292bb-105">邮件存储区提供程序概述</span><span class="sxs-lookup"><span data-stu-id="292bb-105">Overview of Message Store Providers</span></span>

<span data-ttu-id="292bb-106">邮件存储提供程序处理邮件的存储和检索以及客户端应用程序用户的其他信息。</span><span class="sxs-lookup"><span data-stu-id="292bb-106">Message store providers handle the storage and retrieval of messages and other information for the users of client applications.</span></span> <span data-ttu-id="292bb-107">邮件信息通过使用称为 "邮件存储库" 的分层系统进行组织。</span><span class="sxs-lookup"><span data-stu-id="292bb-107">The message information is organized by using a hierarchical system known as a message store.</span></span> <span data-ttu-id="292bb-108">邮件存储在多个级别中实现, 容器称为文件夹, 其中包含不同类型的邮件。</span><span class="sxs-lookup"><span data-stu-id="292bb-108">The message store is implemented in multiple levels, with containers called folders that hold messages of different types.</span></span> <span data-ttu-id="292bb-109">对邮件存储区中的级别数没有限制;文件夹可以包含多个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="292bb-109">There is no limit to the number of levels in a message store; folders can contain many subfolders.</span></span>
  
<span data-ttu-id="292bb-110">可以通过多种方式使用邮件存储区数据。</span><span class="sxs-lookup"><span data-stu-id="292bb-110">Message store data can be used in a variety of ways.</span></span> <span data-ttu-id="292bb-111">除了典型的电子邮件使用之外, 还可以将文件夹用作公开讨论的论坛, 作为参考文档的存储库, 或作为公告板信息的容器。</span><span class="sxs-lookup"><span data-stu-id="292bb-111">In addition to the typical email usage, folders can be used as a forum for public discussion, as a repository for reference documents, or as a container for bulletin board information.</span></span> <span data-ttu-id="292bb-112">单个邮件存储区可以包含多种类型的信息, 一些是可修改的, 有些则不是。</span><span class="sxs-lookup"><span data-stu-id="292bb-112">A single message store can hold many types of information, some modifiable and some not.</span></span> <span data-ttu-id="292bb-113">多个客户端可以安装相同的邮件存储, 从而轻松快速地共享数据。</span><span class="sxs-lookup"><span data-stu-id="292bb-113">Multiple clients can install the same message store, making it easy and fast to share data.</span></span>
  
<span data-ttu-id="292bb-114">邮件存储文件夹允许您对邮件进行排序和筛选, 并在用户界面 (UI) 显示中自定义视图。</span><span class="sxs-lookup"><span data-stu-id="292bb-114">Message store folders allow you to sort and filter messages and to customize the view in a user interface (UI) display.</span></span> <span data-ttu-id="292bb-115">筛选出的邮件的链接保存在称为搜索结果文件夹的特殊文件夹中。</span><span class="sxs-lookup"><span data-stu-id="292bb-115">Links to filtered messages are held in special folders called search-results folders.</span></span> <span data-ttu-id="292bb-116">客户端应用程序的用户输入筛选条件, MAPI 将其称为限制, 并将条件应用于存储在一个或多个文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="292bb-116">The user of a client application enters filtering criteria, which MAPI refers to as a restriction, and the criteria is applied to the messages stored in one or more folders.</span></span> <span data-ttu-id="292bb-117">例如, 用户可能只想查看那些处理到达日期晚于上周的特定主题的邮件。</span><span class="sxs-lookup"><span data-stu-id="292bb-117">For example, a user might want to view only those messages dealing with a particular subject with arrival dates that are more recent than last week.</span></span> <span data-ttu-id="292bb-118">对与条件匹配的邮件的引用在搜索结果文件夹中列出, 实际邮件仍保留在其常规文件夹中。</span><span class="sxs-lookup"><span data-stu-id="292bb-118">References to the messages that match the criteria are listed in the search-results folder and the real messages remain in their regular folders.</span></span>
  
<span data-ttu-id="292bb-119">消息是从一个用户或应用程序传输到另一个用户或应用程序的数据的单位。</span><span class="sxs-lookup"><span data-stu-id="292bb-119">Messages are the units of data transferred from one user or application to another user or application.</span></span> <span data-ttu-id="292bb-120">每封邮件都包含一些用于传输的邮件文本和邮件信封信息。</span><span class="sxs-lookup"><span data-stu-id="292bb-120">Every message contains some message text and message envelope information that is used for transmission.</span></span> <span data-ttu-id="292bb-121">某些邮件包含一个或多个附件, 或与文件、另一封邮件或 OLE 对象的形式的邮件一起传输的或与之传输的其他数据。</span><span class="sxs-lookup"><span data-stu-id="292bb-121">Some messages include one or more attachments, or additional data related to and transported with a message in the form of a file, another message, or an OLE object.</span></span>
  
## <a name="the-sample-wrapped-pst-store-provider"></a><span data-ttu-id="292bb-122">包装的 PST 存储区提供程序示例</span><span class="sxs-lookup"><span data-stu-id="292bb-122">The Sample Wrapped PST Store Provider</span></span>

<span data-ttu-id="292bb-123">复制 API 允许您将项目从后端数据存储库复制到 Outlook PST 存储。</span><span class="sxs-lookup"><span data-stu-id="292bb-123">The Replication API allows you to replicate items from a back-end data repository into an Outlook PST store.</span></span> <span data-ttu-id="292bb-124">您可以使用复制 API 将数据复制到专用的 PST 存储, 并跟踪同步状态。</span><span class="sxs-lookup"><span data-stu-id="292bb-124">You use the Replication API to replicate the data into a dedicated PST store and keep track of the synchronization state.</span></span> <span data-ttu-id="292bb-125">此方法不要求您引入自定义 MAPI 存储提供程序, 这对编写和维护非常复杂。</span><span class="sxs-lookup"><span data-stu-id="292bb-125">This approach does not require you to introduce a custom MAPI store provider, which is complex to write and maintain.</span></span> <span data-ttu-id="292bb-126">但是, PST 存储提供程序需要进行包装以使用复制 API。</span><span class="sxs-lookup"><span data-stu-id="292bb-126">However, the PST store provider does need to be wrapped to work with the Replication API.</span></span>
  
<span data-ttu-id="292bb-127">示例包装的 PST 存储区提供程序使用个人文件夹文件 (PST) 提供程序作为存储数据的后端。</span><span class="sxs-lookup"><span data-stu-id="292bb-127">The Sample Wrapped PST Store Provider uses the Personal Folders file (PST) provider as the back end for storing data.</span></span> <span data-ttu-id="292bb-128">包装的 PST 存储区提供程序应与复制 API 结合使用。</span><span class="sxs-lookup"><span data-stu-id="292bb-128">The wrapped PST store provider should be used in conjunction with the Replication API.</span></span> <span data-ttu-id="292bb-129">有关详细信息, 请参阅[关于复制 API](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="292bb-129">For more information, see [About the Replication API](about-the-replication-api.md).</span></span> <span data-ttu-id="292bb-130">示例包装的 pst 存储提供程序中的大多数函数将其参数直接传递给基础 PST 提供程序。</span><span class="sxs-lookup"><span data-stu-id="292bb-130">Most of the functions in the Sample Wrapped PST Store Provider pass their arguments directly to the underlying PST provider.</span></span> <span data-ttu-id="292bb-131">某些函数需要特殊实现, 以下主题对此进行了说明。</span><span class="sxs-lookup"><span data-stu-id="292bb-131">Certain functions require special implementation and are described in the following topics.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="292bb-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="292bb-132">In this section</span></span>

- [<span data-ttu-id="292bb-133">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="292bb-133">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="292bb-134">介绍如何下载和安装示例包装的 PST 存储区提供程序。</span><span class="sxs-lookup"><span data-stu-id="292bb-134">Explains how to download and install the Sample Wrapped PST Store Provider.</span></span>
    
- [<span data-ttu-id="292bb-135">初始化打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="292bb-135">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="292bb-136">实现打包的 pst 存储提供程序的第一步是初始化和配置打包的 pst 存储区提供程序。</span><span class="sxs-lookup"><span data-stu-id="292bb-136">The first step in implementing a wrapped PST store provider is to initialize and configure the wrapped PST store provider.</span></span>
    
- [<span data-ttu-id="292bb-137">登录到打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="292bb-137">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="292bb-138">在包装的 pst 存储区提供程序初始化之后, 您必须实现功能, 以便 mapi 和 mapi 后台处理程序可以登录到打包的 pst 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="292bb-138">After a wrapped PST store provider is initialized, you must implement functions so that MAPI and the MAPI spooler can log on to the wrapped PST store provider.</span></span>
    
- [<span data-ttu-id="292bb-139">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="292bb-139">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="292bb-140">若要使用包装的 PST 存储区提供程序, 必须包装**[IMAPISupport:: IUnknown](imapisupportiunknown.md)** 接口以实现常见的打包 PST 存储提供程序任务。</span><span class="sxs-lookup"><span data-stu-id="292bb-140">To use a wrapped PST store provider you must wrap the **[IMAPISupport::IUnknown](imapisupportiunknown.md)** interface to implement common wrapped PST store provider tasks.</span></span> 
    
- [<span data-ttu-id="292bb-141">关闭打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="292bb-141">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="292bb-142">使用包装的 pst 存储区提供程序完成后, 必须正确关闭包装的 pst 存储区提供程序。</span><span class="sxs-lookup"><span data-stu-id="292bb-142">After you finish using a wrapped PST store provider, you must properly shut down the wrapped PST store provider.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="292bb-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="292bb-143">See also</span></span>



[<span data-ttu-id="292bb-144">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="292bb-144">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="292bb-145">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="292bb-145">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

