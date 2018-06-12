---
title: 有关示例包装 PST 存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 953391ce-31a2-3271-365a-284cf5e15d82
description: 上次修改时间： 2012 年 7 月 3 日
ms.openlocfilehash: 51aef9d8778997749e401b008ebdb4126a248ee0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774474"
---
# <a name="about-the-sample-wrapped-pst-store-provider"></a><span data-ttu-id="30b8c-103">有关示例包装 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="30b8c-103">About the Sample Wrapped PST Store Provider</span></span>

 
  
<span data-ttu-id="30b8c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="30b8c-104">**Applies to**: Outlook</span></span> 
  
## <a name="overview-of-message-store-providers"></a><span data-ttu-id="30b8c-105">消息存储提供程序概述</span><span class="sxs-lookup"><span data-stu-id="30b8c-105">Overview of Message Store Providers</span></span>

<span data-ttu-id="30b8c-106">消息存储提供程序处理对存储和检索的邮件和其他用户的客户端应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="30b8c-106">Message store providers handle the storage and retrieval of messages and other information for the users of client applications.</span></span> <span data-ttu-id="30b8c-107">使用称为的消息存储的分层系统，邮件信息的排列方式。</span><span class="sxs-lookup"><span data-stu-id="30b8c-107">The message information is organized by using a hierarchical system known as a message store.</span></span> <span data-ttu-id="30b8c-108">消息存储在多个级别实现与名为保留的不同类型的消息的文件夹的容器。</span><span class="sxs-lookup"><span data-stu-id="30b8c-108">The message store is implemented in multiple levels, with containers called folders that hold messages of different types.</span></span> <span data-ttu-id="30b8c-109">没有为邮件存储区; 中的级别数限制文件夹可以包含很多子文件夹。</span><span class="sxs-lookup"><span data-stu-id="30b8c-109">There is no limit to the number of levels in a message store; folders can contain many subfolders.</span></span>
  
<span data-ttu-id="30b8c-110">消息存储数据可以采用多种方式。</span><span class="sxs-lookup"><span data-stu-id="30b8c-110">Message store data can be used in a variety of ways.</span></span> <span data-ttu-id="30b8c-111">典型的电子邮件使用率，除了作为公共讨论的论坛、 参考文档的库或布告栏信息的容器，则可使用文件夹。</span><span class="sxs-lookup"><span data-stu-id="30b8c-111">In addition to the typical email usage, folders can be used as a forum for public discussion, as a repository for reference documents, or as a container for bulletin board information.</span></span> <span data-ttu-id="30b8c-112">许多类型的信息，一些可修改和不可以保留的单个消息存储。</span><span class="sxs-lookup"><span data-stu-id="30b8c-112">A single message store can hold many types of information, some modifiable and some not.</span></span> <span data-ttu-id="30b8c-113">多个客户端可以安装相同的消息存储库，使其轻松和快速共享数据。</span><span class="sxs-lookup"><span data-stu-id="30b8c-113">Multiple clients can install the same message store, making it easy and fast to share data.</span></span>
  
<span data-ttu-id="30b8c-114">消息存储文件夹允许进行排序和筛选消息和自定义中的用户界面 (UI) 显示的视图。</span><span class="sxs-lookup"><span data-stu-id="30b8c-114">Message store folders allow you to sort and filter messages and to customize the view in a user interface (UI) display.</span></span> <span data-ttu-id="30b8c-115">指向筛选的邮件保存在名为搜索结果文件夹的特殊文件夹中。</span><span class="sxs-lookup"><span data-stu-id="30b8c-115">Links to filtered messages are held in special folders called search-results folders.</span></span> <span data-ttu-id="30b8c-116">客户端应用程序的用户输入筛选条件，其中 MAPI 指限制和条件应用于一个或多个文件夹中存储的消息。</span><span class="sxs-lookup"><span data-stu-id="30b8c-116">The user of a client application enters filtering criteria, which MAPI refers to as a restriction, and the criteria is applied to the messages stored in one or more folders.</span></span> <span data-ttu-id="30b8c-117">例如，用户可能想要查看这些处理与到达日期晚于上一周的特定主题的邮件。</span><span class="sxs-lookup"><span data-stu-id="30b8c-117">For example, a user might want to view only those messages dealing with a particular subject with arrival dates that are more recent than last week.</span></span> <span data-ttu-id="30b8c-118">搜索结果文件夹中列出引用符合条件的邮件和实际的邮件保留在其正则文件夹。</span><span class="sxs-lookup"><span data-stu-id="30b8c-118">References to the messages that match the criteria are listed in the search-results folder and the real messages remain in their regular folders.</span></span>
  
<span data-ttu-id="30b8c-119">邮件是从一个用户或另一个用户或应用程序的应用程序传送的数据的单位。</span><span class="sxs-lookup"><span data-stu-id="30b8c-119">Messages are the units of data transferred from one user or application to another user or application.</span></span> <span data-ttu-id="30b8c-120">每个邮件包含一些消息文本和用于传输邮件信封信息。</span><span class="sxs-lookup"><span data-stu-id="30b8c-120">Every message contains some message text and message envelope information that is used for transmission.</span></span> <span data-ttu-id="30b8c-121">某些消息包括一个或多个附件或其他数据与传输的文件，另一条消息或 OLE 对象形式一条消息。</span><span class="sxs-lookup"><span data-stu-id="30b8c-121">Some messages include one or more attachments, or additional data related to and transported with a message in the form of a file, another message, or an OLE object.</span></span>
  
