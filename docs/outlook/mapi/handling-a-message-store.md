---
title: 处理的消息存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7eca0e1f-a855-4ef7-b892-0bddee59de5e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f915a17b8271f7ec4173f507504bf165a6084085
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775057"
---
# <a name="handling-a-message-store"></a><span data-ttu-id="cd7b5-103">处理的消息存储</span><span class="sxs-lookup"><span data-stu-id="cd7b5-103">Handling a message store</span></span>
  
<span data-ttu-id="cd7b5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cd7b5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cd7b5-105">处理的消息存储是组的任何客户端任务的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-105">Handling a message store is an important part of any client's set of tasks.</span></span> <span data-ttu-id="cd7b5-106">这些任务包括打开、 复制、 移动、 添加和删除文件夹和消息，显示各种表格，设置属性，以及控制访问级别。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-106">These tasks include opening, copying, moving, adding, and deleting folders and messages, displaying various tables, setting properties, and controlling access levels.</span></span>

- <span data-ttu-id="cd7b5-107">[打开消息存储](opening-a-message-store.md)： 介绍如何在会话过程中打开一个或多个邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-107">[Opening a Message Store](opening-a-message-store.md): Describes how to open one or more message stores during a session.</span></span>
    
- <span data-ttu-id="cd7b5-108">[打开默认的邮件存储](opening-the-default-message-store.md)： 介绍如何打开默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-108">[Opening the Default Message Store](opening-the-default-message-store.md): Describes how to open the default message store.</span></span>
    
- <span data-ttu-id="cd7b5-109">[Validating 和初始化消息存储](validating-and-initializing-a-message-store.md)： 介绍如何以初始化和验证的消息存储。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-109">[Validating and Initializing a Message Store](validating-and-initializing-a-message-store.md): Describes how to initialize and validate a message store.</span></span>
    
- <span data-ttu-id="cd7b5-110">[搜索消息存储](searching-a-message-store.md)： 介绍如何查看查找与搜索条件匹配的消息的一个或多个文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-110">[Searching a Message Store](searching-a-message-store.md): Describes how to look through one or more folders looking for messages that match search criteria.</span></span>
    
- <span data-ttu-id="cd7b5-111">[选择接收文件夹](selecting-a-receive-folder.md)： 描述的步骤用于创建的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-111">[Selecting a Receive Folder](selecting-a-receive-folder.md): Describes the steps for creating a receive folder.</span></span>
    
- <span data-ttu-id="cd7b5-112">[打开邮件存储文件夹](opening-a-message-store-folder.md)： 介绍如何打开一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-112">[Opening a Message Store Folder](opening-a-message-store-folder.md): Describes how to open a folder.</span></span>
    
- <span data-ttu-id="cd7b5-113">[显示文件夹内容表](displaying-a-folder-contents-table.md)： 介绍如何显示文件夹内容表包含有关的所有消息的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-113">[Displaying a Folder Contents Table](displaying-a-folder-contents-table.md): Describes how to display the folder contents table that contains summary information about all of its messages.</span></span>
    
- <span data-ttu-id="cd7b5-114">[遍历收件箱文件夹](traversing-the-inbox-folder.md)： 介绍如何循环收件箱中的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-114">[Traversing the Inbox Folder](traversing-the-inbox-folder.md): Describes how to cycle through all the messages in the Inbox.</span></span>
    
- <span data-ttu-id="cd7b5-115">[复制或移动邮件或文件夹](copying-or-moving-a-message-or-a-folder.md)： 介绍如何一个或多个邮件复制或移动。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-115">[Copying or Moving a Message or a Folder](copying-or-moving-a-message-or-a-folder.md): Describes how to copy or move one or more messages.</span></span>
    
- <span data-ttu-id="cd7b5-116">[打开一条消息](opening-a-message.md)： 介绍如何打开一封邮件。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-116">[Opening a Message](opening-a-message.md): Describes how to open a message.</span></span>
    
- <span data-ttu-id="cd7b5-117">[查找一条消息的图标](finding-the-icon-for-a-message.md)： 介绍如何查找与消息关联的图标。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-117">[Finding the Icon for a Message](finding-the-icon-for-a-message.md): Describes how to find an icon that is associated with a message.</span></span>
    
- <span data-ttu-id="cd7b5-118">[打开视图描述符](opening-a-view-descriptor.md)： 介绍如何打开视图描述符。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-118">[Opening a View Descriptor](opening-a-view-descriptor.md): Describes how to open a view descriptor.</span></span>
    
- <span data-ttu-id="cd7b5-119">[删除邮件](deleting-a-message.md)： 介绍如何删除一条消息。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-119">[Deleting a Message](deleting-a-message.md): Describes how to delete a message.</span></span>
    
- <span data-ttu-id="cd7b5-120">[保存收件箱中的邮件](saving-a-message-in-the-inbox.md)： 介绍如何在收件箱中存储一条消息。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-120">[Saving a Message in the Inbox](saving-a-message-in-the-inbox.md): Describes how to store a message in the Inbox.</span></span>
    
- <span data-ttu-id="cd7b5-121">[查找发送或保存邮件](finding-sent-or-saved-messages.md)： 介绍如何找到已保存或发送的所有传出邮件。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-121">[Finding Sent or Saved Messages](finding-sent-or-saved-messages.md): Describes how to locate all outgoing messages that have been saved or sent.</span></span>
    
- <span data-ttu-id="cd7b5-122">[跟踪对话](tracking-conversations.md)： 介绍如何跟踪对话。</span><span class="sxs-lookup"><span data-stu-id="cd7b5-122">[Tracking Conversations](tracking-conversations.md): Describes how to track conversations.</span></span>
    

