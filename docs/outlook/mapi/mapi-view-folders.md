---
title: MAPI 查看文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1936ec2-bf8a-4242-a41d-64d26b813bd0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cb26771e9968175ab67366e35cf019ce23d51b8d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776352"
---
# <a name="mapi-view-folders"></a><span data-ttu-id="542d9-103">MAPI 查看文件夹</span><span class="sxs-lookup"><span data-stu-id="542d9-103">MAPI View Folders</span></span>

  
  
<span data-ttu-id="542d9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="542d9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="542d9-105">查看文件夹是根文件夹，包含定义替代显示布局人际邮件 (IPM) 文件夹的内容的相关的信息。</span><span class="sxs-lookup"><span data-stu-id="542d9-105">View folders are root folders that contain associated information to define alternative display layouts for the contents of interpersonal message (IPM) folders.</span></span> <span data-ttu-id="542d9-106">查看文件夹位于邮件存储的根目录下，因此，不可见的典型的客户端应用程序中。</span><span class="sxs-lookup"><span data-stu-id="542d9-106">View folders reside under the root for the message store and, therefore, are not visible in the typical client application.</span></span> <span data-ttu-id="542d9-107">不是每个消息存储包括查看文件夹;仅配置为默认的邮件存储用作会话的消息存储必须包括它们。</span><span class="sxs-lookup"><span data-stu-id="542d9-107">Not every message store includes view folders; only message stores that are configured to work as the default message store for the session must include them.</span></span>  
  
<span data-ttu-id="542d9-108">MAPI 支持两个视图文件夹：</span><span class="sxs-lookup"><span data-stu-id="542d9-108">MAPI supports two view folders:</span></span>
  
- <span data-ttu-id="542d9-109">常见 — 公共视图文件夹中包含的是标准的消息存储库的并且可供客户端访问的消息存储的任何用户视图。</span><span class="sxs-lookup"><span data-stu-id="542d9-109">Common — The common view folder contains views that are standard for the message store and can be used by any user of a client that accesses the message store.</span></span> <span data-ttu-id="542d9-110">存储在的存储**PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)) 属性中的公共视图文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="542d9-110">The entry identifier for the common view folder is stored in the store's **PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="542d9-111">个人 — 个人视图文件夹包含由特定用户定义的视图。</span><span class="sxs-lookup"><span data-stu-id="542d9-111">Personal — The personal view folder contains views that are defined by a particular user.</span></span> <span data-ttu-id="542d9-112">MAPI 定义按住个人视图文件夹的项标识符的**PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="542d9-112">MAPI defines the **PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)) property for holding the entry identifier of the personal view folder.</span></span> <span data-ttu-id="542d9-113">使用个人视图，例如，一个用户无法查看一组按发件人，列出仅邮件主题和回执日期; 的消息另一个用户无法查看同一组按日期排序，列出的主题、 发件人和邮件大小。</span><span class="sxs-lookup"><span data-stu-id="542d9-113">Using personal views, for example, one user could look at a group of messages sorted by sender, listing only the message subject and receipt date; another user could look at the same group sorted by date, listing the subject, sender, and message size.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="542d9-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="542d9-114">See also</span></span>



[<span data-ttu-id="542d9-115">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="542d9-115">MAPI Folders</span></span>](mapi-folders.md)

