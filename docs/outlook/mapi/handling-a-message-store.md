---
title: 处理邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7eca0e1f-a855-4ef7-b892-0bddee59de5e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 933dbd95a4b2f82d78e6e8035936eb2be4ba09ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407541"
---
# <a name="handling-a-message-store"></a><span data-ttu-id="ca9ca-103">处理邮件存储</span><span class="sxs-lookup"><span data-stu-id="ca9ca-103">Handling a message store</span></span>
  
<span data-ttu-id="ca9ca-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca9ca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca9ca-105">处理邮件存储区是任何客户端的一组任务的重要部分。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-105">Handling a message store is an important part of any client's set of tasks.</span></span> <span data-ttu-id="ca9ca-106">这些任务包括打开、复制、移动、添加和删除文件夹和邮件、显示各种表、设置属性和控制访问级别。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-106">These tasks include opening, copying, moving, adding, and deleting folders and messages, displaying various tables, setting properties, and controlling access levels.</span></span>

- <span data-ttu-id="ca9ca-107">[打开邮件存储](opening-a-message-store.md): 介绍如何在会话过程中打开一个或多个邮件存储。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-107">[Opening a Message Store](opening-a-message-store.md): Describes how to open one or more message stores during a session.</span></span>
    
- <span data-ttu-id="ca9ca-108">[打开默认邮件存储](opening-the-default-message-store.md): 介绍如何打开默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-108">[Opening the Default Message Store](opening-the-default-message-store.md): Describes how to open the default message store.</span></span>
    
- <span data-ttu-id="ca9ca-109">[验证和初始化邮件存储](validating-and-initializing-a-message-store.md): 介绍如何初始化和验证邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-109">[Validating and Initializing a Message Store](validating-and-initializing-a-message-store.md): Describes how to initialize and validate a message store.</span></span>
    
- <span data-ttu-id="ca9ca-110">[搜索邮件存储](searching-a-message-store.md): 介绍如何在一个或多个文件夹中查找与搜索条件相匹配的邮件。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-110">[Searching a Message Store](searching-a-message-store.md): Describes how to look through one or more folders looking for messages that match search criteria.</span></span>
    
- <span data-ttu-id="ca9ca-111">[选择接收文件夹](selecting-a-receive-folder.md): 介绍了创建接收文件夹的步骤。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-111">[Selecting a Receive Folder](selecting-a-receive-folder.md): Describes the steps for creating a receive folder.</span></span>
    
- <span data-ttu-id="ca9ca-112">[打开邮件存储文件夹](opening-a-message-store-folder.md): 介绍如何打开文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-112">[Opening a Message Store Folder](opening-a-message-store-folder.md): Describes how to open a folder.</span></span>
    
- <span data-ttu-id="ca9ca-113">[显示文件夹内容表格](displaying-a-folder-contents-table.md): 介绍如何显示包含所有邮件的摘要信息的 "文件夹内容" 表。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-113">[Displaying a Folder Contents Table](displaying-a-folder-contents-table.md): Describes how to display the folder contents table that contains summary information about all of its messages.</span></span>
    
- <span data-ttu-id="ca9ca-114">[遍历 "收件箱" 文件夹](traversing-the-inbox-folder.md): 介绍如何在收件箱中的所有邮件之间循环。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-114">[Traversing the Inbox Folder](traversing-the-inbox-folder.md): Describes how to cycle through all the messages in the Inbox.</span></span>
    
- <span data-ttu-id="ca9ca-115">[复制或移动邮件或文件夹](copying-or-moving-a-message-or-a-folder.md): 介绍如何复制或移动一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-115">[Copying or Moving a Message or a Folder](copying-or-moving-a-message-or-a-folder.md): Describes how to copy or move one or more messages.</span></span>
    
- <span data-ttu-id="ca9ca-116">[打开邮件](opening-a-message.md): 介绍如何打开邮件。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-116">[Opening a Message](opening-a-message.md): Describes how to open a message.</span></span>
    
- <span data-ttu-id="ca9ca-117">[查找邮件的图标](finding-the-icon-for-a-message.md): 介绍如何查找与邮件相关联的图标。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-117">[Finding the Icon for a Message](finding-the-icon-for-a-message.md): Describes how to find an icon that is associated with a message.</span></span>
    
- <span data-ttu-id="ca9ca-118">[打开视图描述符](opening-a-view-descriptor.md): 介绍如何打开视图描述符。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-118">[Opening a View Descriptor](opening-a-view-descriptor.md): Describes how to open a view descriptor.</span></span>
    
- <span data-ttu-id="ca9ca-119">[删除邮件](deleting-a-message.md): 介绍如何删除邮件。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-119">[Deleting a Message](deleting-a-message.md): Describes how to delete a message.</span></span>
    
- <span data-ttu-id="ca9ca-120">[在收件箱中保存邮件](saving-a-message-in-the-inbox.md): 介绍如何在收件箱中存储邮件。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-120">[Saving a Message in the Inbox](saving-a-message-in-the-inbox.md): Describes how to store a message in the Inbox.</span></span>
    
- <span data-ttu-id="ca9ca-121">[查找已发送或已保存的邮件](finding-sent-or-saved-messages.md): 介绍如何查找已保存或发送的所有传出邮件。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-121">[Finding Sent or Saved Messages](finding-sent-or-saved-messages.md): Describes how to locate all outgoing messages that have been saved or sent.</span></span>
    
- <span data-ttu-id="ca9ca-122">[跟踪对话](tracking-conversations.md): 介绍如何跟踪对话。</span><span class="sxs-lookup"><span data-stu-id="ca9ca-122">[Tracking Conversations](tracking-conversations.md): Describes how to track conversations.</span></span>
    