## <a name="the-sample-wrapped-pst-store-provider"></a><span data-ttu-id="30b8c-122">本示例自动换行 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="30b8c-122">The Sample Wrapped PST Store Provider</span></span>

<span data-ttu-id="30b8c-123">复制 API 允许您将项目从后端数据存储库复制到 Outlook PST 存储区。</span><span class="sxs-lookup"><span data-stu-id="30b8c-123">The Replication API allows you to replicate items from a back-end data repository into an Outlook PST store.</span></span> <span data-ttu-id="30b8c-124">您使用复制 API 数据复制到专用的 PST 存储并跟踪的同步状态。</span><span class="sxs-lookup"><span data-stu-id="30b8c-124">You use the Replication API to replicate the data into a dedicated PST store and keep track of the synchronization state.</span></span> <span data-ttu-id="30b8c-125">此方法不需要您要引入的自定义的 MAPI 存储提供，即复杂编写和维护。</span><span class="sxs-lookup"><span data-stu-id="30b8c-125">This approach does not require you to introduce a custom MAPI store provider, which is complex to write and maintain.</span></span> <span data-ttu-id="30b8c-126">但是，PST 存储提供程序需要使用复制 API 换行。</span><span class="sxs-lookup"><span data-stu-id="30b8c-126">However, the PST store provider does need to be wrapped to work with the Replication API.</span></span>
  
<span data-ttu-id="30b8c-127">示例自动换行 PST 存储提供程序存储数据作为后端使用的个人文件夹文件 (PST) 提供程序。</span><span class="sxs-lookup"><span data-stu-id="30b8c-127">The Sample Wrapped PST Store Provider uses the Personal Folders file (PST) provider as the back end for storing data.</span></span> <span data-ttu-id="30b8c-128">应与复制 API 结合使用的换行的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="30b8c-128">The wrapped PST store provider should be used in conjunction with the Replication API.</span></span> <span data-ttu-id="30b8c-129">有关详细信息，请参阅[有关复制 API](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="30b8c-129">For more information, see [About the Replication API](about-the-replication-api.md).</span></span> <span data-ttu-id="30b8c-130">大部分示例自动换行 PST 存储提供程序中的函数及其参数直接传递到基础太平洋标准时间提供程序。</span><span class="sxs-lookup"><span data-stu-id="30b8c-130">Most of the functions in the Sample Wrapped PST Store Provider pass their arguments directly to the underlying PST provider.</span></span> <span data-ttu-id="30b8c-131">某些功能需要特殊的实现，并且以下主题所述。</span><span class="sxs-lookup"><span data-stu-id="30b8c-131">Certain functions require special implementation and are described in the following topics.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="30b8c-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="30b8c-132">In this section</span></span>

- [<span data-ttu-id="30b8c-133">安装示例自动换行 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="30b8c-133">Installing the Sample Wrapped PST Store Provider</span></span>](installing-the-sample-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="30b8c-134">介绍如何下载并安装示例自动换行 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="30b8c-134">Explains how to download and install the Sample Wrapped PST Store Provider.</span></span>
    
- [<span data-ttu-id="30b8c-135">初始化换行的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="30b8c-135">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="30b8c-136">实现包装的 PST 存储提供程序的第一步是初始化和配置的换行的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="30b8c-136">The first step in implementing a wrapped PST store provider is to initialize and configure the wrapped PST store provider.</span></span>
    
- [<span data-ttu-id="30b8c-137">登录到换行的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="30b8c-137">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="30b8c-138">初始化换行的 PST 存储提供程序后，您必须实现函数，以便 MAPI 和 MAPI 后台处理程序可以登录到的换行的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="30b8c-138">After a wrapped PST store provider is initialized, you must implement functions so that MAPI and the MAPI spooler can log on to the wrapped PST store provider.</span></span>
    
- [<span data-ttu-id="30b8c-139">使用包装的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="30b8c-139">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="30b8c-140">若要使用换行的 PST 存储提供程序必须打包**[IMAPISupport::IUnknown](imapisupportiunknown.md)** 界面，以实现常见换行 PST 存储提供程序任务。</span><span class="sxs-lookup"><span data-stu-id="30b8c-140">To use a wrapped PST store provider you must wrap the **[IMAPISupport::IUnknown](imapisupportiunknown.md)** interface to implement common wrapped PST store provider tasks.</span></span> 
    
- [<span data-ttu-id="30b8c-141">关机的情况下被环绕的 PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="30b8c-141">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)
    
- <span data-ttu-id="30b8c-142">使用换行的 PST 存储提供程序之后，您必须正确关闭的换行的 PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="30b8c-142">After you finish using a wrapped PST store provider, you must properly shut down the wrapped PST store provider.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="30b8c-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30b8c-143">See also</span></span>



[<span data-ttu-id="30b8c-144">有关复制 API</span><span class="sxs-lookup"><span data-stu-id="30b8c-144">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="30b8c-145">开发 MAPI 消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="30b8c-145">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

