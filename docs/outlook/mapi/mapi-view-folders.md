---
title: MAPI 视图文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1936ec2-bf8a-4242-a41d-64d26b813bd0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ca9e5138d3ded13dfe33037f75e43ef1098f3c2d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412532"
---
# <a name="mapi-view-folders"></a><span data-ttu-id="eeec1-103">MAPI 视图文件夹</span><span class="sxs-lookup"><span data-stu-id="eeec1-103">MAPI View Folders</span></span>

  
  
<span data-ttu-id="eeec1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eeec1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eeec1-105">视图文件夹是包含相关信息的根文件夹，用于为 IPM 文件夹中的外 (内容定义) 布局。</span><span class="sxs-lookup"><span data-stu-id="eeec1-105">View folders are root folders that contain associated information to define alternative display layouts for the contents of interpersonal message (IPM) folders.</span></span> <span data-ttu-id="eeec1-106">查看文件夹位于邮件存储的根目录下，因此在典型的客户端应用程序中不可见。</span><span class="sxs-lookup"><span data-stu-id="eeec1-106">View folders reside under the root for the message store and, therefore, are not visible in the typical client application.</span></span> <span data-ttu-id="eeec1-107">不是每个邮件存储都包括视图文件夹;只有配置为用作会话的默认邮件存储的邮件存储必须包含它们。</span><span class="sxs-lookup"><span data-stu-id="eeec1-107">Not every message store includes view folders; only message stores that are configured to work as the default message store for the session must include them.</span></span>  
  
<span data-ttu-id="eeec1-108">MAPI 支持两个视图文件夹：</span><span class="sxs-lookup"><span data-stu-id="eeec1-108">MAPI supports two view folders:</span></span>
  
- <span data-ttu-id="eeec1-109">Common — 常见视图文件夹包含邮件存储的标准视图，并且供访问邮件存储的客户端的任何用户使用。</span><span class="sxs-lookup"><span data-stu-id="eeec1-109">Common — The common view folder contains views that are standard for the message store and can be used by any user of a client that accesses the message store.</span></span> <span data-ttu-id="eeec1-110">常用视图文件夹的条目标识符存储在存储的 PR_COMMON_VIEWS_ENTRYID ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)) 属性中。 </span><span class="sxs-lookup"><span data-stu-id="eeec1-110">The entry identifier for the common view folder is stored in the store's **PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="eeec1-111">个人 — 个人视图文件夹包含由特定用户定义的视图。</span><span class="sxs-lookup"><span data-stu-id="eeec1-111">Personal — The personal view folder contains views that are defined by a particular user.</span></span> <span data-ttu-id="eeec1-112">MAPI 定义PR_VIEWS_ENTRYID (个人视图) 条目标识符的[PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)属性。 </span><span class="sxs-lookup"><span data-stu-id="eeec1-112">MAPI defines the **PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)) property for holding the entry identifier of the personal view folder.</span></span> <span data-ttu-id="eeec1-113">例如，使用个人视图，一个用户可能会查看一组按发件人排序的邮件，其中只列出邮件主题和接收日期;另一个用户可能查看按日期排序的同一组，列出主题、发件人和邮件大小。</span><span class="sxs-lookup"><span data-stu-id="eeec1-113">Using personal views, for example, one user could look at a group of messages sorted by sender, listing only the message subject and receipt date; another user could look at the same group sorted by date, listing the subject, sender, and message size.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eeec1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eeec1-114">See also</span></span>



[<span data-ttu-id="eeec1-115">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="eeec1-115">MAPI Folders</span></span>](mapi-folders.md)

